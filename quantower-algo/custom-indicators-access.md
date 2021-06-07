---
description: Создайте экземпляр пользовательского индикатора с входными параметрами.
---

# Доступ к пользовательским индикаторам

## Общее

Quantower API предоставляет огромную коллекцию встроенных индикаторов. Но иногда нам нужно использовать собственный индикатор, который мы разработали ранее или скачали из Интернета.

В этой статье мы создадим экземпляр пользовательского индикатора и по-разному передадим входные параметры.

Ниже вы можете увидеть код пользовательского индикатора. Представим, что это очень полезный скрипт и что мы хотим использовать результаты его вычислений в нашем коде. Но нас не устраивают входные параметры по умолчанию, поэтому мы хотим их изменить.

```csharp
public class CustomIndicator : Indicator
{
    [InputParameter("Level", 10, 0.1, 9999, 0.1, 1)]
    public double LevelValue = 10;

    [InputParameter("Slow period", 20, 1, 9999, 1, 0)]
    public int SlowPeriod = 30;

    [InputParameter("Price type", variants: new object[]
    {
        "Close", PriceType.Close,
        "Open", PriceType.Open,
        "High", PriceType.High,
        "Low", PriceType.Low,
    })]
    public PriceType PriceType = PriceType.Close;

    [InputParameter("Period")]
    public Period Period = Period.MIN1;

    //
    // Parameterless constructor
    //
    public CustomIndicator()
    {
        this.Name = "Custom indicator";
        this.AddLineSeries("Line", Color.DodgerBlue, 2, LineStyle.Solid);

        this.SeparateWindow = true;
    }

    protected override void OnUpdate(UpdateArgs args)
    {
        // something usefull
    }
}
```

## Использовать конструктор класса \(новичок\)

Самый простой способ создать и передать параметры - использовать конструктор класса. На данный момент в нашем пользовательском индикаторе есть конструктор, который не принимает параметров \(конструктор без параметров\). Такой конструктор должен быть у каждого индикатора.

Давайте добавим новый конструктор для класса CustomIndicator, в котором мы переопределим входные параметры по умолчанию.

```csharp
public class CustomIndicator : Indicator
{
    // ...

    //
    // Parameterless constructor
    //
    public CustomIndicator()
    {
        this.Name = "Custom indicator";
        this.AddLineSeries("Line", Color.DodgerBlue, 2, LineStyle.Solid);

        this.SeparateWindow = true;
    }

    //
    // New constructor with parameters
    //
    public CustomIndicator(double levelValue, int slowPeriod, PriceType priceType, Period period)
         : this() // Don't forget to invoke parameterless constructor
    {
        this.LevelValue = levelValue;
        this.SlowPeriod = slowPeriod;
        this.PriceType = priceType;
        this.Period = period;
    }

    // ...
}
```

Теперь в других индикаторах мы можем использовать этот конструктор вместо конструктора по умолчанию. Например, в методе «OnInit».

```csharp
class BestIndicator : Indicator
{       
    private Indicator customIndicator;

    protected override void OnInit()
    {
        this.customIndicator = new CustomIndicator(10, 500, PriceType.High, Period.DAY1);
        this.AddIndicator(this.customIndicator);
    }

    protected override void OnUpdate()
    {
        var indicatorValue = this.customIndicator.GetValue();

        // something usefull
    }
}
```

## Использовать сборник настроек индикатора \(заранее\)

Этот метод можно использовать, если вы не можете добавить требуемый конструктор. Например, вы импортировали dll-библиотеку с индикатором. У каждого индикатора есть свойство «Настройки», которое содержит все входные параметры, преобразованные в объекты типа «SettignItem».

Чтобы изменить любой из параметров, необходимо вызвать метод UpdateItemValue и передать имя необходимого параметра и новое значение.

```csharp
class BestIndicator : Indicator
{       
    private Indicator customIndicator;

    //    
    protected override void OnInit()
    {
        var customIndicator = new CustomIndicator();
        var settings = customIndicator.Settings;

        try
        {
            settings.UpdateItemValue("Level", 12.5);
            settings.UpdateItemValue("Slow period", 55);
            settings.UpdateItemValue("Price type", new SelectItem("Open", PriceType.Open));
            settings.UpdateItemValue("Period", Period.MONTH1);

            this.AddIndicator(this.customIndicator);
        }
        catch (Exception ex)
        {
            // log exception
        }

        indicator.Settings = settings;
    }

    // 
    protected override void OnUpdate()
    {
        var indicatorValue = customIndicator.GetValue();

        // something usefull
    }
}
```

