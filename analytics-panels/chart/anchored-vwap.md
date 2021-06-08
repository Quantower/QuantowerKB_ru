---
description: >-
  Привязанный инструмент VWAP или пользовательский VWAP позволяет рисовать линию
  VWAP в указанном диапазоне или от указанной начальной точки.
---

# Привязанный VWAP

Укажите начальную точку на графике, и привязанный VWAP проведет линию к текущему моменту. Также вы можете указать конечную точку для линии, установить стандартное отклонение и максимально допустимое отклонение.

![](../../.gitbook/assets/anchored-vwap.gif)

Нажав на значок «Шестеренка», вы можете настроить параметры выбранного VWAP.

![&#x41D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x430; &#x43F;&#x430;&#x440;&#x430;&#x43C;&#x435;&#x442;&#x440;&#x43E;&#x432; &#x432;&#x44B;&#x431;&#x440;&#x430;&#x43D;&#x43D;&#x43E;&#x433;&#x43E; VWAP.](../../.gitbook/assets/polzovatelskii-vwap.jpg)

* **Линия VWAP** - установите тип основной линии, ее толщину и цвет.
* **Тип данных** - установите данные для расчета VWAP: Ticks или Current TF. Тики будут использовать тиковые данные для расчета VWAP, и загрузка займет гораздо больше времени. Текущий TF будет использовать данные бара из текущего выбранного таймфрейма вашего графика. Он будет использовать данные типа цены и умножить их на объем бара.
* **Тип цены** - выберите цену для текущего типа данных TF \(Open, High, Low, Close, HL / 2, HLC / 3, OHLC / 4\)

![](../../.gitbook/assets/polzovatelskie-vwap-nastroiki.png)

* **Standard Deviation Bands**. When the parameter is active, the standard deviation lines up and down from VWAP will be additionally calculated on the chart. Specify the number of standard deviations in the _**"Value"**_ field and colors
* **Maximum Permissible Deviation \(MPD\).** MPD is similar to the standard deviation but is calculated as \(VWAP period high - VWAP period low\)/2.
* **Points coordinates** — defines the starting point for custom VWAP
* **Visible on specified timeframes** — this setting allows you to specify on which timeframes VWAP will be displayed.
* **Полосы стандартного отклонения**. Когда параметр активен, линии стандартного отклонения вверх и вниз от VWAP будут дополнительно рассчитаны на графике. В поле **«Значение»** укажите количество стандартных отклонений и цвета.
* **Максимально допустимое отклонение \(МДО\).** **МДО** аналогичен стандартному отклонению, но рассчитывается как \(максимум периода VWAP - минимум периода VWAP\) / 2.
* Координаты точек - определяет начальную точку для пользовательского VWAP.

  Виден на указанных таймфреймах - этот параметр позволяет указать, на каких таймфреймах будет отображаться VWAP.

