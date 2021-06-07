---
description: Используйте расширенную технику анализа объема в ваших индикаторах
---

# Доступ к данным анализа объема из индикаторов

Торговая платформа Quantower имеет широкий набор[ **инструментов анализа объема**](https://www.quantower.com/volumeanalysistools), расширенную аналитическую функциональность, которая позволяет вам видеть торгуемый объем на каждом уровне цены, оценивать баланс между покупателями и продавцами и понимать намерения трейдеров относительно будущей цены.

Вы можете легко получить доступ ко всем данным анализа объемов из вашего индикатора. По умолчанию графики не загружают такие данные, так как для получения полной истории сделок требуется время. Вам необходимо уведомить график, что он нужен вашему индикатору для расчетов, и вы можете сделать это, реализовав специальный интерфейс IVolumeAnalysisIndicator:

```csharp
public class IndicatorVolumeAnalysis : Indicator, IVolumeAnalysisIndicator
{       
    ...
```

Он содержит только один метод VolumeAnalysisData\_Loaded и он будет вызван, когда все необходимые данные закончат загрузку:

```csharp
public void VolumeAnalysisData_Loaded()
{
    // Add your logic here
}
```

Если вам нужно знать текущее состояние загрузки, вы можете использовать Прогресс расчета анализа объема из исторических данные. Если загрузка была запущена, этот объект будет установлен, и вы можете узнать текущее состояние или даже процент загруженных данных:

```csharp
if (HistoricalData.VolumeAnalysisCalculationProgress.State != VolumeAnalysisCalculationState.Finished
    Core.Instance.Loggers.Log(HistoricalData.VolumeAnalysisCalculationProgress.ProgressPercent.ToString());
```

По завершении загрузки объект Total будет доступен для каждого HistoryItem из HistoricalData, который обеспечивает доступ к агрегированным данным анализа объема:

```csharp
HistoricalData[0].VolumeAnalysisData.Total.Volume
HistoricalData[0].VolumeAnalysisData.Total.Trades
HistoricalData[0].VolumeAnalysisData.Total.AverageBuySize
```

Список всех доступных типов данных:

| Тип данных | Описание |
| :--- | :--- |
| Объем | Общий размер всех позиций, исполненных на каждом ценовом уровне или ценовом диапазоне. |
| Объем покупки | Общий размер всех позиций на покупку, выполненных на каждом ценовом уровне или ценовом диапазоне. |
| Объем продажи | Общий размер всех позиций на продажу, выполненных на каждом ценовом уровне или ценовом диапазоне. |
| Сделки | Количество контрактов \(сделок\), заключенных на каждом ценовом уровне. |
| Buy Сделки | Количество сделок на покупку, выполненных на каждом ценовом уровне. |
| Sell Сделки | Количество сделок на продажу, выполненных на каждом ценовом уровне. |
| Buy Объем в процентах | Показывает, сколько процентов от общего объема относится к сделкам на покупку |
| Sell Объем в процентах | Показывает, сколько процентов от общего объема относится к сделкам на продажу |
| Дельта | Показывает разницу в торговом объеме между покупателями и продавцами. Позволяет оценить, кто в данный момент контролирует цену на рынке. |
| Дельта-процент | Показывает разницу \(%\) в торговом объеме между покупателями и продавцами. Позволяет оценить, кто в данный момент контролирует цену на рынке. |
| Средний размер | Средний объем позиции, которая была исполнена по определенной цене или ценовому диапазону. |
| Средний Купить Размер | Средний объем позиции на покупку, которая была исполнена по определенной цене или в ценовом диапазоне. |
| Средний размер продажи | Средний объем позиции на продажу, которая была исполнена по определенной цене или ценовому диапазону. |
| Максимальный объем одной сделки | Показывает максимальный объем одной сделки, которая была исполнена по определенной цене или ценовому диапазону. |
| Максимальный объем одной сделки процент   | Показывает максимальный \(%\) объем одной сделки, которая была исполнена по определенной цене или ценовому диапазону. |

За исключением общей \(агрегированной\) информации, у вас есть доступ к данным анализа объема для каждой цены в баре. Он доступен в словаре PriceLevels и содержит те же типы данных, что и Total:

```csharp
this.HistoricalData[0].VolumeAnalysisData.PriceLevels[1.2564].Volume
```

В качестве примера создадим простой индикатор, который будет рисовать 2 линии в отдельном окне графика. Первый покажет AverageBuySize, а второй - AverageSellSize. Это полный исходный код:

```csharp
using System;
using System.Drawing;
using TradingPlatform.BusinessLayer;
using TradingPlatform.BusinessLayer.Modules.Indicators;

namespace IndicatorVolumeAnalysis
{   
    public class IndicatorVolumeAnalysis : Indicator, IVolumeAnalysisIndicator
    {
        public IndicatorVolumeAnalysis()
            : base()
        {
            // Defines indicator's name and description.
            Name = "IndicatorVolumeAnalysis";
            Description = "My indicator's annotation";

            // Defines line on demand with particular parameters.
            AddLineSeries("AverageBuySize", Color.CadetBlue, 1, LineStyle.Solid);
            AddLineSeries("AverageSellSize", Color.Red, 1, LineStyle.Solid);

            // By default indicator will be applied on main window of the chart
            SeparateWindow = true;
        }

        public void VolumeAnalysisData_Loaded()
        {
            // Set value to all previous indicators points
            for (int i = 0; i < this.Count; i++)
            {
                SetValue(this.HistoricalData[i].VolumeAnalysisData.Total.AverageBuySize, 0, i);
                SetValue(this.HistoricalData[i].VolumeAnalysisData.Total.AverageSellSize, 1, i);
            }
        }

        protected override void OnUpdate(UpdateArgs args)
        {            
            // Volume analysis data not loaded yet
            if (this.HistoricalData.VolumeAnalysisCalculationProgress == null || this.HistoricalData.VolumeAnalysisCalculationProgress.State != VolumeAnalysisCalculationState.Finished)
                return;

            // Example of access Volume Analysis data
            SetValue(this.HistoricalData[0].VolumeAnalysisData.Total.AverageBuySize, 0);
            SetValue(this.HistoricalData[0].VolumeAnalysisData.Total.AverageSellSize, 1);            
        }               
    }
}
```

Когда мы построим этот индикатор и добавим его на график, мы увидим следующий результат:

![&#x41B;&#x438;&#x43D;&#x438;&#x438; &#x438;&#x43D;&#x434;&#x438;&#x43A;&#x430;&#x442;&#x43E;&#x440;&#x430; &#x43F;&#x43E;&#x43A;&#x430;&#x437;&#x44B;&#x432;&#x430;&#x44E;&#x442; &#x441;&#x440;&#x435;&#x434;&#x43D;&#x438;&#x439; &#x440;&#x430;&#x437;&#x43C;&#x435;&#x440; &#x43F;&#x43E;&#x43A;&#x443;&#x43F;&#x43A;&#x438; &#x438; &#x441;&#x440;&#x435;&#x434;&#x43D;&#x438;&#x439; &#x440;&#x430;&#x437;&#x43C;&#x435;&#x440; &#x43F;&#x440;&#x43E;&#x434;&#x430;&#x436;&#x438;.](../.gitbook/assets/volumeanalysisindicator.png)

В этом разделе мы показали вам простой пример индикатора, основанного на данных объемного анализа. Вы можете улучшить его и создать действительно продвинутый и сложный индикатор, похожий на инструменты Volume Analysis из Quantower, например Cluster Chart. В наших следующих разделах мы предоставим пример рисования профилей объема на диаграмме.

