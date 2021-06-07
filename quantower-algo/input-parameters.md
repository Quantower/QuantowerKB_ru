---
description: >-
  Измените поведение индикаторов или стратегий с помощью набора входящих
  параметров.
---

# Входящие параметры

## Общее

В предыдущем разделе мы показали вам, как создать базовый индикатор с помощью Visual Studio с расширением Quantower Algo и использовать его на графике в торговой платформе. Мы создали индикатор Simple Moving Average с жестко запрограммированными параметрами. Но что, если нам нужно изменить эти параметры? Например, мы хотим использовать цены открытия вместо цен закрытия или использовать другой период. Перекомпилировать индикатор каждый раз не очень удобно, и мы предоставляем вам возможность легкой настройки ваших скриптов с помощью так называемых входных параметров.

## Что такое входящий параметр?

После добавления индикатора на график вы можете найти на нем пункт меню «Настройка», отображающий окно «Настройки». Индикаторы обычно имеют некоторые общие настройки для настройки линий и определенные настройки, связанные с их алгоритмом или расчетами.

Вы можете создать любое количество входных параметров, необходимых в ваших скриптах. Их можно использовать как для индикаторов, так и для стратегий.

С технической точки зрения Входной параметр - это обычная переменная, отмеченная специальным атрибутом. На данный момент мы поддерживаем основные базовые типы: строка, число, дата, время, счет, символ, список опций и другие.

Мы подробно покажем, как объявлять каждый тип входных параметров и как их настраивать.

## Типы входящих параметров

### Текст

Иногда может потребоваться, чтобы пользователь предоставил некоторую текстовую информацию, например, для отображения на графике. Для этого вам нужно объявить строковую переменную и пометить ее как **InputAttribute.** Вам необходимо указать имя входного параметра, которое будет отображаться на экране настроек:

```csharp
[InputParameter("Text")]
public string text;
```

Если вы вызовете экран настроек, вы увидите текстовое поле, которое вы можете использовать для ввода значения. Вот и все - ваш первый входной параметр готов:

![&#x41F;&#x440;&#x438;&#x43C;&#x435;&#x440; &#x43F;&#x430;&#x440;&#x430;&#x43C;&#x435;&#x442;&#x440;&#x430; &#x432;&#x432;&#x43E;&#x434;&#x430; &#x442;&#x435;&#x43A;&#x441;&#x442;&#x430; &#x43D;&#x430; &#x44D;&#x43A;&#x440;&#x430;&#x43D;&#x435; &#x438;&#x43D;&#x434;&#x438;&#x43A;&#x430;&#x442;&#x43E;&#x440;&#x430; &#xAB;&#x41D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x438;&#xBB;](../.gitbook/assets/text_example%20%281%29.png)

Если у вас есть несколько входящих параметров и вы хотите расположить их в соответствующем порядке, вы можете применить параметр SortIndex для каждого Входящего параметра:

```csharp
[InputParameter("First text", 1)]
public string firstText;

[InputParameter("Second text", 2)]
public string secondText;

[InputParameter("Third text", 3)]
public string thirdText;
```

Как видите, параметры отображаются в указанном порядке:

![&#x41E;&#x442;&#x441;&#x43E;&#x440;&#x442;&#x438;&#x440;&#x43E;&#x432;&#x430;&#x43D;&#x43D;&#x44B;&#x435; &#x432;&#x445;&#x43E;&#x434;&#x44F;&#x449;&#x438;&#x435; &#x43F;&#x430;&#x440;&#x430;&#x43C;&#x435;&#x442;&#x440;&#x44B;](../.gitbook/assets/few-text_example.png)

### **Boolean**

In case you need a simple switcher, for example, to enable an option, you can use bool variable with an InputParameter attribute:

```csharp
[InputParameter("Boolean")]
public bool boolean;
```

### **Number**

One of the most important types of input parameters is numbers. Input parameters can be applied to **int**, **double**, **long** and **decimal** variables:

```csharp
[InputParameter("Integer")]
public int intNumber;
```

You can specify additional parameters - minimum/maximum value, increment, and decimal places.

```csharp
[InputParameter("Double", 0, 0.00001, 10, 0.00001, 5)]
public double doubleNumber;
```

### **Symbol**

Sometimes you may need possibility so select symbol, for example in case of calculation of correlation between symbol from the chart and another symbol. And again - all you need just declare variable and mark in with **InputParameter** attribute:

```csharp
[InputParameter("Symbol")]
public Symbol symbol;
```

### **Account**

If your script is executing some trading operation you need to provide an account setting. Use a variable of **Account** type for this:

```csharp
[InputParameter("Account")]
public Account account;
```

### **DateTime**

Usually, DateTime settings are using to specify some range of history, for example, left and right border of downloaded history:

```csharp
[InputParameter("Date")]
public DateTime dateTime;
```

### **Color**

Color Input Parameters store color value in an RGB format:

```csharp
[InputParameter("Color")]
public Color color;
```

### **List with options**

List with options Input parameter allows to select the value from the predefined list of possible states

```csharp
[InputParameter("Simple price types list", 1, variants: new object[]{
    "Close", PriceType.Close,
    "Open", PriceType.Open,
    "High", PriceType.High,
    "Low", PriceType.Low,
    "Typical", PriceType.Typical,
    "Median", PriceType.Median,
    "Weighted", PriceType.Weighted
})]
```

## Conclusion

To summarize all said above, we gathered all types of Input Parameters to show you how they can look in settings screen:

![All type of Input Parameters](../.gitbook/assets/all-input.png)

These basic types of Input parameters are enough to create complex indicators and strategies with a wide list of settings. Despite this, we are constantly adding new Input Parameter types. Feel free to contact us and propose your variants — we are open to our users' feedback.

