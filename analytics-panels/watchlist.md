---
description: >-
  На панели списка наблюдения отображается краткая информация о ценах на
  выбранные инструменты, которые вы можете сгруппировать в списки.
---

# Список наблюдения

Панель Watchlist - это стандартная табличная панель, представляющая различную торговую информацию для указанного списка символов. Список символов можно настроить с помощью экрана поиска символов, доступного при нажатии кнопки \[+\] на панели инструментов, или из контекстного меню таблицы - опция «Добавить символы».

![&#x421;&#x43B;&#x435;&#x434;&#x438;&#x442;&#x435; &#x437;&#x430; &#x438;&#x43D;&#x444;&#x43E;&#x440;&#x43C;&#x430;&#x446;&#x438;&#x435;&#x439; &#x43E; &#x43D;&#x435;&#x43E;&#x431;&#x445;&#x43E;&#x434;&#x438;&#x43C;&#x43E;&#x43C; &#x441;&#x438;&#x43C;&#x432;&#x43E;&#x43B;&#x435; &#x441; &#x43F;&#x43E;&#x43C;&#x43E;&#x449;&#x44C;&#x44E; &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438; &#x441;&#x43F;&#x438;&#x441;&#x43A;&#x430; &#x43D;&#x430;&#x431;&#x43B;&#x44E;&#x434;&#x435;&#x43D;&#x438;&#x44F;](../.gitbook/assets/watchlist-general-view.gif)

Каждый символ, добавленный в список наблюдения, можно удалить через контекстное меню в строке символа. Вы также можете очистить весь список через контекстное меню.

{% hint style="warning" %}
Когда вы добавляете символ, который уже присутствует в текущем списке, он будет добавлен в конец списка, создавая дубликаты.
{% endhint %}

## Управление столбцами

## Избранные списки

Вы можете захотеть сохранить несколько списков для панели Watchlist. Чтобы сохранить какой-либо список в качестве избранного, вы можете использовать кнопку \[Сохраненные списки\] на панели инструментов. Если у вас еще нет сохраненных списков, откроется всплывающее окно «Сохранить текущий список», где вы можете указать имя для сохраняемого списка.

![](../.gitbook/assets/spisok-svoi-.gif)

Once you press the **\[ SAVE \]** button, the new list will be added to the Favorites and became available from the _**“Saved lists”**_ drop-down on the toolbar.

![Favorite lists drop-down](../.gitbook/assets/lists-in-the-watchlist.png)

Using the _**“Favorite lists”**_ drop-down, you can manage the current saved lists \(edit name, remove\) and initiate the current list save.

{% hint style="info" %}
Please notice. When you click on any of favorite lists it will be added below the current list. If you want to see the selected list only, you should clear the Watchlist first.
{% endhint %}

## Indicators

The Watchlist panel supports the indicators value display in separate columns. In order to add some indicator, thare are two ways to to it:

* right-click on watchlist table and proceed to _**"Indicators" -&gt; "Add indicator"**_ option. This opens an indicators lookup screen, where you should select the required one.

![Indicators in watchlist are very useful](../.gitbook/assets/indicators-watchlist-first-way.png)

* through the icon _**"Add indicator"**_ in the upper right corner of the Watchlist panel

![There are two ways to add indicators in the panel](../.gitbook/assets/indicators-watchlist-second-way.png)

When you select an indicator, you will see the new column \(with the selected indicator name\) added to the right side of watchlist table. To remove indicator, go to the Indicators category in the context menu and click the _**“Remove Indicator Name”**_ option.

{% hint style="info" %}
Some indicators need time to calculate their values. You will see the “Initializing...” text in such cells.
{% endhint %}

If you have created \(or added\) a custom indicator in the platform and want to add it to the Watchlist panel, you need to add an additional parameter to the code. More information about how to do this is given in our guide "[**Adding a custom indicator to Watchlist**](../quantower-algo/custom-indicator-to-watchlist.md)".

