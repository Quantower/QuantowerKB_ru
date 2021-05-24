---
description: >-
  Узнайте, как добавлять или удалять столбцы в таблице, сортировать и
  фильтровать данные, устанавливать предупреждения и действия.
---

# Управление таблицами

## Табличные панели

Табличные панели представлены как отдельный класс - все они имеют не менее 99% функциональности в зависимости от вида таблицы. Мы используем общий компонент таблицы для всех этих панелей, поэтому поведение и функции в основном одинаковы.

![&#x41F;&#x440;&#x438;&#x43C;&#x435;&#x440; &#x442;&#x430;&#x431;&#x43B;&#x438;&#x447;&#x43D;&#x44B;&#x445; &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x435;&#x439;](../.gitbook/assets/tablepanels.png)

Некоторые табличные панели имеют специальную панель инструментов, которую можно использовать для массовой фильтрации или быстрых действий. Другие панели таблиц могут не иметь заголовков столбцов, потому что они действительно не нужны для понимания данных, поэтому были скрыты для экономии места; это отключает возможность фильтрации данных столбца на таких панелях.

## Управление столбцами

Данные в таблицах организованы в строки и столбцы, где параметры каждого элемента \(строки\) отображаются в столбцах. Не все доступные столбцы по умолчанию отображаются на каждой панели таблицы. Мы выбрали наиболее популярные и важные для каждой панели и сделали возможность изменять набор столбцов по своему усмотрению.

![](../.gitbook/assets/kolonki-po-umolchaniyu.jpg)

Щелкните правой кнопкой мыши заголовок любого столбца, чтобы увидеть контекстное меню «Набор столбцов». Затем щелкните любой элемент в этом меню, чтобы изменить видимость столбца. Минимум в таблице должен остаться 1 столбец; последний видимый столбец нельзя будет скрыть.

Другие полезные функции управления столбцами - это сортировка и изменение размера. Каждый столбец можно перетаскивать за заголовок между другими столбцами внутри таблицы, чтобы задать требуемую последовательность. Вы также можете перетащить вертикальные границы между двумя столбцами, чтобы изменить их размер.

## Фильтрация

Набор строк в таблице можно отфильтровать по некоторому значению данных в их столбце. Есть два способа применить фильтрацию:

* Быстрый фильтр таблицы
* Расширенный фильтр таблицы

{% hint style="success" %}
Быстрый фильтр таблицы - это еще одна точка доступа к расширенной опции фильтрации, позволяющей применять простые фильтры в несколько кликов.
{% endhint %}

Доступ к быстрому фильтру таблицы можно получить, щелкнув значок «Фильтр» в заголовке любого столбца таблицы.

![&#x411;&#x44B;&#x441;&#x442;&#x440;&#x430;&#x44F; &#x444;&#x438;&#x43B;&#x44C;&#x442;&#x440;&#x430;&#x446;&#x438;&#x44F; &#x43F;&#x43E; &#x441;&#x442;&#x43E;&#x43B;&#x431;&#x446;&#x443;](../.gitbook/assets/dopolnitelnye-filtry.png)

Depending on the data type in a column, the Quick filter will give you the corresponding form for input; currently “_**String**_”, “_**Date/time**_” & “_**Number**_” filtering are supported. Once you select some option — the table rows will be filtered to that ones, containing the selected value. Quick filter can be cancelled by pressing “_**Cancel filtering**_” option.

## Sorting

Each table can be sorted by column value. To sort the table, click on column’s header; you will see a “_**Sorting**_” icon appears. The next click on this header will revert the sorting by this column. You can sort your table only by one column simultaneously.

## Grouping

If you want to organize your rows more precisely, you can use a “_**Rows grouping**_” feature. It allows separating all table items in groups, made from data of some column. Currently, only “_**String**_” data columns are supported for grouping.

![Table grouped by &#x201C;Side&#x201D; value](../.gitbook/assets/tablegrouping.png)

To apply the grouping just right-click on the table body and find an option “_**Group by**_”; the second-level of context menu will contain all of available columns that can be grouped by. You can group by one column only. To cancel grouping — follow the previous steps and uncheck the column.

