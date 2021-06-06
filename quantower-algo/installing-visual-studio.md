---
description: >-
  Как установить расширение Visual Studio и Quantower Algo и создать свои
  собственные индикаторы
---

# Установка Visual Studio

Visual Studio - это интегрированная среда разработки \(IDE\) от Microsoft, которая включает редактор кода с IntelliSense, отладчик, поддержку систем управления версиями и многие другие профессиональные функции. Текущая поддерживаемая версия **Visual Studio - 2019.**

{% hint style="success" %}
Мы рекомендуем вам использовать самую базовую версию Visual Studio - версию Community, которая доступна бесплатно.
{% endhint %}

Вы можете скачать [**Visual Studio с официального сайта**](https://visualstudio.microsoft.com/ru/thank-you-downloading-visual-studio/?sku=Community&rel=16). Для его установки требуется около 10 минут и 2,5 ГБ свободного места на жестком диске.

{% embed url="https://www.youtube.com/watch?v=CelIt\_F0Wuw" caption="" %}

Download the web installer and run it. After initialization, you will be prompted to select the required components. For using with Quantower Algo extension we need only the "**NET desktop development**" workload. You can uncheck optional components also, to reduce installation size:

Загрузите веб-установщик и запустите его. После инициализации вам будет предложено выбрать необходимые компоненты. Для использования с расширением Quantower Algo нам понадобится только рабочая нагрузка **«Разработка рабочего стола NET».** Вы также можете снять флажок с дополнительных компонентов, чтобы уменьшить размер установки:

![&#x41C;&#x438;&#x43D;&#x438;&#x43C;&#x430;&#x43B;&#x44C;&#x43D;&#x430;&#x44F; &#x43D;&#x435;&#x43E;&#x431;&#x445;&#x43E;&#x434;&#x438;&#x43C;&#x430;&#x44F; &#x443;&#x441;&#x442;&#x430;&#x43D;&#x43E;&#x432;&#x43A;&#x430;](../.gitbook/assets/screenshot_1dd.png)

Продолжите установку, и через несколько минут, после загрузки и применения необходимых пакетов, Visual Studio запустится автоматически:

![&#x41F;&#x440;&#x435;&#x434;&#x441;&#x442;&#x430;&#x432;&#x43B;&#x435;&#x43D;&#x438;&#x435; Visual Studio 2019 &#x43F;&#x43E; &#x443;&#x43C;&#x43E;&#x43B;&#x447;&#x430;&#x43D;&#x438;&#x44E;](../.gitbook/assets/default-view-of-visual-studio.png)

Теперь нам нужно установить расширение **Quantower Algo** из Visual Studio Marketplace. Используйте пункт главного меню _**«Инструменты -&gt; Расширения и обновления ...»,**_ чтобы открыть Менеджер расширений. Введите **«Quantower»** в поле поиска на вкладке «Интернет», и вы найдете необходимое расширение:

![&#x41E;&#x43A;&#x43D;&#x43E; &#x440;&#x430;&#x441;&#x448;&#x438;&#x440;&#x435;&#x43D;&#x438;&#x439; &#x438; &#x43E;&#x431;&#x43D;&#x43E;&#x432;&#x43B;&#x435;&#x43D;&#x438;&#x439;](../.gitbook/assets/extensions-manager.png)

Щелкните **"Загрузить"**. Visual Studio попросит вас перезапустить, чтобы завершить процесс установки расширения.

Чтобы проверить, успешно ли установлен Quantower Algo, щелкните пункт меню _**«Файл -&gt; Создать -&gt; Проект»**_, введите «Индикатор», и вы увидите специальный тип проекта для пустого индикатора:

![&#x41E;&#x43A;&#x43D;&#x43E; &#x43D;&#x43E;&#x432;&#x43E;&#x433;&#x43E; &#x43F;&#x440;&#x43E;&#x435;&#x43A;&#x442;&#x430;](../.gitbook/assets/image%20%2854%29.png)

Теперь все готово для создания [**вашего первого индикатора.**](https://app.gitbook.com/@quantower/s/quantower-ru/~/drafts/-MbWdSvrjFLRXlV514IW/quantower-algo/simple-indicator)\*\*\*\*

