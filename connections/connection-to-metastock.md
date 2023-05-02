---
description: >-
  Это руководство покажет процесс регистрации новой учетной записи для MetaStock
  XENITH, установки приложения Eikon и как подключить его через платформу
  Quantower.
---

# Подключение к MetaStock

* [**Как создать учетную запись MetaStock XENITH / EIKON?**](connection-to-metastock.md#kak-sozdat-uchetnuyu-zapis-metastock-xenith-eikon)
* [**Скачайте и установите Metastock XENITH**](https://app.gitbook.com/@quantower/s/quantower-ru/\~/drafts/-Mf2S4zWrMsbBFI05SuA/connections/connection-to-metastock#download-and-install-metastock-xenith)
* [**Запуск Quantower с подключением к Metastock**](https://app.gitbook.com/@quantower/s/quantower-ru/\~/drafts/-Mf2S4zWrMsbBFI05SuA/connections/connection-to-metastock#launch-quantower-with-metastock-connection)
* [**Как добавить символ на график или на другую панель**](connection-to-metastock.md#kak-dobavit-simvol-na-grafik-ili-na-druguyu-panel)

## Как создать учетную запись MetaStock XENITH / EIKON?

[**Перейдите по ссылке**](https://www.metastock.com/offer/ek/?whc=quantowerek\&pc=Eq-quantower) и нажмите кнопку _**«Получить БЕСПЛАТНУЮ пробную версию XENITH на 1 месяц»**_. Выберите рыночные данные, на которые вы хотите подписаться.

![Цены на подписку на биржевые данные MetaStock XENITH](../.gitbook/assets/pricing-metastoc-xenith-\_-eikon.png)

Metastock предлагает базу данных различных аналитических данных, разделенных не только по типам, но и по регионам. Например, если вам нужны рыночные данные для конкретной биржи или региона (Азия, Европа), вы можете легко выбрать их на их веб-сайте. Но мы рекомендуем использовать для этого обратиться в поддержку Metastock, которая поможет вам создать план данных, соответствующий вашим требованиям.

![MetaStock Eikon в действии](<../.gitbook/assets/screenshot\_3 (1).png>)

**Создайте учетную запись**, чтобы получать их продукты. Если у вас уже есть учетная запись, войдите в систему.

![Войдите в свою учетную запись или создайте новую](../.gitbook/assets/create-an-account-metastock.png)

## Скачайте и установите Metastock XENITH

После того, как вы выбрали необходимую подписку и создали новую учетную запись, вам необходимо принять "Пользовательское соглашение", загрузить и установить Metastock XENITH. Ссылка доступна в личном кабинете после регистрации.

## Запуск Quantower с подключением к Metastock

Выберите соединение с Metastock в диспетчере соединений Quantower и нажмите "Подключить". Это также запустит программное обеспечение Metastock. Введите учетные данные, полученные от Metastock, в их приложение.

![Нажмите кнопку «Подключиться», и платформа автоматически запустит платформу Eikon.](../.gitbook/assets/connection-to-metastock.png)

![Запуск MetaStock XENITH Eikon](../.gitbook/assets/thomson-reuters-eikon-connection.png)

## Как добавить символ на график или на другую панель

{% hint style="info" %}
Из-за ограничений API подключение к MetaStock Xenith позволяет находить символы только по точному тикеру (!)
{% endhint %}

Поисковая система на платформе Eikon позволяет искать акции по текстовому описанию или буквам любого регистра. К сожалению, этот механизм не распространяется на другие платформы через API.

По этой причине важно использовать точный тикер акций, представленный на платформе Eikon. В противном случае вы не получите результатов поиска.

![Используйте точный тикер акций, чтобы получать рыночные данные в Quantower](../.gitbook/assets/tiker-poisk.png)

![Используйте точный тикер акций, чтобы получать рыночные данные в Quantower](<../.gitbook/assets/tiker-2 (1).png>)

![Поиск по описанию не найдет акции](../.gitbook/assets/poisk-po-opisaniyu.png)

![Поиск работает только по точному тикеру](../.gitbook/assets/poisk-po-tochnomu-tikeru.png)

![Поиск работает только по точному тикеру](../.gitbook/assets/tiker-2.png)





