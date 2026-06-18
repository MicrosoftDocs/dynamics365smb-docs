---
title: Understand Policy Compliance in Expense Agent
description: Learn how Expense Agent validates expenses against your organization's policies in real time, including soft warnings and hard blocks.
author: brentholtorf
ms.topic: concept-article
ms.date: 04/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-assisted
---

# How expense policy and rules compliance work

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Expense Agent checks your expenses against your organization's rules and policies so you can catch and fix issues before you submit. Rules are defined by your administrator in **Expense Management Rules** in [!INCLUDE [prod_short](../includes/prod_short.md)] and are applied automatically as you work with expenses. 

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## What happens during rule validation

Expense Agent validates your expenses in real time. When you create or edit an expense, the app checks it against the rules your organization set-up. If an expense doesn't meet a rule requirement, you see a notification right away rather than finding out after you submit.

Rule validation also runs when you submit an expense report. The app reviews all expenses in the report and flags any that have issues, so you can address everything before your approver sees the report.

## Soft warnings and hard blocks

Not all rule issues are the same. Expense Agent uses two levels of enforcement:

- **Soft warnings** flag an expense that's outside rule or policy but still lets you proceed. For example, if a meal expense is slightly above the usual limit, you see a warning. You can provide a justification and continue with the submission.
- **Hard blocks** prevent you from submitting until you fix the issue. For example, if a required receipt is missing or an expense category isn't allowed, you must correct the expense before you can submit the report.

> [!TIP]
> When you get a soft warning, add a clear justification in the **Purpose/Notes** field in the **Categorization** tab in web app. This information can help your approver understand the context and speeds up the approval process.

## Policy validation

Rule validation is performed proactively for individual expenses, while policy validation is executed after the expense report was submitted. This separation ensures that:

- Some controls apply at the individual expense line level  
- Some controls apply to the entire expense report  
- Certain validations depend on the relationship between multiple expense lines  

Policy validation supports approvers by providing more context to review both the overall report and the individual expenses it contains.

> [!NOTE]  
> Policy validation isn't yet available and is planned for release in version 28.3.

### Policies vs. Rules

**Expense Management Rules** enforce strict, measurable constraints. They typically rely on defined thresholds or conditions and might:

- Enforce maximum or recommended spending limits  
- Require justification for amounts exceeding defined thresholds  
- Restrict or disallow specific types of expenses  
- Enforce the use of specific merchants or providers  

**Expense Policies**, in contrast, define expected behavior using natural language. They provide guidance that isn't always tied to specific amounts, such as:

- When employees might use business class travel
- What is appropriate for business meals  
- Acceptable hotel standards and conditions for exceptions, and so on  

## Where the rule status appears

You can see the expense rule status of your expenses in several places:

- **Expense list** - Each expense shows a policy badge that indicates whether it's compliant, has a warning, or is blocked.
- **Expense details** - Open an expense to review specific policy messages and any justifications you added.
- **Report summary** - When you open an expense report, the summary shows the overall policy status across all expenses in the report. This summary gives you a quick way to spot issues before you submit.

## Related information

[Expense Agent overview](expense-agent-overview.md)  
[Upload receipts and create expenses](expense-agent-upload-receipts.md)  
[Edit and manage expenses](expense-agent-edit-expenses.md)  
[Expense and report statuses](expense-agent-statuses.md)  
[Troubleshoot common issues in Expense Agent](expense-agent-troubleshoot.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
