---
description: >-
  Панель Positions отображает расширенную информацию обо всех открытых в данный
  момент позициях
---

# Открытые позиции

На панели «Позиции» отображаются все открытые на данный момент позиции. Как только вы открываете новую позицию, она появляется на этой панели и становится доступной для управления. Панель **Позиции** связана с группой **Портфолио** боковой панели Центра управления.

![](../.gitbook/assets/portfolio.png)

![&#x41E;&#x431;&#x449;&#x438;&#x439; &#x432;&#x438;&#x434; &#x43F;&#x430;&#x43D;&#x435;&#x43B;&#x438; Positions](../.gitbook/assets/positions.png)

## Доступные столбцы

| **Account** | логин учетной записи, на которой открыта позиция |
| :--- | :--- |
| **Symbol**  | торгуемый символ |
| **Description** | комментарии к символу |
| **Symbol type** | рыночная категория символа \(CFD, спот, акции и т. д.\) |
| **Expiration date** | дата истечения контракта |
| **Position ID** | уникальный номер, который торговая система присваивает каждой позиции |
| **Side** | тип сделки \(ПОКУПКА или ПРОДАЖА\) |
| **Open price** | цена, по которой была открыта позиция |
| **Current price** | рыночная цена, которую можно получить у брокера |
| **Quantity** | объем позиции в лотах или единицах, в зависимости от того, что выбрано в диалоговом окне «Настройки». |
| **Date/Time** | дата и время открытия позиции |
| **Gross P/L** | прибыль / убыток в валюте счета, рассчитывается исходя из разницы в цене |
| **Gross P/L, ticks** |  |
| **Net P/L** | прибыль / убыток по позиции без учета комиссии |
| **Position exposure** | размещение позиции в валюте счета. Рассчитывается на основе цены открытия |
| **Position value \(open price\)** | открытая стоимость позиции. Рассчитывается на основе цены открытого рынка |
| **Position value \(current price\)** | текущая стоимость позиции. Рассчитывается исходя из текущей рыночной цены |
| **Fee** | показывает общую сумму комиссии, взятой за позицию |
| **Swaps** | суммы, собранные / выплаченные брокером при переносе позиции на новую дату валютирования |
| **Expiration date** | дата истечения контракта |
| **Strike price** | цена исполнения опционного контракта |
| **Stop loss** | Цена стоп-лосса, установленная для позиции |
| **Take profit** | Цена тейк-профита, установленная для позиции |

## Context menu actions

By right-clicking on each row of Positions panel, you will get a context menu with the following functions:

![Context functions](../.gitbook/assets/positions_context.png)

### Selected position\(s\) actions

| **Modify position** | Invokes the modification screen, allowing to add SL/TP orders to selected position manually |
| :--- | :--- |
| **Modify SL to breakeven** |  |
| **Quick SL/TP** | allows quick adding SL/TP orders to selected position |
| **Close position** | Options: close all selected positions, all positions by selected symbol, all positions for selected account, all positions |
| **Reverse** | allows reversing all selected positions, all positions by selected symbol, all positions by selected account, all positions |

### Common actions

| **Group by** | Groups all rows by the selected column |
| :--- | :--- |
| **Columns visibility** | Allows to toggle the columns visibility |

## Hot buttons toolbar

In order to manage your position efficiently, there is a Hot buttons toolbar in Positions panel. It allows trader to perform the most crucial actions with each, several or all available opened positions in one click.

{% hint style="danger" %}
Depending on the panel settings, hot buttons can proceed without confirmation screen. Please be careful while using them.
{% endhint %}

### Hot buttons list

| **Breakeven** |  |
| :--- | :--- |
| **Close all** | closes all opened positions |
| **CLX all** | closes all opened positions and cancels all orders |
| **Reverse all** | reverses all positions |
| **Close negative** | closes the positions with negative P/L |
| **Close positive** | closes the positions with positive P/L |
| **Close long** | closes the positions with Side = Long |
| **Close short** | closes the positions with Side = Short |
| **Close** | closes all positions by selected symbol and account |
| **Close selected** | closes all selected positions |
| **Reverse** | reverses positions by selected symbol and account |
| **Reverse selected** | reverses all selected positions |
| **CLX** | closes opened positions and cancels orders by selected symbol and account |

### Hot buttons visibility

By default, not all of the available Hot buttons are displayed on Positions panel's toolbar. You can manage visibility of that buttons using the context menu: right-click with your mouse and toggle the desired buttons.

{% hint style="info" %}
Hot buttons are situated on panel's toolbar, so become unavailable once you disable toolbar for specific panel in panel's settings.
{% endhint %}

