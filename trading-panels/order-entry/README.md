---
description: >-
  Ввод ордеров позволяет создавать торговые ордера с различными условиями,
  такими как количество ордеров, цена, сторона, тип ордера, и отправлять их на
  рынок.
---

# Ввод ордера

* \*\*\*\*[**Общая информация**](./#obshaya-informaciya)\*\*\*\*
* \*\*\*\*[**Как открыть панель ввода заказов?**](./#kak-otkryt-panel-vvoda-zakazov)\*\*\*\*
* \*\*\*\*[**Выбор символа и счета**](./#vybor-simvola-i-scheta)\*\*\*\*
* \*\*\*\*[**Типы заказов и ограничения**](./#tipy-zakazov-i-ogranicheniya)\*\*\*\*
* \*\*\*\*[**Защита ордера**](./#zashita-ordera)\*\*\*\*
* \*\*\*\*[**Подтверждение заказа**](./#podtverzhdenie-zakaza)\*\*\*\*



* **Ввод ордера для CQG подключения**
* Order Entry for Rithmic connection
* Order Entry for Binance Futures

## Общая информация

Панель ввода ордеров позволяет создавать торговые ордера с различными условиями, такими как количество ордеров, цена, сторона, тип ордера, и отправлять их на рынок. На панели ввода заказа вы можете предоставить всю необходимую информацию для заказа и легко отправить ее, нажав соответствующую кнопку действия.

![](../../.gitbook/assets/sozdat-order.png)

Вся панель условно разделена на несколько зон:

* выбор торгового инструмента и торгового счета;
* установка необходимого количества заказа и стороны заказа \(Купить или Продать\);
* выбор типа заявки, ее цены и условия TIF;
* установка цен стоп-лосс и тейк-профит;
* информация о текущих ценах Ask и Bid, размере спреда, ценах VWAP, а также кнопка размещения ордера.

## Как открыть панель ввода заказов?

Откройте главное меню, щелкнув логотип, и в разделе **«Торговые»** щелкните значок OE.

![](../../.gitbook/assets/kak-otkryt-panel-sozdat-order.png)

## Выбор символа и счета

Выбор торгового инструмента можно выполнить вручную через Поиск символов или [привязав панель к другим панелям](https://help.quantower.com.ru/general-settings/binds), например, к графику. Просто выберите один цвет ссылки на двух панелях, и у них будет параметр [синхронизированного символа](https://help.quantower.com.ru/general-settings/link-panels).

{% hint style="info" %}
В зависимости от выбранного подключения и торговой пары, панель ввода ордера автоматически перечислит и покажет все поддерживаемые данным коннектом типы ордеров и условия, доступные для связанного инструмента при выбранном соединении. 
{% endhint %}

Если в вашем подключении доступно несколько торговых счетов, вы можете выбрать необходимую учетную запись, нажав кнопку «Выбрать учетную запись».

![](../../.gitbook/assets/vybor-podklyucheniya.png)

## Типы заказов и ограничения

Ввод ордеров автоматически перечисляет все поддерживаемые обменом типы ордеров, доступные для связанного инструмента при выбранном соединении. В рамках существующих подключений мы поддерживаем:

* **Рыночный ордер** - это ордер, размещаемый без цены с намерением получить лучшую ставку или лучшее предложение, доступное в настоящее время на рынке. Ордер исполняется по текущей лучшей цене.
* **Лимитный ордер** позволяет выставить ордер по определенной лимитной цене или лучше.
* **Стоп-ордер** позволяет подать рыночный ордер на покупку или продажу, если и когда будет достигнута цена срабатывания стоп-сигнала.  В каждом подключении могут быть свои особенные типы ордеров, доступные именно для выбранного соединения.

![](../../.gitbook/assets/tipy-orderov.png)



Параметры **Time-in-Force \(TIF\)** определяют продолжительность времени, в течение которого ордер будет продолжать работать, прежде чем он будет отменен. В рамках существующих подключений мы поддерживаем множество **TIF:**

* **DAY** - ордер будет отменен, если он не будет исполнен в течение текущего торгового дня;
* **FOK** \(или Fill or Kill\) - ордер будет отменен, если он не будет исполнен в полном объеме, как только он станет доступен;
* **Ордера GTC** \(действительны до отмены\) будут работать до тех пор, пока они не будут отменены трейдером или не истечет срок действия контракта;
* **IOC** \(Немедленно или отменить\) требует, чтобы любая часть ордера, которая не была исполнена, как только она становится доступной на рынке, была отменена;
* **Ордер GTD** \(Действителен до даты\) будет продолжать работать в системе и на рынке до тех пор, пока он не будет выполнен или до закрытия рынка в указанную дату.

![The list of TIF conditions](../../.gitbook/assets/tif-types.png)

{% hint style="info" %}
The TIF list can be different depends on connection, order type or instrument type!
{% endhint %}

## Защита ордера

Чтобы защитить позицию от значительного убытка, вы можете использовать ордера **Stop Loss**. Для этого активируйте флажок **«Stop Loss»** и укажите цену, по которой ордер будет закрыт.

Once the position becomes profitable, you can change the Stop Loss price to a break-even level. To automate this process, **Trailing Stop** was created. This tool is especially useful when price changes strongly in the same direction or when it is impossible to watch the market continuously for some reason.

![Activation of Trailing stop](../../.gitbook/assets/trailing-stop-order.png)

To gain profit, you can use the **Take Profit** order, which will automatically close the position at the specified price. To do this, activate the "_**Take Profit**_" checkbox and specify the price at which the order will be closed.

{% hint style="info" %}
Stop Loss order can be set:

* for Long positions below the current price
* for Short positions above the current price

Take Profit order can be set:

* for Long positions above the current price
* for Short positions below the current price
{% endhint %}

## Подтверждение заказа

Once you have set all the necessary parameters of the order and clicked the **PLACE ORDER** button, the order confirmation screen will appear.

This window contains summary information about your order, which will allow you to verify the correctness of the entered data - order type, trade instrument, price, quantity, prices of take profit and stop loss.

![Confirmation of the order placement](../../.gitbook/assets/order-confirmation.png)

![Confirmation of the order cancellation](../../.gitbook/assets/confirmation-of-order-cancel.png)

{% hint style="info" %}
If you activate the "_**Do not show again**_" checkbox, the confirmation will not be displayed and the order will be immediately sent to the order book. In order to return these notifications, it is necessary to activate the "_**Confirm order placement**_" checkbox in the [General settings](https://help.quantower.com/getting-started/general-settings#confirmations) of the application
{% endhint %}

