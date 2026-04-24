---
title: Set Up Per Diem and Mileage Allowances
description: Learn how to configure per diem rates, mileage reimbursement, partial day rules, and meal reductions for expense management in Business Central.
author: brentholtorf
ms.topic: how-to
ms.date: 04/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6974, 6996
---

# Set up per diem and mileage allowances

Organizations that reimburse travel expenses often use standard per diem rates for meals and lodging, and mileage rates for driving. This article explains how to configure these allowances in [!INCLUDE[prod_short](../includes/prod_short.md)].

## Configure mileage rates

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Agent Setup**, and then choose the related link.
2. On the **Allowance** FastTab, set the **Standard Rate of Mileage** to your organization's reimbursement rate per distance unit.
3. In the **Default Mileage UOM** field, choose the default unit of measure. For example, miles or kilometers.

When an expense user creates a mileage expense, the amount is calculated automatically based on the distance entered and the configured rate.

## Configure per diem rates

Per diem rates reimburse employees for daily travel expenses using a fixed amount instead of requiring individual receipts. To learn more about per diem rates, go to [How per diem expenses work for users](#how-per-diem-expenses-work-for-users).

1. On the **Expense Agent Setup** page, on the **Allowance** FastTab, choose the method in the **Full Per-Diem Calculation** field.

    | Method | Description |
    | --- | --- |
    | **None** | Per diem is not used. |
    | **Full Calendar Day** | A full per diem is granted only if the employee is away for an entire calendar day (midnight to midnight). |
    | **24-hour Rolling Period** | A full per diem is calculated for every 24-hour block starting from the trip's beginning. The last day qualifies if it meets or exceeds the minimum hours. |
    | **Overnight Stay** | A full per diem is granted only if the employee spends a night away from home and the travel time meets or exceeds the minimum hours. |

2. In the **Per Diem Rounding Precision** field, enter a number to control decimal rounding on per diem amounts.
3. In the **Minimum Hours for Per Diem** field, enter the minimum hours of travel required to qualify for a full per diem.

## Configure partial day rules

When travel doesn't cover a full day, partial day rules determine the reimbursement.

1. On the **Expense Agent Setup** page, on the **Allowance** FastTab, in the **Partial Day Rules** field, specify how to handle partial days.

    | Option | Description |
    | --- | --- |
    | **Flat Percentage of Full Rate** | A fixed percentage of the full per diem rate is applied. Use with the **Full Calendar Day** calculation method. |
    | **Based on Eligible Hours** | The partial amount is calculated based on the number of qualifying hours. Use with the **24-hour Rolling Period** or **Overnight Stay** methods. The number of hours must meet or exceed the minimum hours for partial per diem. |

2. In **Min Hours for Partial Per Diem**, enter the minimum hours required to qualify for a partial per diem.
3. In **Percentage For Partial Day**, enter the percentage of the full per diem to pay for partial days (used with the flat percentage option).

## Configure meal reductions

If meals are provided during travel, for example, at a conference, the per diem amount can be reduced.

1. On the **Expense Agent Setup** page, on the **Allowance** FastTab, enter the percentage to deduct when breakfast is provided in the **Reduction for Breakfast %** field.
2. In the **Reduction for Lunch %** field, enter the percentage to deduct when lunch is provided.
3. In the **Reduction for Dinner %** field, enter the percentage to deduct when dinner is provided.

## How per diem expenses work for users

When an expense user creates a per diem expense:

1. They select a per diem category and choose the travel location.
2. They enter the starting and ending dates and times.
3. The system calculates the per diem amount based on the location rates, travel duration, and any meal reductions.
4. The user can choose the **Per Diem** action to view or edit the calculated entries.

The per diem detail view shows one line for each day of the trip with the full daily rate. If meals were provided on specific days (for example, dinner included at a conference), the user can mark those meals on the corresponding day. The system recalculates the per diem for that day by applying the configured reduction percentage. This means some days may have a full per diem while others are reduced.

> [!NOTE]
> If the expense uses a foreign currency, [!INCLUDE [prod_short](../includes/prod_short.md)] automatically converts the per diem amount to the local currency using the configured exchange rate.

To learn more about recording per diem and mileage expenses, go to [Create and manage expenses](expense-management-create-expenses.md).

## Related information

[Set up expense management](expense-management-setup.md)  
[Create and manage expenses](expense-management-create-expenses.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
