---
title: Set Up Expense Categories and Rules
description: Learn how to create expense categories, subcategories, locations, and policy rules that control what expenses employees can submit in Business Central.
author: brentholtorf
ms.topic: how-to
ms.date: 04/22/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 6900, 6901, 6920, 6930, 6937, 6945, 6946, 6952, 6973
---

# Set up expense categories and rules

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Expense categories classify the types of expenses employees can submit. Expense rules enforce your organization's spending policies automatically. This article explains how to set up both in [!INCLUDE[prod_short](../includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Set up expense payment methods

Payment methods define how expenses were paid, such as cash, credit card, or company card.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Payment Methods**, and then choose the related link.
2. Choose **New** and create entries for each payment method your organization uses.

## Create expense categories

An expense category represents a type of expense, such as meals, travel, or office supplies. Each category can have its own posting group, payment method, and detail requirements.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Categories**, and then choose the related link.
2. Choose **New** to create a category, or open an existing one to modify its setup.
3. Fill in the following fields:

    | Field | Description |
    | --- | --- |
    | **Code** | A short code that identifies the category. |
    | **Description** | A description of the category. |
    | **Posting Group** | The posting group used for general ledger accounting. Links the category to the appropriate G/L accounts. |
    | **Default Payment Method** | The default expense payment method for expenses in this category. For example, **Cash** (employee paid personally), **Credit Card** (company-issued card), or **Company Paid** (paid directly by the company). Users can still change this setting per expense. To learn more about payment methods, go to [Set up expense payment methods](#set-up-expense-payment-methods). |
    | **Attachment Enforcement** | Specifies whether an attachment (receipt) is required when submitting expenses in this category. |
    | **Refundable** | Specifies whether expenses in this category are eligible for reimbursement according to company policy. |
    | **Expense Detail Required** | Specifies what level of detail is required. Options: **None**, **Itemize** requires itemization using subcategories, **Participants** requires adding guests, **Per Diem** requires location and travel dates, or **Mileage** requires distance. |
    | **Expense Group** | Groups similar categories for reporting and analysis. |
    | **Prepayment-Cash Advance** | Specifies whether the category requires or supports prepayments or cash advances. |
    | **Inactive** | Marks the category as inactive. Inactive categories can't be used for new expenses. |

4. To add subcategories, choose the **Subcategories** action and create entries for more specific classifications.

> [!NOTE]
> A refundable expense is one the company can accept and reimburse according to internal policy. Because employees might occasionally submit nonbusiness expenses, the **Refundable** toggle helps identify and restrict nonallowable items early in the process.

## Create expense subcategories

Each expense category can include one or more subcategories. Subcategories are especially important when itemization is required, because they let users break down a single receipt into multiple types of charges (for example, a hotel stay versus a minibar charge).

1. Open the **Expense Category** you want to add subcategories to.
2. Choose the **Subcategories** action.
3. Add lines for each subcategory and complete the following fields:

    | Field | Description |
    | --- | --- |
    | **Code** | A short code that identifies the subcategory. |
    | **Description** | A description of the subcategory. |
    | **Expense Description Mandatory** | Requires users to enter a custom description. Standard descriptions can't be used when this toggle is turned on. |
    | **Refundable** | Specifies whether the subcategory is refundable by default. Useful when itemizing because some parts of a receipt might be refundable while others aren't. |
    | **Inactive** | Marks the subcategory as inactive. |

## Set up expense locations

Expense locations define the geographic areas used for calculating per diem allowances. A simple country/region definition is often not enough because daily rates can vary due to differences in purchasing power or travel policies. Expense locations let you define country/regional, or city-level areas with distinct per diem rates.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Locations**, and then choose the related link.
2. Choose **New** or open an existing location to modify it.
3. Fill in the following fields:

    | Field | Description |
    | --- | --- |
    | **No.** | The identifier of the location or area. |
    | **Country/Region Code** | The country or region the location belongs to. Required. |
    | **City** | The city, for more granular definitions. Optional. |
    | **State** | The state or province, if relevant. Optional. |

When configured, you can use these locations in per diem calculations and reference them in expense management rules.

## Set up expense groups

Expense groups let you group categories for reporting and analysis.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Groups**, and then choose the related link.
2. Choose **New** and enter a code and description for each group.

## Create expense rules

Expense rules define conditions that expenses must meet based on category and location. Rules can require justification, restrict merchants, or enforce amount limits.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Management Rules**, and then choose the related link.
2. Choose **New** to open the **Expense Rule Card** page.
3. Fill in the following fields:

    | Field | Description |
    | --- | --- |
    | **Expense Category Code** | The category this rule applies to. |
    | **Expense Location** | The location this rule applies to. Leave blank to apply to all locations. |
    | **Effective Date** | The date when this rule takes effect. |
    | **Justification Required** | Specifies when justification is required for expenses under this rule. |
    | **Currency Code** | The required currency. Leave blank to allow any currency. |
    | **Unit of Measure Code** | The required unit of measure for mileage expenses. Leave blank to allow any unit. |

4. On the **Merchant Requirements** FastTab, turn on the **Required Specific Merchant** toggle if only a specific vendor is allowed, and then enter the merchant name. Use this setting when your company has contracts with vendors and doesn't allow alternatives.
5. On the **Rule Conditions** FastTab, add one or more conditions. For each condition, choose a **Condition Type** and enter a **Value**:

    | Condition type | Description |
    |---|---|
    | **None** | No condition applies. |
    | **Fix Amount** | Only the exact amount specified in **Value** is allowed. |
    | **Max Amount** | The amount in **Value** is the maximum permitted. |
    | **Min Amount** | The amount in **Value** is the minimum permitted. |
    | **At Least Justification Needed** | Amounts above the **Value** require justification. |
    | **Daily Rate** | Used for per diem daily rates. Requires an expense location on the rule. |

> [!TIP]
> You can create multiple rules for the same category with different locations and effective dates. [!INCLUDE [prod_short](../includes/prod_short.md)] applies the most specific matching rule.

### How rules are applied

To enable rule enforcement, turn on **Apply Rules** on the **Expense Agent Setup** page. If this setting isn't turned on, rules aren't applied. The exception is per diem calculations, which are always considered.

When rules are enabled, [!INCLUDE [prod_short](../includes/prod_short.md)] automatically checks expenses against the matching rules. If an expense violates a rule, the violation appears in the **Rule Violations** FactBox on the expense card and the expense report. Violations don't block submission, but they're visible to approvers.

### Rules versus policies

Expense management distinguishes between *rules* and *policies*:

- **Rules** are amount-based conditions that require exact accuracy. For example, a rule might set a maximum amount for a meal expense or require justification for amounts above a threshold. Rules are stored in Business Central tables and are enforced automatically. Rules are available now.
- **Policies** are language-based conditions that describe expected behavior. For example, a policy might specify:

   - When employees can book business class flights.
   - What hotel star rating is allowed.
   - Whether to permit alcohol at a business lunch.

Policies use AI to evaluate compliance and are part of the full approval experience.

> [!NOTE]
> Policies are a planned capability and aren't yet available in the current release. Rules are fully implemented and available today.

## Next steps

[Create and manage expenses](expense-management-create-expenses.md)

## Related information

[Set up expense management](expense-management-setup.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
