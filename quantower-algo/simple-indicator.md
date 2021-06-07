---
description: 'В этом разделе мы покажем вам, насколько просто писать индикаторы в Quantower.'
---

# Простой индикатор

{% hint style="info" %}
Мы будем использовать расширение Quantower Algo для Visual Studio, но основные принципы действительны для всех сред разработки. Если у вас не установлено расширение Visual Studio или Quantower Algo, вы можете прочитать руководство [**Как установить Quantower Algo.**](https://app.gitbook.com/@quantower/s/quantower-ru/~/drafts/-Mb_LzyI38AnKls7m3Ia/quantower-algo/installing-visual-studio)\*\*\*\*

Смотрите примеры некоторых стратегий, интеграций и индикаторов в нашем [**репозитории Github.**](https://github.com/Quantower/Examples)\*\*\*\*
{% endhint %}

## Итак, что такое индикатор в целом?

Индикатор  - это математические вычисления, основанные на цене или объеме финансового инструмента. Результат используется для отображения на графике и помогает трейдеру принять правильное решение. С технической точки зрения индикатор в Quantower представляет собой набор линий с буферами. Каждому элементу буфера присваивается исторический бар или тик на графике. Все, что вам нужно, это произвести необходимые вычисления и поместить результат в этот буфер.

Звучит не очень сложно, правда? Давайте начнем! Например, напишем код, который будет реализовывать алгоритм индикатора Simple Moving Average.

Используйте _**«Файл -&gt; Новый проект»**_ в главном меню Visual Studio, чтобы открыть окно «Новый проект». Наберите «Индикатор», и вы увидите специальный тип проекта для пустого индикатора:

Для начала нужно создать новый проект индикатора. Quantower Algo предоставляет вам предопределенные шаблоны для пустого индикатора, а также несколько примеров реальных индикаторов с исходным кодом:

![](../.gitbook/assets/sozdat-proekt.jpg)



![](../.gitbook/assets/prostoi-indikator.png)

![](../.gitbook/assets/prostoi-indikator-shag2.png)

Минимально необходимый исходный код будет сгенерирован автоматически и содержит основные функции индикатора:

![&#x418;&#x441;&#x445;&#x43E;&#x434;&#x43D;&#x44B;&#x439; &#x43A;&#x43E;&#x434; &#x43F;&#x43E; &#x443;&#x43C;&#x43E;&#x43B;&#x447;&#x430;&#x43D;&#x438;&#x44E; &#x434;&#x43B;&#x44F; &#x43F;&#x443;&#x441;&#x442;&#x43E;&#x433;&#x43E; &#x438;&#x43D;&#x434;&#x438;&#x43A;&#x430;&#x442;&#x43E;&#x440;&#x430;](../.gitbook/assets/default-code.png)

## Структура кода индикатора

### Общие настройки

Пора углубиться в код. В методе конструктора вы можете указать имя индикатора, краткое имя для отображения на графиках и необходимость отдельного окна на графике для вашего индикатора. Наиболее важным здесь является указание количества линий и их стиля по умолчанию: Solid / Dot / Histogram, цвета и ширины. В нашем примере нам нужна всего одна строка, но вы можете добавить любую сумму:

```csharp
/// <summary>
/// Indicator's constructor. Contains general information: name, description, LineSeries etc. 
/// </summary>
public SimpleIndicator()
    : base()
{
    // Defines indicator's name and description.
    Name = "SimpleIndicator";
    Description = "My indicator's annotation";

    // Defines line on demand with particular parameters.
    AddLineSeries("line1", Color.CadetBlue, 1, LineStyle.Solid);

    // By default indicator will be applied on main window of the chart
    SeparateWindow = false;
}
```

### Получение данных

Метод «OnUpdate» будет вызываться каждый раз при изменении истории - здесь нам нужно добавить свои расчеты. Большинство индикаторов используют в своих алгоритмах цены или объемы. Quantower API предоставляет вам несколько способов получить эти данные - вы можете получить доступ к данным открытия, максимума, минимума, закрытия и других данных из текущего бара или из предыдущих столбцов, если это необходимо.

Общий метод [**GetPrice**](http://api.quantower.com/docs/TradingPlatform.BusinessLayer.Indicator.html#TradingPlatform_BusinessLayer_Indicator_GetPrice_TradingPlatform_BusinessLayer_PriceType_System_Int32_) позволяет получить все типы данных:

```csharp
// To get Low price of the current bar
double low = GetPrice(PriceType.Low);
// To get Volume price for the fifth bar before the current
double volume = GetPrice(PriceType.Volume, 5);
```

And a few simplified ways to retrieve the data:

```csharp
// To get Close price of the current bar
double close = Close();
// To get High price of the current bar
double high = High();
// To get Open price for the fifth bar before the current
double open = Open(5);
```

You can find more information about "**Indicator"** class in our [API documentation](http://api.quantower.com).

### Setting data

Now we know how to get prices, but as we told before, we need also to put results into indicator buffer. We can use "[**SetValue**](http://api.quantower.com/docs/TradingPlatform.BusinessLayer.Indicator.html#TradingPlatform_BusinessLayer_Indicator_SetValue_System_Double_System_Int32_System_Int32_)**"** method for this:

```csharp
// Put value into current bar for first line of indicator
SetValue(1.43);
// Put value into current bar for second line of indicator
SetValue(1.43, 1);
// Put value into fifth bar before the current bar for second line of indicator
SetValue(1.43, 1, 5);
```

All this is enough to finish our first indicator. Let's add calculations into "**OnUpdate"** method using standard C\# possibilities. This is our total code:

```csharp
/// <summary>
/// Calculation entry point. This function is called when a price data updates. 
/// </summary>
protected override void OnUpdate(UpdateArgs args)
{
    int Period = 10;

    // Checking, if current amount of bars
    // more, than period of moving average. If it is true
    // then the calculation is possible
    if (Count <= Period)
        return;

    double sum = 0.0; // Sum of prices
    for (int i = 0; i < Period; i++)
        // Adding bar's price to the sum
        sum += GetPrice(PriceType.Close, i);

    // Set value to the "SMA" line buffer.
    SetValue(sum / Period);
}
```

As you can see, we use only Close prices for calculations and hard code Period value. In the real case, you will allow a user to specify this values. In our next topic, we will show how to use the Input Parameter for your scripts.

### Build

Indicator is ready to use in trading platform. We need to compile it - use "_**Build -&gt; Build Solution**_" in the main menu or hot key **F6**. Quantower Algo extension will automatically copy your indicator to assigned Quantower trading platform and you will see it in the "Indicators" lookup on the chart:

![You can see your indicator in Indicator Lookup](../.gitbook/assets/indicator-in-lookup.png)

If you decide to make some corrections in your calculations, you can rebuild your indicator and you even don't need to re-add it again on the chart - it will be updated automatically and you will see results immediately:

![You will see all your changes right after rebuild](../.gitbook/assets/indicator-after-changes.png)

As you can see it did not take a lot of time to get the first results. Using this basic example you can easily create your own indicator — all power of C\# language is available for you. In the next topic we will show you how to add possibility of [customizing of your indicator via Input Parameters](input-parameters.md).

