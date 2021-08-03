---
description: >-
  Менеджер подключений позволяет выбрать из доступных интеграций те, с которыми
  вы торгуете, и подключиться к ним, используя свои учетные записи.
---

# Менеджер подключений

{% embed url="https://www.youtube.com/watch?v=\_1tnBDlyDbY" caption="Как работать с диспетчером подключений в Quantower" %}

**Подключения** - это интеграция со сторонними поставщиками, которые предоставляют различные данные: торговые котировки, историю символов и т. д.

![&#x412;&#x44B;&#x437;&#x43E;&#x432; &#x43C;&#x435;&#x43D;&#x435;&#x434;&#x436;&#x435;&#x440;&#x430; &#x43F;&#x43E;&#x434;&#x43A;&#x43B;&#x44E;&#x447;&#x435;&#x43D;&#x438;&#x439;](../.gitbook/assets/vyzov-menedzhera-podklyuchenii.png)

## Основная информация

**Диспетчер подключений** - это экран, который позволяет вам выбрать из доступных подключений те, с которыми вы торгуете, и подключиться к ним, используя свои учетные записи. При подключении к любому брокеру или бирже диспетчер подключений запоминает ваши учетные данные и будет использовать их для дальнейших автоматических подключений \(повторное подключение в случае ошибок\). Если вы не хотите хранить свои учетные данные в диспетчере, просто щелкните значок «Заблокировать» в форме входа.

![&#x41E;&#x43A;&#x43D;&#x43E; &#x434;&#x438;&#x441;&#x43F;&#x435;&#x442;&#x447;&#x435;&#x440;&#x430; &#x43F;&#x43E;&#x434;&#x43A;&#x43B;&#x44E;&#x447;&#x435;&#x43D;&#x438;&#x439; &#x441; &#x43D;&#x435;&#x441;&#x43A;&#x43E;&#x43B;&#x44C;&#x43A;&#x438;&#x43C;&#x438; &#x443;&#x447;&#x435;&#x442;&#x43D;&#x44B;&#x43C;&#x438; &#x437;&#x430;&#x43F;&#x438;&#x441;&#x44F;&#x43C;&#x438;](../.gitbook/assets/multiple-accounts.gif)

Окно диспетчера подключений состоит из двух столбцов: список подключений и информация о подключении. Столбец информации о подключении содержит информацию об активном подключении или форме входа в систему, если текущее подключение неактивно.

Each active connection is marked with green Status dot by the left hand from its name. The "_**Star**_" icon indicates that connection is favorite and displayed on Control center toolbar. This icon is also used to **add/remove** a connection **from favorites**.

Connection login form varies depending on integration requirements. Usually, it has Login & password fields and “_**Connect**_” button. This button initiates the authorization process. Some integrations have settings \(a “_**Gear**_” icon on the right side of connection logo\) and account creation button \(a “_**User with plus**_” icon on the right side of “_**Connect**_” button\). Account creation redirects you to the integration vendor website.

Once connected, info column will contain the data about ping and current connection status text. There is a “_**Disconnect**_” button also.

## Multi-connect

{% hint style="info" %}
Quantower supports multiple connections simultaneously, but this function available under paid licenses — Advanced Features, Crypto Package, Multi-Asset package and All-In-One License.
{% endhint %}

![Multiple connections in Quantower at the same time ](../.gitbook/assets/multiple-connections.png)

## Настройки подключения

У каждого подключения есть свои особенности. Для некоторых подключений можно выбирать дополнительные URL для коннекта по API. Для некоторых подключений/брокеров можно выбирать отдельные рынки и биржи. 

Что бы проверить дополнительные настройки, доступные для выбранного коннекта, перейдите по ссылке "Настройки подключения", которая размещена внизу в окне менеджера подключений:

![&#x414;&#x43E;&#x43F;&#x43E;&#x43B;&#x43D;&#x438;&#x442;&#x435;&#x43B;&#x44C;&#x43D;&#x44B;&#x435; &#x43D;&#x430;&#x441;&#x442;&#x440;&#x43E;&#x439;&#x43A;&#x438; &#x43E;&#x442;&#x434;&#x435;&#x43B;&#x44C;&#x43D;&#x43E;&#x433;&#x43E; &#x43F;&#x43E;&#x434;&#x43A;&#x43B;&#x44E;&#x447;&#x435;&#x43D;&#x438;&#x44F;](../.gitbook/assets/nastroiki-podklyucheniya.png)

**Далее, в зависимости от выбранного коннекта, Вы сможете настроить дополнительные параметры, которые относятся к настройкам отдельного соединения.**

* **\[Binance Futures\]**  Есть возможность выбрать необходимость загрузки истории сделок. Для некоторых коннектов, например для биржи Binance, история сделок сохраняется локально на Вашем компьютере. И история сделок будет отображаться на графике и в информационных панелях с данными о истории только при отмеченном параметре "загружать историю сделок". Так же можно разрешить/не разрешать изменение кредитного плеча, установить период обновления, базу расчета прибыли и т.д.

![\[Binance Futures\] ](../.gitbook/assets/fyuchersy-binans.png)

* **\[Bybit\]** Выбор альтернативной ссылки для получения данных:

![\[Bybit\]](../.gitbook/assets/babit-nastroiki.png)

*  **\[CQG\]** Выбор определенных рынков, что бы оптимизировать в дальнейшем выбор торговых пар в дереве символов для торговли.

![\[CQG\] ](../.gitbook/assets/amp-dopolnitelnye-nastroiki.png)

*  **\[Binance Margin\]** Выбрать необходимость загрузки истории сделок. Для некоторых коннектов, например для биржи Binance, история сделок сохраняется локально на Вашем компьютере. И история сделок будет отображаться на графике и в информационных панелях с данными о истории только при отмеченном параметре "загружать историю сделок"

![\[Binance Margin\] ](../.gitbook/assets/binans-marzhin.png)

