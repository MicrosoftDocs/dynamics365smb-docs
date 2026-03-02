---
title: Configure a week-based calendar
description: Learn how to configure a week based calendar for your Power BI Semantic Models.
author: kennieNP
ms.topic: get-started
ms.search.keywords: analysis, reporting, business intelligence, KPI, installation, administration
ms.date: 02/19/2026
ms.author: kepontop
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Configure a week-based calendar

This article describes how to configure a week-based calendar for your Power BI Semantic Models. You configure your week-based calendar on the **Power BI Reports Setup** page, and your settings flow through to each connected semantic model.

:::image type="content" source="image-6.png" alt-text="Screenshot of a calendar.":::

## Four concepts to consider

Think about your configuration in this order:

1. [Define the Week Structure](#define-the-week-structure).
2. [Define the Fiscal Year Anchor](#define-the-fiscal-year-anchor).
3. [Define the Fiscal Boundary Rule](#define-the-fiscal-boundary-rule).
4. [Define the Period Pattern (445 / 454 / 544)](#define-the-period-pattern-445--454--544).

### Define the week structure

Before you configure fiscal boundaries or 445 patterns, you must first define the week structure on the **Power BI Reports Setup** page by filling in the **First Day of Week** field. The week structure establishes the framework of the calendar.

Treat the **First Day of Week** setting as a foundational configuration that shouldn't change after you start to run reports. Changing the setting afterward:

- Changes historical fiscal year start dates.
- Changes week numbers for all historical data.
- Might change which years contain 53 weeks.
- Can break year-over-year period comparisons.

> [!IMPORTANT]
> Changing the setting in the **First Day of Week** field changes the entire calendar structure.

### Define the fiscal year anchor

The *anchor* is the first day of the month specified in the **First Month of Fiscal Calendar** field on the **Power BI Reports Setup** page. It's the reference point that sets fiscal year boundaries.

In the following example, January is chosen as **First Month of Fiscal Calendar**. Therefore, the anchor for 2026 is **Thursday**, January 1.

:::image type="content" source="image-5.png" alt-text="Screenshot that shows a calendar.":::

> [!IMPORTANT]
> The anchor **isn't** the fiscal year start.

### Define the fiscal boundary rule

If you choose **Weekly** in the **Calendar Type** field, you can use the **Weekly Type** field to set the boundary rule (Nearest or Last). The rule determines how the anchor snaps to the week grid.

1. [Nearest](#nearest-rule): Snap to the closest week boundary.
2. [Last](#last-rule): Snap to the week that has the anchor.

#### Nearest rule

The following example describes how the Nearest rule works. The example assumes that fields are filled in as follows:

- The **Weekly Type** field is set to **Nearest**.
- The **First Month of Fiscal Calendar** field is set to **January**.
- The **First Day of Week** field is set to **Sunday**.

The anchor is Thursday, January 1, 2026.

##### Define the week grid for the Nearest rule

Because the **First Day of Week** field contains **Sunday**, the week grid runs from Sunday to Saturday. So, the week grid containing January 1, 2026 looks like:

| Sunday | Monday | Tuesday | Wednesday | Thursday  | Friday | Saturday |
| :---:  | :---:  | :---:   | :---:     | :---:     | :---:  | :---:    |
| Dec 28 | Dec 29 | Dec 30  | Dec 31    | **Jan 1** | Jan 2  | Jan 3    |

##### Identify the two possible week boundaries

For the anchor (January 1), there are two possible starting points for your fiscal year:

- The previous week starting Sunday, December 28, 2025.
- The next week starting Sunday, January 4, 2026.

The Nearest rule chooses the boundary that's closest to the anchor.

##### Compare distances

The distance from January 1 to December 28 is four days backward. The distance to January 4 is three days forward. Because January 4 is closer, the fiscal year start is January 4, 2026.

#### Last rule

The following example describes how the Last rule works. The example assumes that fields are filled in as follows:

- The **Weekly Type** field is set to **Last**.
- The **First Month of Fiscal Calendar** field is set to **January**.
- The **First Day of Week** field is set to **Sunday**.

The anchor is Thursday, January 1, 2026.

##### Define the week grid for the Last rule

Because **First Day of Week** field contains **Sunday**, the week grid runs from Sunday to Saturday.

- Sunday is day 1
- Monday is day 2
- Tuesday is day 3
- and so on...

##### Find the start of the week containing the anchor

January 1, 2026 is a Thursday, so that week grid looks as follows:

| Sunday | Monday | Tuesday | Wednesday | Thursday  | Friday | Saturday |
| :---:  | :---:  | :---:   | :---:     | :---:     | :---:  | :---:    |
| Dec 28 | Dec 29 | Dec 30  | Dec 31    | **Jan 1** | Jan 2  | Jan 3    |

##### Apply the Last rule

For the Last rule, the fiscal year begins on the first day of the week that contains the anchor date. Because January 1 is in the week that started December 28, the fiscal year starts on **December 28, 2025**.

### Define the period pattern (445/454/544)

The next step is to determine how to group weeks into reporting periods by filling in the **Quarter Week Type** field:

- 445
- 454
- 544

The **Quarter Week Type** field specifies how to group weeks within each quarter. Each quarter contains 13 weeks that are distributed across three fiscal months according to the pattern you select.

| Pattern | Weeks in Month 1 | Weeks in Month 2 | Weeks in Month 3 |
| :---:   | :---:            | :---:            | :---:            |
| 445     | 4                | 4                | 5                |
| 454     | 4                | 5                | 4                |
| 544     | 5                | 4                | 4                |

All three patterns total 13 weeks per quarter (52 weeks per year, before any 53rd week adjustment).

> [!NOTE]
> The **Quarter Week Type** field only affects how you label weeks as fiscal periods, and how you structure reporting periods. The setting doesn't:
>
> - Change when the fiscal year starts.
> - Effect the week grid.
> - Influence the Last or Nearest rule.
> - Determine whether a year has 52 or 53 weeks.

## Related information

[Power BI Subscription Billing app](SRB/analytics/subscription-powerbi-app.md)  
[Overview of subscription billing](SRB/welcome.md)
