---
description: >-
  Технология Rithmic обеспечивает доступ к торговле фьючерсами и опционами на
  CME, CBOT, NYMEX и других биржах. Полная глубина рынка, надежные данные и
  отличное исполнение - вот основные характеристики
---

# Connection to Rithmic

Чтобы подключить Quantower к брокеру, использующему технологию Rithmic, достаточно иметь (или создать новую) учетную запись.

* ****[**Как подключить существующую учетную запись**](connection-to-rithmic.md#kak-podklyuchit-sushestvuyushuyu-uchetnuyu-zapis)****
* ****[**Создание и подключение новой учетной записи.**](connection-to-rithmic.md#creating-a-new-accounts-and-further-connection)****
* [**Problems during the connection to Rithmic**](connection-to-rithmic.md#problems-during-the-connection-to-rithmic)

## Как подключить существующую учетную запись

* [**Загрузите и установите RTrader Pro**](https://yyy3.rithmic.com/?page\_id=16) с официального сайта Rithmic
* Откройте диспетчер соединений на платформе Quantower, выберите Rithmic и укажите тип соединения (Demo / Real).
* Нажмите «Настройки подключения» и активируйте опцию «Использовать RTrader», чтобы избежать дополнительной оплаты за подписку на рыночные данные. При необходимости трейдер может изменить сервер. По умолчанию сервер Rithmic Paper Chicago настроен для демо счетов, а сервер Rithmic Aurora Chicago настроен для реальных счетов.
* Введите свой логин и пароль и нажмите "Подключиться".

![Введите данные для входа в систему для подключения к Rithmic.](../.gitbook/assets/rithmic-connection.png)

{% hint style="info" %}
С 1 мая 2020, биржа [**CME изменила правила определения профессионального участника рынка**](https://yyy3.rithmic.com/?p=1069) и, как следствие, увеличила комиссию за рыночные данные. Чтобы правильно определить профессионального участника, Ritmic изменил параметры подключения на своей платформе, а также в API для таких платформ, как Quantower.&#x20;

Чтобы избежать дополнительной оплаты за подписку на рыночные данные, трейдеру необходимо подключиться через платформу RTrader Pro в режиме **Allow Plugins,** а также активировать настройку в Quantower, которая называется **Use RTrader**.
{% endhint %}

![Активируйте опцию Use RTrader, чтобы избежать дополнительной оплаты за подписку на рыночные данные](../.gitbook/assets/rithmic-plugin.gif)

## Создание и подключение новой учетной записи.

* [**Create a new demo**](https://rithmic.com/demo.html#sign-up) or open a real account with any broker supporting Rithmic technology, accept agreements, and start using our platform.

{% embed url="https://youtu.be/3kpiOCiqE5Q" %}

* To register [**Rithmic Demo**](https://rithmic.com/demo.html#sign-up) **go to their official website or **follow this [link](https://rithmic.com/demo.html#sign-up)
* Fill in all the required fields
* Accept _**"Market Data Subscription Agreement"**_ and _"**Market Data Self-Certification"**_
* Account will be activated within 30-60 minutes.

## **Problems during the connection to Rithmic**

Sometimes, when connecting to the Rithmic, you may see the error **"**_**Market Data Connection Closed".**_

![Rithmic error "Market Data Connection Closed" in Quantower](../.gitbook/assets/connections-error-with-rithmic.png)

This error message is most commonly encountered by _**new Rithmic users for various reasons**_ and is not within the control of Quantower platform. More often it occurs for the following reasons:

* You didn't accept aggrements "_Market Data Subscription Agreement"_ and _"Market Data Self-Certification"_  during the registration on Rithmic's website or in R Trader platform. _We recommend connecting through **R Trader** or **R Trader Pro** platforms to check your account._
* A new account was created less than an hour ago. Usually the **full activation of a new account takes from 30 minutes to 1 hour**.
* The error can be encountered because the Rithmic server is unavailable to be connected to. This error commonly can be encountered over the weekend. In this case it is best to wait until Sunday evening to see if you can connect to determine if this is the problem or there is some other problem.
* Rithmic demo accounts are limited to 14 days per exchange guidelines on providing live, streaming data. If you have used a Rithmic demo previously you will _not_ be able to login with a new Rithmic demo Username.
* If you are unable to connect within a few days, you need to contact your broker about this issue.

If you enable Use RTrader plugin in Connection Settings and still can not connect to Rithmic, please check that you have more than 1 active session for Market data.

![](<../.gitbook/assets/image (100).png>)
