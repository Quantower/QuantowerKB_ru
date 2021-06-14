# Ввод ордера для CQG

Общий вид панели ввода заказов для подключения CQG выглядит следующим образом и разделен на следующие категории:

* Выбор счета и символа
* Направление ордера и его количество
* Параметры ордера - тип, TIF, цена, алгоритмические настройки
* Режим для стоп-лосса и тейк-профита. Мульти-кронштейны
* Стратегии размещения заказов

![](../../.gitbook/assets/vvod-ordera-cqg.png)

## CQG OrderTypes, Time in Force \(TIF\), Algorithmic in Quantower

CQG provides various order types for trading via the Order Entry panel:

* Market order
* Limit order
* Stop order
* Stop limit order

![Order types in Quantower for CQG connection](../../.gitbook/assets/image%20%28218%29.png)

**Time-in-force \(TIF\)** instructions define the length of time over which an order will continue working before it is canceled. CQG provides various TIFs:

![Time in Force \(TIFs\) for CQG connection](../../.gitbook/assets/image%20%28217%29.png)

* **GTC \(Good till canceled\)** — orders will remain working until they are canceled by trader or the contract expires;
* **FOK \(or Fill or Kill\)** —  order will be canceled if it is not executed in the entire volume as soon as it becomes available;
* **IOC \(Immediate or cancel\)** — requires that any portion of an order that is not filled as soon as it becomes available in the market is canceled;
* **DAY** — order will be canceled if it is not executed within the current trading day;
* **GTD \(Good till date\)** — order will remain working within the system and in the marketplace, until it executes or until the close of the market on the date specified.
* **GTT \(Good till time\)** — order that remains open until a specified time. At that time, any unfilled lots are canceled.
* **FAK** \(**Fill and Kill\)** — _\*\*_orders require that any remaining quantity after a partial fill be canceled.
* **ATC \(At the Close Order\)** — order to buy or sell a stock at the closing price. One of the benefits of this type of order is that it can be placed prior to the actual end of the trading day requested. This would be the opposite of an at-the-open order.
* **ATO \(At-The-Open Order\)** — order to buy or sell a stock at the opening price. ATO order is allowed during pre-open sessions \(morning and afternoon\) or even the night before.

