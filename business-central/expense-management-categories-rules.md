---
title: Set Up Expense Categories and Rules
description: Learn how to create expense categories, subcategories, locations, and policy rules that control what expenses employees can submit in Business Central.
author: brentholtorf
ms.topic: how-to
ms.date: 04/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Set up expense categories and rules

Expense categories classify the types of expenses employees can submit. Expense rules enforce your organization's spending policies automatically. This article explains how to set up both in [!INCLUDE[prod_short](includes/prod_short.md)].

## To create expense categories

An *expense category* represents a type of expense, such as meals, travel, or office supplies. Each category can have its own posting group, payment method, and detail requirements.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Expense Categories**, and then choose the related link.
2. Choose **New** to create a category.
3. Fill in the following fields:

    | Field | Description |
    |---|---|
    | **Code** | A short code that identifies the category. |
    | **Description** | A description of the category. |
    | **Posting Group** | The posting group used for general ledger accounting. |
    | **Default Payment Method** | The default payment method for expenses in this category. |
    | **Refundable** | Specifies whether expenses in this category are eligible for reimbursement. |
    | **Expense Detail Required** | Specifies what detail is required, such as itemization, participants, per diem, or mileage. |

4. To add subcategories, choose the **Subcategories** action and create entries for more specific classifications.

## To set up expense locations

Expense locations are used with per diem allowances and expense rules. They represent travel destinations where spending policies may differ.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Expense Locations**, and then choose the related link.
2. Choose **New** and enter a code and description for each location.

## To set up expense groups

Expense groups let you group categories for reporting and analysis.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Expense Groups**, and then choose the related link.
2. Choose **New** and enter a code and description for each group.

## To create expense rules

Expense rules define conditions that expenses must meet based on category and location. Rules can require justification, restrict merchants, or enforce amount limits.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Expense Management Rules**, and then choose the related link.
2. Choose **New** to open the **Expense Rule Card**.
3. Fill in the following fields:

    | Field | Description |
    |---|---|
    | **Expense Category Code** | The category this rule applies to. |
    | **Expense Location** | The location this rule applies to. Leave blank to apply to all locations. |
    | **Effective Date** | The date when this rule takes effect. |
    | **Justification Required** | Specifies when justification is required for expenses under this rule. |
    | **Currency Code** | The required currency. Leave blank to allow any currency. |
    | **Unit of Measure Code** | The required unit of measure for mileage expenses. Leave blank to allow any unit. |

4. In the **Merchant Requirements** section, turn on **Required Specific Merchant** if only a specific vendor is allowed, and enter the merchant name.
5. In the **Rule Conditions** section, add conditions that define thresholds or limits for expenses.

> [!TIP]
> You can create multiple rules for the same category with different locations and effective dates. The system applies the most specific matching rule.

## To set up expense payment methods

Payment methods define how expenses were paid, such as cash, credit card, or company card.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Expense Payment Methods**, and then choose the related link.
2. Choose **New** and create entries for each payment method your organization uses.

## How rules are applied

When you turn on **Use Rules** in the **Expense Agent Setup** page, the system automatically checks expenses against the matching rules. If an expense violates a rule, the violation appears in the **Rule Violations** factbox on the expense card and the expense report. Violations don't block submission, but they're visible to approvers.

## Related information

[Set up expense management](expense-management-setup.md)  
[Create and manage expenses](expense-management-create-expenses.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
