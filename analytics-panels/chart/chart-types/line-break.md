# График линейного прорыва \(Line Break\)

## Общая информация о графике

**Line Break** очень похож на другие графики, не зависящие от времени, такие как Kagi, P&F, Range Bars. График с линейным разрывом печатает серию столбцов, которые представляют растущие и падающие цены. Ключевым параметром, участвующим в построении графика, является количество последних столбцов для построения текущего бара.

![&#x41E;&#x431;&#x449;&#x438;&#x439; &#x432;&#x438;&#x434; &#x413;&#x440;&#x430;&#x444;&#x438;&#x43A;&#x430; &#x43B;&#x438;&#x43D;&#x435;&#x439;&#x43D;&#x43E;&#x433;&#x43E; &#x43F;&#x440;&#x43E;&#x440;&#x44B;&#x432;&#x430; &#x432; Quantower](../../../.gitbook/assets/line-break-chart-general-view.png)

It is important to note that the bars on this chart are usually called "lines". Line Break based on closing prices so it takes the current price and compares it with the closing prices of the previous bars \(lines\). The number of the previous bars that participate in the calculation specified in the chart settings.

## Line Break calculation

The most common number of Line Break setting is 3. It means that the closing price of the current line is compared to the closing price of the third line ago.

![Chart settings for Line Break](../../../.gitbook/assets/line-break-settings.png)

Each new closing price has three possible outcomes:

* a new line with the same color  — build when the price goes in the same direction.
* a new line with the opposite color — build when the price change is enough to warrant a reversal. 
* no new lines are added when the price does not extend the trend or the change is not enough to warrant a reversal.

![An example of how to build a Line Break chart](../../../.gitbook/assets/line-break-example.png)

In the example above shows areas where the line color was changed. The yellow line shows the level of the third bar, when it breaks, the line color changes.

