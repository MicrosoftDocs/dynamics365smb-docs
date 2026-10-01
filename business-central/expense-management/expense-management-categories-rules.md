---
title: Set Up Expense Categories, Rules, and Policies
description: Learn how to create expense categories, subcategories, groups, rules, and AI-evaluated policies that control employee expenses in Business Central.
author: jswymer
ms.topic: how-to
ms.date: 09/25/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: Primary_6945, Primary_7127, 6900, 6901, 6920, 6930, 6937, 6945, 6946, 6952, 6973
ai-usage: ai-assisted
---

# Create expense categories, rules, and policies

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Expense categories, subcategories, and groups classify expenses for reporting and processing. Expense rules validate expenses against predefined conditions, while expense policies use AI to evaluate natural-language guidelines. This article explains how to set up these features in [!INCLUDE[prod_short](../includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Create expense categories

An expense category represents a type of expense or allowance, such as meals, travel, office supplies, per diem, or mileage. Configure each category with its own posting group, default payment method, and specific requirements for additional details. 

To further refine classification, use expense subcategories within each category. Subcategories provide a more granular distinction and improve reporting clarity and policy readiness. For categories configured for itemization, subcategories are required.  

To create the **Expense Category**, follow these steps:

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Categories**, and then choose the related link.
1. Choose **New** to create a category, or open an existing one to modify its setup.
1. Fill in the following fields:

    | Field | Description |
    | --- | --- |
    | **Code** | A short code that identifies the category. |
    | **Description** | Specifies the meaning and usage of this category for Expense Agent. Provide a detailed explanation because Expense Agent relies on this description for accurate classification. Maximum 250 characters. Learn more in [Write descriptions that help Expense Agent categorize receipts](#write-descriptions-that-help-expense-agent-categorize-receipts). |
    | **Posting Description** | A short description of the category used for posting. |
    | **Posting Group** | The posting group used for general ledger accounting. Links the category to the appropriate G/L accounts. |
    | **Withholding Selection Mode** | Indicates whether the category is configured for a **Single Tax** or a **Tax Group** for employee withholding tax. Learn more in [Configure withholding tax for a category](#configure-withholding-tax-for-a-category). |
    | **Withholding Tax Prod. Post. Group** | Specifies the product posting group that is copied to a general journal line when the expense category is selected. This field is required for both withholding selection modes. |
    | **Withholding Group Code** | Specifies the withholding tax group to use when **Withholding Selection Mode** is **Tax Group**. |
    | **Default Payment Method** | The default expense payment method for expenses in this category. For example, **Cash** (employee paid personally), **Credit Card** (company-issued card), or **Company Paid** (paid directly by the company). Users can still change this setting per expense. Learn more in [Set up expense payment methods](expense-management-setup.md#set-up-expense-payment-methods). |
    | **Attachment Enforcement** | Specifies whether an attachment (receipt) is required when submitting expenses in this category. |
    | **Refundable** | Specifies whether expenses in this category are eligible for reimbursement according to company policy. Learn more in [Control whether expenses are refundable](#control-whether-expenses-are-refundable). |
    | **Expense Detail Required** | Specifies what level of detail is required. Options: **None**, **Itemize** requires itemization using subcategories, **Participants** requires adding guests, **Per Diem** requires location and travel dates, or **Mileage** requires distance. |
    | **Expense Group** | Groups similar categories for reporting and analysis. |
    | **Prepayment-Cash Advance** | Specifies whether the category requires or supports prepayments or cash advances. |
    | **VAT Prod. Posting Group** | Specifies the VAT product posting group used with the default VAT business posting group to determine how VAT is calculated and posted. This field is shown on the **Expense Categories** page when VAT reclaim is enabled. |
    | **Default VAT %** | Specifies the default VAT percentage for VAT specification lines in this category. |
    | **Default VAT Reclaim %** | Specifies the percentage of the VAT amount suggested for reclaim when an expense is added to a report. An accountant must approve or reject the suggestion before posting. |
    | **Inactive** | Marks the category as inactive. Inactive categories can't be used for new expenses. |

1. To add **Expense Subcategories** for a specific category, select the category you want and choose the **Subcategories** action. Create entries for more specific classifications.

### Write descriptions that help Expense Agent categorize receipts

Expense Agent uses the category description to categorize information extracted from receipts. Clearly explain the category's primary purpose and include enough detail to distinguish it from similar categories.

For example:

- **Hotel stays**: *Expenses for hotel and accommodation stays related to business travel. Includes room charges, mandatory hotel fees, city or tourist taxes, and services charged to the room during the stay.*
- **Air travel**: *Expenses for commercial air travel, including airline tickets and airfare. Covers flights, passenger names, routes, carriers, booking references, fares, taxes, seat selection, baggage or change fees, and boarding passes.*

### Configure withholding tax for a category

> [!NOTE]
> The **Expense Withholding Tax** extension adds withholding tax fields and processing to Expense Agent. The extension requires both the **Expense Agent (Preview)** and **Withholding Tax** extensions.

The category's withholding tax product posting group must have a matching setup for the employee's withholding tax business posting group. Learn more in [Set up and post employee withholding tax](../finance-withholding-tax-employees.md).

### Control whether expenses are refundable

A refundable expense is one that your organization can accept and reimburse according to its internal policy. Turn off **Refundable** for categories that represent nonbusiness or other nonallowable expenses. This setting helps identify nonrefundable expenses early in the process.

## Create expense subcategories

Each expense category can include one or more subcategories. Subcategories are especially important when itemization is required, because they let users break down a single receipt into multiple types of charges (for example, a hotel stay versus a minibar charge).

1. Open or select the **Expense Category** you want to add subcategories to.
1. Choose the **Subcategories** action.
1. Add lines for each subcategory and complete the following fields:

    | Field | Description |
    | --- | --- |
    | **Code** | A short code that identifies the subcategory. |
    | **Description** | Specifies the meaning and usage of this subcategory for the Expense Agent. Provide a detailed explanation, as the agent relies on this description for accurate classification. Maximum 250 characters. |
    | **Posting Description** | A short description of the subcategory used for posting. |
    | **Expense Description Mandatory** | Requires users to enter a custom description. Standard descriptions can't be used when this toggle is turned on. |
    | **Refundable** | Specifies whether the subcategory is refundable by default. Useful when itemizing because some parts of a receipt might be refundable while others aren't. |
    | **VAT Prod. Posting Group** | Specifies the VAT product posting group for this subcategory. This value overrides the category value for the VAT specification line. |
    | **Default VAT %** | Specifies the VAT percentage suggested for VAT specification lines in this subcategory. |
    | **Default VAT Reclaim %** | Specifies the percentage of the VAT amount suggested for reclaim when an expense is added to a report. An accountant must approve or reject the suggestion before posting. |
    | **Inactive** | Marks the subcategory as inactive. |

> [!NOTE]
> Each subcategory can be configured as refundable or non-refundable. Even if the main category is marked as refundable, it doesn't guarantee that all expense lines are compliant. Subcategories allow accurate calculation of refundable and non-refundable amounts. 

## Configure VAT defaults for categories

When VAT reclaim is enabled, category and subcategory setup provides defaults for VAT specification lines. A subcategory can override the category's VAT product posting group, VAT percentage, and reclaim percentage.

During initial setup, the **Apply default settings** action assigns VAT defaults to supported categories and subcategories based on the country or region in **Company Information**. The generated setup uses a 100 percent reclaim percentage for categories and subcategories that have a nonzero VAT rate.

To use different VAT treatment for a subcategory:

1. On the **Expense Categories** page, select the category, and then choose **Subcategories**.
1. Fill in the **VAT Prod. Posting Group**, **Default VAT %**, and **Default VAT Reclaim %** fields for each subcategory that requires different VAT treatment.

The defaults provide the initial calculation. They don't approve the reclaim. An accountant reviews each VAT specification line on the expense report and makes the final reclaim decision.

To enable the feature and set the default VAT business posting group, see [Set up VAT reclaim](expense-management-setup.md#set-up-vat-reclaim).

## Set up expense locations

Expense locations define the geographic areas used for calculating per diem allowances. A simple country or region definition often isn't enough because daily rates can vary due to differences in purchasing power or travel policies. Expense locations let you define country or regional, or city-level areas with distinct per diem rates. 

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Locations**, and then select the related link.
1. Choose **New** or open an existing location to modify it.
1. Fill in the following fields:

    | Field | Description |
    | --- | --- |
    | **No.** | The identifier of the location or area. |
    | **Country/Region Code** | The country or region the location belongs to. Required. |
    | **City** | The city, for more granular definitions. Optional. |
    | **State** | The state or province, if relevant. Optional. |

When configured, you can use these locations in per diem calculations and reference them in expense management rules.

## Set up expense groups

Expense groups let you group categories for reporting and analysis.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Groups**, and then select the related link.
1. Choose **New** and enter a code and description for each group.

## Create expense rules

Expense rules define conditions that expenses must meet based on category and location. Rules can require justification, restrict merchants, or enforce amount limits.

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Expense Management Rules**, and then choose the related link.
1. Choose **New** to open the **Expense Rule Card** page.
1. Fill in the following fields:

    | Field | Description |
    | --- | --- |
    | **Expense Category Code** | The category this rule applies to. |
    | **Expense Location** | The location this rule applies to. Leave blank to apply to all locations. |
    | **Effective Date** | The date when this rule takes effect. |
    | **Justification Required** | Specifies when justification is required for expenses under this rule. |
    | **Currency Code** | The required currency. Leave blank to allow any currency. |
    | **Unit of Measure Code** | The required unit of measure for mileage expenses. Leave blank to allow any unit. |

1. On the **Merchant Requirements** FastTab, turn on the **Required Specific Merchant** toggle if only a specific vendor is allowed, and then enter the merchant name. Use this setting when your company has contracts with vendors and doesn't allow alternatives.
1. On the **Rule Conditions** FastTab, add one or more conditions. For each condition, choose a **Condition Type** and enter a **Value**:

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

To enable rule enforcement, turn on **Apply Rules** on the **Expense Agent Setup** page. If you don't turn on this setting, rules aren't applied. The exception is per diem calculations, which are always considered.

When you turn on rules, [!INCLUDE [prod_short](../includes/prod_short.md)] automatically checks expenses against the matching rules. If an expense violates a rule, the violation appears in the **Rule Violations** FactBox on the expense card and the expense report. Violations don't block submission, but they're visible to approvers.

### Compare rules and policies

Expense management distinguishes between *rules* and *policies*:

- **Rules** are measurable conditions that Business Central checks deterministically. For example, a rule might set a maximum amount for a meal expense or require justification for amounts above a threshold.
- **Policies** are natural-language conditions that describe expected business behavior and are evaluated using AI. For example, a policy might specify when employees can book business class flights, what hotel star rating is allowed, or whether to permit alcohol at a business lunch. During approval, approvers can review policy evaluation results alongside the rules compliance status.

Assign policies to expense categories and configure them through the **Expense Policies** page. Before Expense Agent can evaluate policies, an administrator must [configure AI-assisted policy evaluation](expense-management-setup.md#configure-ai-assisted-policy-evaluation).

## Create and manage expense policies

Use the **Expense Policies** page to define natural-language policies that apply to expense reports.

You need the **Expense Management - Admin** permission set or equivalent custom permissions to create or change policies. The **Expense Management - Read** permission set lets users view policies but not change them.

1. [!INCLUDE [open-search](../includes/open-search.md)], enter **Expense Policies**, and then select the related link.
1. Select **New** to create a policy.
1. Fill in the following fields:
   - **Expense Category Code**: Select the category this policy applies to, or leave the field blank to apply the policy to all categories.
   - **Description**: Enter a short name for the policy. The description can contain up to 50 characters.
   - **Policy Text**: Enter the full policy in natural language. The policy can contain up to 2,048 characters. For example, "Business class flights are approved only for international trips over 4 hours."
   - **Enabled**: Turn on this toggle to include the policy in evaluations.
1. Select **OK** to save the policy.

When you change a policy, earlier evaluation results can become outdated. Affected expenses show **Policies pending** until Expense Agent finishes a current evaluation.

> [!TIP]
> Keep policy text clear and specific. The AI evaluates expenses using natural language, so policies written in plain business language work better than highly technical or ambiguous language.

To learn how Expense Agent evaluates policies and reports compliance statuses, go to [How expense policy and rules compliance work](expense-agent-policy-compliance.md).

## Next steps

[Create and manage expenses](expense-management-create-expenses.md)

## Related information

[Set up expense management](expense-management-setup.md)  
[Manage employee expenses](expense-management-overview.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]