---
description: >-
  Менеджер поиска символов, позволяющий искать и выбирать любой доступный символ
  из активных соединений
---

# Менеджер торговых символов \(тикеров\)

Окно менеджера поиска символов - это специальный экран, позволяющий искать и выбирать любой доступный символ из активных соединений. В терминале Quantower есть различные поверхности, для которых требуется настроить параметр символа \(список наблюдения, диаграмма, информация о символах и т. д.\). В зависимости от требований, менджер поиска символов может позволять выбор одного или нескольких котировок.

При каждом коннекте к выбранному соединению, вы будете получать список всех доступных символов этого соединения на экране менеджера поиска символов. Поскольку Quantower допускает одновременно несколько подключений, у вас может быть в менеджере несколько похожих символов с данными, которые могут немного отличаться. Это нормально, потому что разные поставщики могут предоставить нам разные данные о котировках.

## Поле поиска

Окно поиска символов обычно вызывается из поля поиска. Это поле состоит из двух частей, которые позволяют открыть экран поиска:

* Торговый символ \(тикер\) с именем подключения
* Значок «**Поиск**» в виде трех вертикальных точек:

![](../.gitbook/assets/pole-poisk-simvolov.png)

Если вы нажмете на имя символа, вы увидите, что появится экран поиска и символы, введенные вами, будут применены в качестве фильтрации для списка символов..

Если вы щелкните значок «Поиск», вы увидите всплывающий экран поиска без какой-либо фильтрации, примененной к списку символов.

![&#x41E;&#x43A;&#x43D;&#x43E; &#x43F;&#x43E;&#x438;&#x441;&#x43A;&#x430; &#x438; &#x432;&#x44B;&#x431;&#x43E;&#x440;&#x430; &#x442;&#x43E;&#x440;&#x433;&#x43E;&#x432;&#x44B;&#x445; &#x441;&#x438;&#x43C;&#x432;&#x43E;&#x43B;&#x43E;&#x432; \(&#x442;&#x438;&#x43A;&#x435;&#x440;&#x43E;&#x432;\)](../.gitbook/assets/symbol-lookup-screen.png)

В любом случае вы получите экран поиска, готовый для выбора символа. Экран поиска состоит из трех элементов:

* Панель инструментов с полем поиска и фильтром
* Список подключений и их символы
* Нижний колонтитул

Для выхода нужно просто кликнуть в любом месте вне окна выбора.

## Поиск и фильтрация

Обычно каждое подключение дает вам на выбор многочисленный список торговых символов. Если вы знаете название торговой пары, вы можете начать вводить его в «Поле поиска», и нижеприведенный список будет мгновенно отфильтрован до элементов, содержащих введенную фразу.

![&#x424;&#x438;&#x43B;&#x44C;&#x442;&#x440;&#x430;&#x446;&#x438;&#x44F; &#x43F;&#x43E;&#x438;&#x441;&#x43A;&#x430; &#x441;&#x438;&#x43C;&#x432;&#x43E;&#x43B;&#x43E;&#x432;](../.gitbook/assets/lookupfiltered.png)

**Фильтр второго уровня.** Кстати, к списку можно применить более общую фильтрацию; просто щелкните значок «Фильтр» справа от поля поиска, и вы увидите второй уровень фильтрации символов.   
Второй уровень фильтрации добавляется при наличии двух и больше одновременных подключений.

![](../.gitbook/assets/filtr-vtorogo-urovnya.png)

Здесь вы сможете отфильтровать список по трем параметрам:

* Все подключения \(активные в настоящее время подключения\)
* Все типы \(FOREX, CFD, опционы и т. Д.\)
* Все биржи \(внебиржевой, NYSE, NASDAQ и т. Д.\)

После выбора некоторых элементов среди параметров фильтрации список фильтруется только по выбранным значениям.

{% hint style="warning" %}
Внимание\(!\) В то время как поле поиска сбрасывается при каждом вызове экрана поиска, фильтры второго уровня остаются такими, как они были настроены в прошлый раз. Поэтому, если вы не можете найти нужный тип символа - проверьте, включен ли у вас этот тип.
{% endhint %}

## Symbols list

The list of symbols is a result of filtering in Lookup screen. Here you can see the nested tree of Symbols, grouped in the following order:

* Connection
* Exchange
* Type
* Subtypes

The Symbol types are marked with additional icons to help you identify the required one more quickly. The Symbol item row consists of Name and description.

To select the Symbol — click on it; to apply the symbol to the required panel, just double-click on it. This action closes the Lookup screen

## Multiple symbols select

In some cases, when panel can accept more than one Symbol item from lookup \(like the Watchlist\), you have an ability to select multiple items by holding the "_**Ctrl key**_" and clicking on the list. Once you ready to apply multiple items — press the "_**blue circle icon**_" on the right bottom corner of the list. You may also select any category level item to apply all its contents to the required panel.

![Multiple Symbols select](../.gitbook/assets/lookupmultiple.png)

## List footer

To help you deal with the big lists of Symbols, there is a footer toolbar with a set of mass actions. It allows to:

* Collapse all nodes
* Expand head nodes \(top-level nodes, usually Connections\)
* Expand first-level child nodes

![Managing of multiple nodes in the Lookup Screen](../.gitbook/assets/collapsing.gif)

The other useful information is placed on the right side of footer toolbar — items count. It may show the total amount of available Symbols \(after the filtering was applied\) as well as 3/235 \(3 from 235\) value, saying that you have selected multiple items among available.

