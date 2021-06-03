---
description: >-
  Профиль объема отображает торговую активность за определенный период времени
  на определенных ценовых уровней
---

# Профили объема

**Профиль объема** отображает торговую активность за определенный период времени на определенных ценовых уровнях. Это означает, что он показывает, что было куплено и продано на этих текущих уровнях, и отображает их в виде гистограммы сбоку от вашего графика. Профиль объема позволяет увидеть зоны максимального торгового интереса и, как следствие, «истинные» уровни поддержки / сопротивления.

Платформа Quantower предлагает четыре типа профилей объема:

* [**Step Volume Profile**](volume-profiles.md#step-volume-profile) ****Пошаговый профиль объема 
* \*\*\*\*[**Left Volume Profile**](volume-profiles.md#left-and-right-volume-profiles)\*\*\*\*
* \*\*\*\*[**Right Volume Profile**](volume-profiles.md#left-and-right-volume-profiles)\*\*\*\*
* \*\*\*\*[**Custom Volume Profile**](volume-profiles.md#custom-volume-profile)\*\*\*\*

## Пошаговый профиль объема 

Пошаговый профиль отображает профили объема с определенным временным шагом. Например, установите период шага равным 1 часу, и вы увидите профили с одинаковыми почасовыми шагами на графике. Изменяя типы данных, вы увидите распределение торгового объема, выполненных сделок, а также дельту для каждого часа торговой сессии.

Вы можете включить профиль шага через панель инструментов анализа объема или их настройки.

![](../../../.gitbook/assets/poshagovyi-profil.gif)

### Общие настройки профиля шага

![](../../../.gitbook/assets/poshagovyi-profil1.gif)

* **Step period & Step coefficient** – determines the step to build the profile. Step period has four types –_Minute, Hour, Day, Week_.
* **Data type** – choose any of the [**20+ data types**](./#data-types-of-volume-analysis-tools) to build a step profile
* **Histogram position** – places the profile on the left or right side relative to the starting point.
* **Histogram label position** – determines the position of the data value: _left, right or none_
* **Show Value Area** – shows the price area with 70% of trading activity for the specified time range. The value of 70% is set by default, but the user can change it at his discretion.
* **Show Value Area borders** – shows the outer limits of the Value Area as dotted lines
* **Highlight maximum value** – levels with the maximum value are highlighted with the specified color
* **Show totals** – this option summarizes the data based on which the profile is built.

![Step profile with various data types](../../../.gitbook/assets/step-profile-data-types.gif)

## Left & Right Volume Profiles

**Left** and **Right volume profile** can be placed on the left and right side of the chart respectively. For example, you can set the delta data on one profile, and on the other the total volume for the same period of time. You can **combine several profiles** that are built on different time periods into one combo profile and put it on left or right chart position.

![Quantower allows to place multiple volume profiles with different data types](../../../.gitbook/assets/left_right-profile.png)

## Custom Volume Profile

Custom profile allows you to create a profile for any time range. For instance, you want to see the distribution of the delta on the flat chart or for the impulse bar. As with other volume analysis tools, you can choose any available data types for display.

![Custom volume profile can be applied to any range](../../../.gitbook/assets/new-custom-profile.gif)

After you have placed a custom profile on the chart, a control panel with five options will appear next to it.

![Control panel for custom volume profile](../../../.gitbook/assets/image%20%2820%29.png)

* Dublicate profile with the same range and settings
* Move profile to the background or foreground
* Lock current position of the profile. Prohibits the profile movement.
* **Additional settings** for selected profile
* Delete selected profile

## Additional settings for custom profile

In addition to the settings for quick management of custom profile, there are additional settings. Let's take a closer look at what you can customize.

![Additional settings for custom volume profile](../../../.gitbook/assets/custom-profile-settings.gif)

There are a lot of various settings, but the most intersting are:

* **Value Area** — shows the price area with 70% of trading activity for the specified time range. The value of 70% is set by default, but the user can change it at his discretion.
* **POC Ray** — extends the level of maximum volume \(Point of Control\) to the price scale
* **Show Total** — shows/hides the total number under certain profile
* **Custom step \(ticks\)** summarizes the volume data of as many price levels as specified in the setting. By default, the value of the custom step is set to 1 tick, which means the volume data are shown at each price level.

