---
description: >-
  Используйте результаты 50+ встроенных индикаторов Quantower в своих стратегиях
  и индикаторах
---

# Доступ к встроенным индикаторам

## Общее

При разработке собственных индикаторов или стратегии вам может потребоваться использование некоторых стандартных индикаторов, например скользящих средних. Вам не нужно писать для этого какой-либо код, поскольку торговая платформа Quantower предоставляет вам широкий набор предопределенных индикаторов. На данный момент существует около 50 встроенных индикаторов, среди них:

* EMA
* ADX
* Keltner
* ROC
* RSI
* KAMA
* AROON
* и много других

## Доступ к встроенным индикаторам

Вы можете получить доступ к встроенным индикаторам с помощью класса Core.Indicators.BuiltIn. Хорошее место для запуска таких индикаторов - метод OnInit вашего скрипта:

```csharp
Indicator AC;

protected override void OnInit()
{
    // An example of creation AC indicator
    AC = Core.Indicators.BuiltIn.AC();                
}
```

Индикатор может предоставлять некоторые параметры, и вы можете указать их при создании:

```csharp
Indicator EMA;

protected override void OnInit()
{
    // An example of creation EMA indicator with parameters: 
    // Period = 10
    // PriceType = Open
    EMA = Core.Indicators.BuiltIn.EMA(10, PriceType.Open);         
}
```

При необходимости вы можете создать несколько копий одного индикатора или несколько разных индикаторов:

```csharp
Indicator fastEMA;
Indicator slowEMA;

protected override void OnInit()
{
    // An example of creation a few EMA indicators with different parameters     
    fastEMA = Core.Indicators.BuiltIn.EMA(12, PriceType.Open);         
    slowEMA = Core.Indicators.BuiltIn.EMA(26, PriceType.Open);         
}
```

Теперь нам нужно назначить созданный индикатор нашему текущему скрипту - это означает, что он будет использовать символ и кавычки из своего родителя. Вы можете сделать это с помощью метода AddIndicator:

```csharp
Indicator EMA;

protected override void OnInit()
{
    // Create EMA indicator
    EMA = Core.Indicators.BuiltIn.EMA(10, PriceType.Open);

    // Add created EMA indicator as a child to our script
    AddIndicator(EMA);
}
```

Все готово для использования этого индикатора в наших расчетах. После получения новых котировок он будет рассчитан автоматически. Вы можете получить доступ к его значениям через метод [GetValue](http://api.quantower.com/docs/TradingPlatform.BusinessLayer.Indicator.html#TradingPlatform_BusinessLayer_Indicator_GetValue_System_Int32_System_Int32_TradingPlatform_BusinessLayer_SeekOriginHistory_):

```csharp
/// <summary>
/// Calculation entry point. This function is called when a price data updates. 
/// </summary>
protected override void OnUpdate(UpdateArgs args)
{
     // Get EMA value for current bar from first line
     double valueFromEMA = EMA.GetValue();

     // Using EMA value in parent indicator
     SetValue(valueFromEMA);            
}
```

Если вам нужно получить доступ к значению для предыдущих баров или к значению из строки других индикаторов, вы можете использовать смещение и параметр lineIndex метода [GetValue](http://api.quantower.com/docs/TradingPlatform.BusinessLayer.Indicator.html#TradingPlatform_BusinessLayer_Indicator_GetValue_System_Int32_System_Int32_TradingPlatform_BusinessLayer_SeekOriginHistory_) \*\*:

```csharp
/// <summary>
/// Calculation entry point. This function is called when a price data updates. 
/// </summary>
protected override void OnUpdate(UpdateArgs args)
{
     // Get EMA value for current bar from second line
     double valueFromEMA = EMA.GetValue(5, 1);

     // Using EMA value in parent indicator
     SetValue(valueFromEMA);            
}
```

Это полный исходный код нашего примера. Мы используем два индикатора EMA с разным периодом и отображаем их разницу на графике:

```csharp
using System.Drawing;
using TradingPlatform.BusinessLayer;


namespace IndicatorWithBuiltIn
{   
    public class IndicatorWithBuiltIn : Indicator
    {
        /// <summary>
        /// Built in indicators
        /// </summary>
        Indicator fastEMA;
        Indicator slowEMA;

        /// <summary>
        /// Indicator's constructor. Contains general information: name, description, LineSeries etc. 
        /// </summary>
        public IndicatorWithBuiltIn()
            : base()
        {
            // Defines indicator's name and description.
            Name = "IndicatorWithBuiltIn";

            // Defines line on demand with particular parameters.
            AddLineSeries("line1", Color.CadetBlue, 1, LineStyle.Solid);

            // By default indicator will be applied on main window of the chart
            SeparateWindow = true;
        }

        /// <summary>
        /// This function will be called after creating an indicator as well as after its input params reset or chart (symbol or timeframe) updates.
        /// </summary>
        protected override void OnInit()
        {
            // Create first instance of EMA indicator with Period 12
            fastEMA = Core.Indicators.BuiltIn.EMA(12, PriceType.Open);
            AddIndicator(fastEMA);

            // Create second instance of EMA indicator with period 26
            slowEMA = Core.Indicators.BuiltIn.EMA(26, PriceType.Open);
            AddIndicator(slowEMA);

        }

        /// <summary>
        /// Calculation entry point. This function is called when a price data updates. 
        /// </summary>
        protected override void OnUpdate(UpdateArgs args)
        {
            // Calculate difference
            double difference = fastEMA.GetValue() - slowEMA.GetValue();

            // Use difference as a value for parent indicator
            SetValue(difference);
        }
    }
}
```

И результат этого индикатора на графике:

![&#x412; &#x434;&#x43E;&#x43F;&#x43E;&#x43B;&#x43D;&#x438;&#x442;&#x435;&#x43B;&#x44C;&#x43D;&#x43E;&#x43C; &#x43E;&#x43A;&#x43D;&#x435; &#x433;&#x440;&#x430;&#x444;&#x438;&#x43A;&#x430; &#x43C;&#x44B; &#x432;&#x438;&#x434;&#x438;&#x43C; &#x440;&#x435;&#x437;&#x443;&#x43B;&#x44C;&#x442;&#x430;&#x442; &#x43D;&#x430;&#x448;&#x438;&#x445; &#x440;&#x430;&#x441;&#x447;&#x435;&#x442;&#x43E;&#x432;.](../.gitbook/assets/result.png)

Как видите, создать этот индикатор было несложно. Перед тем, как приступить к написанию собственного кода, проверьте сначала, возможно, нужные вычисления уже доступны во встроенном наборе. Команда Quantower постоянно работает над добавлением новых встроенных индикаторов. Если у вас есть идеи и предложения, что мы должны добавить - [смело пишите нам.](https://www.quantower.com/contact-us)

