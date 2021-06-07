---
description: Доступ к совокупным и неагрегированным коллекциям книги заказов.
---

# Level2 данные

## Теория

Книга заказов \(или level2\) - это набор заявок на покупку и продажу для определенных инструментов, организованных по уровню цен. У каждого уровня есть три важных значения - цена, размер и сторона. Эта коллекция динамична, то есть постоянно обновляется в реальном времени в течение дня.

Многие профессиональные трейдеры разрабатывают свои стратегии, используя данные книги заказов. Quantower API предоставляет пользователям простой способ получить агрегированные и неагрегированные снимки книги заказов. \*\* Чтобы использовать его, вам просто нужно выполнить метод GetDepthOfMarketAggregatedCollections и передать нужные вам параметры. Этот метод находится в классе «DepthOfMarket». У каждого инструмента есть свой объект DepthOfMarket.

#### Загрузки

Есть два метода загрузки

```csharp
public DepthOfMarketAggregatedCollections GetDepthOfMarketAggregatedCollections(GetLevel2ItemsParameters parameters = null)
```

Этот метод принимает объект [GetLevel2ItemsParameters](https://api.quantower.com/docs/TradingPlatform.BusinessLayer.GetLevel2ItemsParameters.html) со свойствами:

* \*\*\*\*[**AggregatedMethod**](https://api.quantower.com/docs/TradingPlatform.BusinessLayer.AggregateMethod.html) - перечисление, тип агрегирования \(по умолчанию «Уровень цен»\)
* **CustomTickSize** - шаг агрегирования \(не может быть меньше размера тика символа\)
* **LevelsCount** - количество необходимых уровней
* **CalculateCumulative** - установите значение true, если вам нужно кумулятивное значение для каждого уровня цен.

```csharp
public DepthOfMarketAggregatedCollections GetDepthOfMarketAggregatedCollections(GetDepthOfMarketParameters parameters)
```

This method takes the “[GetDepthOfMarketParameters](https://api.quantower.com/docs/TradingPlatform.BusinessLayer.GetDepthOfMarketParameters.html)”-object with properties:

* [**GetLevel2ItemsParameters**](https://api.quantower.com/docs/TradingPlatform.BusinessLayer.GetLevel2ItemsParameters.html) **-** the object described above.
* **CalculateImbalancePercent -** set ‘true’ if you need ‘imbalance’ value for each price level.

These methods return a ‘[DepthOfMarketAggregatedCollections](https://api.quantower.com/docs/TradingPlatform.BusinessLayer.DepthOfMarketAggregatedCollections.html)’ object with two lists - ‘Asks’ and ‘Bids’. Each collection contains instances of [‘Level2Item’](https://api.quantower.com/docs/TradingPlatform.BusinessLayer.Level2Item.html) class. There are our price levels.

## **Practice**

In this topic we will develop a simple indicator which will draw ‘Cumulative’ values as histogram.

![](../.gitbook/assets/level2_example.png)

### **Input parameters**

First, let’s define input parameters. We want to manage the number of levels and set custom tick size.

```csharp
[InputParameter("Level count", 10, 1, 9999, 1, 0)]
public int InputLevelsCount = 10;

[InputParameter("Custom tick size", 30, 0.0001, 9999, 0.0001, 4)]
public double InputCustomTicksize = 0.0001;
```

### **Class constructor**

Populate constructor of our class. Define name and add line series.

```csharp
Name = "Level2 cumulative";

AddLineSeries("Asks cumulative", Color.DarkRed, 10, LineStyle.Histogramm);
AddLineSeries("Bids cumulative", Color.DarkGreen, 10, LineStyle.Histogramm);

SeparateWindow = true;
```

### **OnInit method**

{% hint style="info" %}
Pay attention! In the ‘OnInit’ method we need to subscribe to the ‘NewLevel2’ event. This is necessary for the terminal to send a 'order book' subscription request to the vendor. The ‘Symbol\_NewLevel2Handler’ method we leave empty.
{% endhint %}

```csharp
protected override void OnInit()
{
     this.Symbol.NewLevel2 += Symbol_NewLevel2Handler;
}

private void Symbol_NewLevel2Handler(Symbol symbol, Level2Quote level2, DOMQuote dom)
{

}
```

### OnUpdate method

In the ‘OnUpdate’ method we skip the historical part and then get a level2 snapshot. Be sure to check that the ask/bid collections have values. Then we get the required levels and set ‘Cumulative’ values into our indicator buffers.

```csharp
protected override void OnUpdate(UpdateArgs args)
{
    // skip historical part
    if (args.Reason == UpdateReason.HistoricalBar)
       return;

    // get current 'order book' snapshot
    var dom = this.Symbol.DepthOfMarket.GetDepthOfMarketAggregatedCollections(new GetLevel2ItemsParameters()
    {
        AggregateMethod = AggregateMethod.ByPriceLVL,
        LevelsCount = this.InputLevelsCount,
        CalculateCumulative = true,
        CustomTickSize = this.InputCustomTicksize
    });

    if (dom.Asks.Length > 0)
       SetValue(dom.Asks.Last().Cumulative, 0);

    if (dom.Bids.Length > 0)
       SetValue(-dom.Bids.Last().Cumulative, 1);
}
```

### OnClear method

In the ‘OnClear’ don’t forget to unsubscribe from the ‘NewLevel2’.

```csharp
protected override void OnClear()
{
    this.Symbol.NewLevel2 -= Symbol_NewLevel2Handler;
}
```

