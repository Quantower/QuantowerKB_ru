# Как подключиться к FxPro через Quantower

Чтобы подключить платформу Quantower к брокеру FxPro и отправлять торговые приказы, вам необходимо использовать cTrader Gateway. Если у вас уже есть торговый счет в FxPro, перейдите к предпоследнему шагу в этом руководстве.

{% embed url="https://youtu.be/FqR1nqsjMrI" caption="" %}

* Перейдите на официальный сайт FxPro и в ****[**разделе Инструменты**](https://www.fxpro.com/trading-platforms/ctrader) выберите платформу cTrader.
* Создайте торговый счет, заполнив регистрационную форму. Демо-счет и реальный счет создаются под одним идентификатором cTrader ID, поэтому существует только одна форма для открытия счета. При регистрации всегда выбирайте платформу cTrader, где вам нужно ее указать.

![Select cTrader platform during the registration process](../../.gitbook/assets/register-with-fxpro-_-select-ctrader.png)

* After registration, you need to create a demo account under your cTrader ID

![](../../.gitbook/assets/fxpro-direct-create-demo.png)

* Choose cTrader platform, leverage, account currency and account size

![](../../.gitbook/assets/fxpro-direct-demo.png)

* After creating a demo account, check the E-Mail that you used when registering your account. In the letter with subject **"Welcome to cTrader ID"** is your ID that will be used as a login in platforms Quantower and cTrader. Set the password for authorization by clicking on the **"Set Password"** button.

![](../../.gitbook/assets/set-password.png)

{% hint style="info" %}
To enter the Quantower platform, use the **cTrader ID** and **password** that you set in the previous step.
{% endhint %}

* Before connecting for the first time through Quantower platform, you need to activate your account in the cTrader system. You can do it via FxPro **cTrader Web-based** platform [https://ct.fxpro.com/](https://ct.fxpro.com/)

![](../../.gitbook/assets/fxpro-ctrader-activation.png)

* Once you logged in to the cTrader web terminal, accept the agreement and switch to the demo account in the upper right corner of the web terminal. This is necessary to activate both the Real and Demo accounts separately.

![](../../.gitbook/assets/select-demo-account.png)

* After that, in the Quantower platform in the connection manager, select cTrader Gateway connection with Demo or Real and press **"Connect"** button. An authorization form will appear, where you need to specify an email or cTrader ID, as well as a password. This is a standard OAUTH authorization where you can see the connection information. **Allow access** and start trading :\)

![](../../.gitbook/assets/ctrader-connection.gif)

![](../../.gitbook/assets/oauth-2019-08-14-18.57.12.png)

* You can place orders via Quantower or cTrader. Good luck!

![](../../.gitbook/assets/chart-on-ctrader-an-quantower.png)

