---
description: >-
  Индикатор облака Ишимоку отображает поддержку и сопротивление, импульс и тренд
  в одном окне.
---

# Ichimoku Cloud Indicator

## Что такое индикатор облака Ишимоку?

Индикатор облака Ишимоку отображает поддержку и сопротивление, импульс и тренд в одном окне. TenkanSen и KijunSen похожи на скользящие средние и анализируются по отношению друг к другу. Когда краткосрочный индикатор TenkanSen поднимается выше долгосрочного индикатора KijunSen, тенденция по ценным бумагам обычно положительная. Когда TenkanSen опускается ниже KijunSen, тенденция по ценным бумагам обычно отрицательная. Затем TenkanSen и KijunSen как группа анализируются относительно Облака, который состоит из области между Senkou A и Senkou B.

![&#x418;&#x43D;&#x434;&#x438;&#x43A;&#x430;&#x442;&#x43E;&#x440; Ichimoku Cloud &#x43D;&#x430; &#x43F;&#x43B;&#x430;&#x442;&#x444;&#x43E;&#x440;&#x43C;&#x435; Quantower](../../../.gitbook/assets/image%20%2872%29.png)

## Как работает индикатор Ichimoku Cloud

* Когда TenkanSen и KijunSen явно находятся над облаком, тенденция выпуска положительная.
* Когда TenkanSen и KijunSen явно ниже Облака, тенденция выпуска отрицательная.
* Использование облака для определения тренда:
* Когда цены выше облака, тренд идет вверх. Когда цены ниже облака, тренд идет вниз. 
* Когда Sendou A растет и превышает Senkou B, восходящий тренд усиливается. 
* Когда Сенкоу А падает ниже Сенкоу В, нисходящий тренд усиливается.
* Сигнал на покупку усиливается, когда Tenkan Sen пересекает Kijun Sen, в то время как Tenkan Sen, Kijun Sen и цена находятся выше облака.
* Сигнал на продажу усиливается, когда TenKan Sen пересекает Kijun Sen, в то время как Tenkan Sen, Kijun Sen и цена находятся ниже облака.

## Расчет индикатора Ichimoku Cloud

Индикатор Ichimoku Cloud состоит из пяти графиков. Их имена и расчеты:

* TenkanSen \(Линия преобразования\): \(High + Low\) / 2 периода по умолчанию = 9
* KijunSen \(Базовая линия\): \(High + Low\) / 2 периода по умолчанию = 26
* Chiku Span \(Lagging Span\): цена закрытия сдвинута назад на 26 баров.
* Senkou A \(ведущий диапазон A\): \(TenkanSen + KijunSen\) / 2 \(Senkou A сдвинут вперед на 26 тактов\)
* Senkou B \(опережающий интервал B\): \(High + Low\) / 2 с периодом = 52 \(Senkou B сдвинут вперед на 26 баров\)

