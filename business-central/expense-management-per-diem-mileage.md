---
title: Set Up Per Diem and Mileage Allowances
description: Learn how to configure per diem rates, mileage reimbursement, partial day rules, and meal reductions for expense management in Business Central.
author: brentholtorf
ms.topic: how-to
ms.date: 04/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Set up per diem and mileage allowances

Organizations that reimburse travel expenses often use standard per diem rates for meals and lodging and mileage rates for driving. This article explains how to configure these allowances in [!INCLUDE[prod_short](includes/prod_short.md)].

## To configure mileage rates

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Expense Agent Setup**, and then choose the related link.
2. In the **Allowance** section, set the **Standard Rate of Mileage** to your organization's reimbursement rate per distance unit.
3. In the **Default Mileage UOM** field, choose the default unit of measure (for example, miles or kilometers).
4. Turn on **Only Shortest Route** if your policy reimburses only the shortest route between locations.

When an expense user creates a mileage expense, the amount is calculated automatically based on the distance entered and the configured rate.

## To configure per diem rates

Per diem rates reimburse employees for daily travel expenses using a fixed amount instead of requiring individual receipts.

1. On the **Expense Agent Setup** page, in the **Allowance** section, choose the method in the **Full Per-Diem Calculation** field:

    | Method | Description |
    |---|---|
    | **None** | Per diem is not used. |
    | **24-hour Rolling Period** | A full per diem applies for each 24-hour period of travel. |
    | **Overnight Stay** | A full per diem applies when the traveler stays overnight. |

2. Set **Per Diem Rounding Precision** to control decimal rounding on per diem amounts.
3. In **Minimum Hours for Per Diem**, enter the minimum hours of travel required to qualify for a full per diem.

## To configure partial day rules

When travel doesn't cover a full day, partial day rules determine the reimbursement.

1. In the **Partial Day Rules** field, choose how partial days are handled.
2. In **Min Hours for Partial Per Diem**, enter the minimum hours required to qualify for a partial per diem.
3. In **Percentage For Partial Day**, enter the percentage of the full per diem to pay for partial days.

## To configure meal reductions

If meals are provided during travel (for example, at a conference), the per diem amount can be reduced.

1. In the **Reduction for Breakfast %** field, enter the percentage to deduct when breakfast is provided.
2. In the **Reduction for Lunch %** field, enter the percentage to deduct when lunch is provided.
3. In the **Reduction for Dinner %** field, enter the percentage to deduct when dinner is provided.

## How per diem expenses work for users

When an expense user creates a per diem expense:

1. They select a per diem category and choose the travel location.
2. They enter the starting and ending dates and times.
3. The system calculates the per diem amount based on the location rates, travel duration, and any meal reductions.
4. The user can choose the **Per Diem** action to view or edit the calculated entries.

For more information about recording per diem and mileage expenses, see [Create and manage expenses](expense-management-create-expenses.md).

## Related information

[Set up expense management](expense-management-setup.md)  
[Create and manage expenses](expense-management-create-expenses.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
