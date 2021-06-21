---
description: >-
  Просматривайте распределение цен в течение указанного времени через профиль
  TPO (известный как профиль рынка®) и понимайте, на каких уровнях цена провела
  больше всего времени.
---

# TPO диаграмма

{% embed url="https://youtu.be/BcDCx0tzlRA" caption="" %}

**Time Price Opportunity**  или TPO график показывает распределение цен в течение указанного времени, формируя таким образом профиль. Это позволяет понять, на каких уровнях или диапазонах цена провела больше всего времени, а также определить основные уровни поддержки и сопротивления.

![&#x414;&#x438;&#x430;&#x433;&#x440;&#x430;&#x43C;&#x43C;&#x430; &#x43F;&#x440;&#x43E;&#x444;&#x438;&#x43B;&#x44F; TPO \(&#x43F;&#x440;&#x43E;&#x444;&#x438;&#x43B;&#x44C; &#x440;&#x44B;&#x43D;&#x43A;&#x430;\), &#x43E;&#x431;&#x449;&#x438;&#x439; &#x432;&#x438;&#x434; &#x43D;&#x430; &#x43F;&#x43B;&#x430;&#x442;&#x444;&#x43E;&#x440;&#x43C;&#x435; Quantower](../.gitbook/assets/tpo-profile-chart-general-view.png)

Чтобы открыть новую панель TPO, перейдите в Главное меню \(значок с логотипом\) и выберите «Диаграмма TPO» в разделе «Аналитика».

![](../.gitbook/assets/menyu-diagramma-tro.png)

### Kлючевые элементы диаграммы профиля TPO

![&#x41E;&#x441;&#x43D;&#x43E;&#x432;&#x43D;&#x44B;&#x435; &#x44D;&#x43B;&#x435;&#x43C;&#x435;&#x43D;&#x442;&#x44B; &#x434;&#x438;&#x430;&#x433;&#x440;&#x430;&#x43C;&#x43C;&#x44B; &#x43F;&#x440;&#x43E;&#x444;&#x438;&#x43B;&#x44F; TPO \(&#x442;&#x430;&#x43A;&#x436;&#x435; &#x438;&#x437;&#x432;&#x435;&#x441;&#x442;&#x43D;&#x43E;&#x433;&#x43E; &#x43A;&#x430;&#x43A; &#x43F;&#x440;&#x43E;&#x444;&#x438;&#x43B;&#x44C; &#x440;&#x44B;&#x43D;&#x43A;&#x430;\) &#x432; Quantower](../.gitbook/assets/tpocontrols.png)

**Point of Control \(POC**\) - ценовой уровень наибольшей рыночной активности или объема торгов. На этом уровне цена большую часть времени проводила в диапазоне профиля.

**Value Area** - ценовой диапазон, в котором происходило примерно 68% - 70% рыночной активности или объема торгов.

**Отдельные или одиночные отпечатки** профиля размещаются в середине конструкции профиля, а не на верхнем или нижнем крае. Они возникают при импульсных движениях и используются как зоны поддержки / сопротивления, которые цена может протестировать в ближайшем будущем. Линия синглов указывает, где начинают формироваться синглы \(в случаях, когда имеется несколько одиночных отпечатков\).

**Буквы TPO** - базовый элемент диаграммы TPO, где каждая буква соответствует определенному времени \(«Build From»\).

## Основные элементы управления TPO графика

На верхней панели инструментов панели TPO графика есть три основных элемента управления:

* \*\*\*\*[**Агрегирование диаграммы профиля TPO**](tpo-chart.md#agregirovanie-diagrammy-profilya-tpo)\*\*\*\*
* \*\*\*\*[**Настройки стиля диаграммы профиля TPO**](tpo-chart.md#nastroiki-stilya-diagrammy-profilya-tpo)\*\*\*\*
* [**Volume Analysis**](tpo-chart.md#volume-analysis)

### Агрегирование диаграммы профиля TPO

Базовым элементом диаграммы TPO являются буквы, которые используются для построения структуры профиля рынка. Каждая буква изначально представляет собой получасовой период. Quantower предлагает указать в настройках агрегирования любые значения, на основе которых будет строиться профиль. Например, дневной профиль из 30-минутных баров считается «стандартным». Но вы можете установить более низкое значение «Построить из», и профиль будет более детальным. И наоборот, установите значение выше, и форма профиля будет более гладкой.

![](../.gitbook/assets/custom-period.gif)

![&#x41F;&#x440;&#x43E;&#x444;&#x438;&#x43B;&#x44C; TPO &#x43C;&#x43E;&#x436;&#x43D;&#x43E; &#x43F;&#x43E;&#x441;&#x442;&#x440;&#x43E;&#x438;&#x442;&#x44C; &#x441; &#x43B;&#x44E;&#x431;&#x44B;&#x43C; &#x43D;&#x430;&#x441;&#x442;&#x440;&#x430;&#x438;&#x432;&#x430;&#x435;&#x43C;&#x44B;&#x43C; &#x43F;&#x435;&#x440;&#x438;&#x43E;&#x434;&#x43E;&#x43C; &#x438; &#x431;&#x430;&#x437;&#x43E;&#x439;](../.gitbook/assets/screenshot_11.png)

* **Строить из \(**Минута, Час, День**\)** — этот параметр определяет продолжительность построения каждой буквы \(для A, B, C и т. д.\).
* **Агрегация профиля** — определяет диапазон для каждого профиля TPO. Стандартный диапазон - 1 день, но есть несколько базовых диапазонов для построения каждого профиля - Минута, Час, День. Например, однодневный диапазон начинается в начале торгового дня и заканчивается в конце текущего торгового дня \(определяемого в торговых часах или индивидуальной сессией\).
* **Диапазон истории** - определяет глубину истории для построения профилей TPO. При большой глубине истории профили объемов можно строить долго, потому что они используют тиковые данные.
* **Пользовательский шаг \(тики\)** - этот параметр определяет высоту и количество букв в профиле. Если включено, высота буквы будет соответствовать количеству отметок, заданному в параметре. Если этот параметр отключен, высота и количество букв будут выбираться автоматически с использованием интеллектуального алгоритма. В результате график будет выглядеть наиболее оптимальным для анализа.

### Настройки стиля диаграммы профиля TPO

Выберите любую цветовую схему для лучшего представления и анализа профиля TPO, а также включите POC, Value Area, Singles, Standard Chart и т.д.

* **Display** - режим отображения писем профиля TPO - Ячейки  или Буквы 

![&#x41E;&#x442;&#x43E;&#x431;&#x440;&#x430;&#x436;&#x435;&#x43D;&#x438;&#x435; &#x43F;&#x440;&#x43E;&#x444;&#x438;&#x43B;&#x44F; TPO &#x432; &#x432;&#x438;&#x434;&#x435; &#x437;&#x430;&#x43F;&#x43E;&#x43B;&#x43D;&#x435;&#x43D;&#x43D;&#x44B;&#x445; &#x44F;&#x447;&#x435;&#x439;&#x43A;&#x438; &#x438;&#x43B;&#x438; &#x431;&#x443;&#x43A;&#x432;](../.gitbook/assets/display-boxes-or-letters.png)

* **Coloring Mode —** choose any color scheme for better representation and analysis of the TPO profile. Currently, there are 10 different coloring modes available — **Single Color, Up/Down Profile, Up/Down Bars, Heatmap, Delta Profile, Delta Price, Delta Bars, Volume Profile, Volume Price, Volume Bars**. 
* **POC типы** — уровень цен наибольшей активности на рынке или объем торгов на графике. Доступны два типа: **Final POC**, показывает единственную строку **Migrating POC**, которая показывает изменение POC в течение торгового дня или выбранной сессии.
* Цветовая схема — выберите любую цветовую схему для лучшего представления и анализа профиля TPO. В настоящее время доступно 10 различных режимов окраски - один цвет, профиль вверх / вниз, полосы вверх / вниз, тепловая карта, профиль дельты, цена дельты, столбцы дельты, профиль объема, цена объема, столбцы объема.

  POC типы — уровень цен наибольшей активности на рынке или объем торгов на графике. Доступны два типа: Final POC, показывает единственную строку Migrating POC, которая показывает изменение POC в течение торгового дня или выбранной сессии.

![](../.gitbook/assets/migrating-poc.gif)

* **Plot Symbol** — show/ hide the standard chart on the TPO Profile chart. Select a **\*\*\[**chart style**\]\(chart/chart-types/\#chart-types-and-styles\)**: **\_**Bar, Candle, Line, Area, Dotted Line, Quantower style\*\*\_.

![](../.gitbook/assets/overlaying-chart.gif)

* **Show Point of Control \(POC\)** — enable a price level of the greatest market activity or trading volume on the chart. At this level, the price spent most time over the profile range. 
* **Show Value Area** — enable price range in which approximately 68% - 70% of the market activity or trading volume took place. 
* **Show Singles** or **single prints** of the profile are placed in the middle of a profile structure, not at the upper or lower edge. They occur on impulse movements and are used as support/resistance zones, which the price can test in the near future. The singles line indicates where the singles begin to form \(in cases when there are several single prints\).

![Enable POC, Value Area and Singles on TPO Profile](../.gitbook/assets/key-elemetns-tpo.gif)

### Volume Analysis

TPO profiles are used on their own to find areas of support and resistance, and can also be used in conjunction with volume profiles. For this, we have added **Volume Analysis** control to the top toolbar of the panel. Here you can select the data type and show/hide the POC & Value Area.

![Add Volume Profiles on TPO Profile Chart](../.gitbook/assets/volume-analysis-tpo.gif)

Switch Volume Profile between [**different data types**](volume-analysis-tools/#data-types-of-volume-analysis-tools), such as delta, buy&sell, trades, volume, etc.

## Splitting & Merging of TPO Profile Chart

Use TPO splitting for a detailed analysis of profile formation. There are two splitting modes available in the platform:

* **Split full profile**, that separates the TPO profile into each bar or letter. To separate profile into columns, click on the profile and press _**"Split"**_ button that is placed on the lower border of a selected profile.

![Split TPO profile into each bar for a detailed analysis](../.gitbook/assets/splitting.gif)

* **Divide by bar**, that option splits the profile in half on the selected bar. To separate TPO profile in half, select a necessary profile and right-click to open the context menu and click on _**"Divide by bar"**_ button.

![Separate TPO Profile at selected bar](../.gitbook/assets/divide-at-bar.png)

![](../.gitbook/assets/dividing.gif)

### Merging of TPO Profile

**Merge** is a feature that combines several profiles into one. Right-click on the selected profile to open the context menu and select **Merge Left** or **Merge Right**. To return profiles to their original positions, press the Reset button.

![](../.gitbook/assets/merging-tpo-profile_market-profile.gif)

## Session Time

Set the custom time range for the necessary trading session and the profile will be built within this range. The rest of the time the profile will not take into account.

To set the time of the necessary session, go to the **TPO Chart settings -&gt; View -&gt; Custom session.** Set the time according the time zone.

![Set custom sessions for TPO Profile](../.gitbook/assets/custom-session-time.gif)

## Additional settings of TPO Profile

Right-click on the chart area -&gt; **Settings** to open the general settings of the TPO Chart panel.

![General settings of TPO Profile Chart in Quantower platform](../.gitbook/assets/tpo-chart-settings.png)

