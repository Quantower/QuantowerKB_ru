---
description: >-
  Менеджер настройки фильтров и уведомлений позволяет вам настроить определенное
  поведение при изменении некоторых данных в таблице.
---

# Менеджер фильтров и уведомлений

Этот менеджер настройки позволяет вам установить определенное поведение при изменении некоторых данных в таблице. Эта функция доступна в панелях:

* [**Watchlist**](../analytics-panels/watchlist.md)
* [**Time & Sales**](../analytics-panels/time-and-sales.md#setup-actions-filters-and-actions)
* [**Price Statistic**](../analytics-panels/price-statistic.md)
* [**Working Orders**](../portfolio-panels/working-orders.md)
* [**Positions**](../portfolio-panels/positions.md)
* [**Trades**](../portfolio-panels/trades.md)
* [**Orders History**](../portfolio-panels/orders-history.md)

![](../.gitbook/assets/filtry-i-alerty.jpg)

Действия настройки состоят из двух вариантов:

1. **Фильтры** - где вы можете настроить фильтры для разных столбцов
2. **Действия** \(уведомления\)— где вы можете настроить несколько действий на основе данных в строках и столбцах.

## Действия

 В настоящее время таблицы Quantower поддерживают четыре типа действий:

* Показать сообщение
* Воспроизвести звук
* Цветовой ряд
* Цвет ячейки

Функциональность действий таблицы можно найти в пункте контекстного меню панели «Настроить действия», и после запуска он открывает «экран действий», где вы можете управлять своими действиями. Процесс создания Действия не сложен.

1. Создать элемент действия
2. Установите условия \(«ИЛИ» и «И»\)
3. Установить задачи \(Показать сообщение, Воспроизвести звук, Цветная строка, Цветная ячейка\)
4. Сохранить действие
5. Включить действие

### Задачи выполняемые в действии 

Как только какое-то условие выполнено, действие выполнит соответствующие задачи. Каждая задача будет выполняться столько раз, сколько было указано в условии.

| Показать сообщение | Отображает всплывающее окно с указанным пользователем сообщением |
| :--- | :--- |
| Воспроизвести звук | Воспроизводит выбранный пользователем звуковой файл |
| Цветовой ряд | Изменяет стиль всей строки, в которой выполнено условие. Позволяет изменить цвет фона и / или текста. |
| Цвет ячейки | Изменяет стиль указанной ячейки \(ячеек\) строки, в которой было выполнено условие. Позволяет изменить цвет фона и / или текста. |

{% hint style="warning" %}
Будьте осторожны с часто встречающимися условиями. Некоторые из них могут выполняться несколько раз в секунду, поэтому такие задачи, как «Воспроизвести звук», могут вызывать беспокойство. Задание «Показать сообщение», запущенное несколько раз, будет отображаться в виде одного окна сообщения.
{% endhint %}

## Табличные фильтры

Строки в таблице можно фильтровать по некоторым значениям данных в их столбце. Есть два способа применить фильтрацию:

* Доступ к быстрой фильтрации можно получить, щелкнув значок «Фильтр» в заголовке любого столбца таблицы.

![Quick filtering per column](https://gblobscdn.gitbook.com/assets%2F-LD6FsRvQ3jgwJIg6O7r%2F-LSZlUr_Myk0rKIIPYb3%2F-LSZtsdnR8ZXyAorsvkj%2FQuick%20filtering.png?alt=media&token=ccff8243-c69e-427c-8825-00c8ce9e1818)

Once you select some option — the table rows will be filtered to those ones, containing the selected value. Quick filter can be canceled by pressing “_**Cancel filtering**_” option.

Quick filtering can be applied only to one column of the table. For filtering multiple columns, we recommend using “_**Setup actions**_”.

* **Advanced filtering,** for applying more complex filtering \(multi-filtering\). Select in the panel's context menu option “_**Setup actions**_”.

![](https://gblobscdn.gitbook.com/assets%2F-LD6FsRvQ3jgwJIg6O7r%2F-LvGYANuFTIQuOZAz6LM%2F-LvGfvw940y4eFZGgYt6%2Fsetup%20actions%20ts.png?alt=media&token=c7a2a5f1-ab62-49c9-b5a9-8f4753f51bbe)

This screen has two tabs on the left side, where the first one is an Advanced filter.

![Advanced filtering in Time &amp; Sales panel](https://gblobscdn.gitbook.com/assets%2F-LD6FsRvQ3jgwJIg6O7r%2F-LSZlUr_Myk0rKIIPYb3%2F-LS_5SP-opC1CiDG-iws%2Fadvanced%20filtering.png?alt=media&token=e2d74d74-7ee5-4533-ae11-09d4db0ab09c)

This screen allows you to Enable/disable filtering as well as set up filtering Conditions. These conditions are set up as:

$$
IF (condition1AND condition2 ...) OR (conditionN...) …
$$

You can setup as many conditions as you like. Due to the possible complex logic of filtering, you are required to apply the changes once you finished the filter set up.

