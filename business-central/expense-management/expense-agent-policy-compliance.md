---
title: Understand Policy Compliance in Expense Agent
description: Learn how Expense Agent validates expenses against your organization's policies in real time, including soft warnings and hard blocks.
author: brentholtorf
ms.topic: conceptual
ms.date: 04/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# How expense policy compliance works

[!INCLUDE[prod_short](../includes/prod_short.md)]

Expense Agent checks your expenses against your organization's policies so you can catch and fix issues before you submit. Policies are defined by your administrator in [!INCLUDE [prod_short](../includes/prod_short.md)] and are applied automatically as you work with expenses.

## What happens during policy validation

Expense Agent validates your expenses in real time. When you create or edit an expense, the app checks it against the policies your organization has set up. If an expense doesn't meet a policy requirement, you see a notification right away rather than finding out after you submit.

Policy validation also runs when you submit an expense report. The app reviews all expenses in the report and flags any that have issues, so you can address everything before your approver sees the report.

## Soft warnings and hard blocks

Not all policy issues are the same. Expense Agent uses two levels of enforcement:

- **Soft warnings** flag an expense that's outside policy but still lets you proceed. For example, if a meal expense is slightly above the usual limit, you see a warning. You can provide a justification and continue with the submission.
- **Hard blocks** prevent you from submitting until you fix the issue. For example, if a required receipt is missing or an expense category isn't allowed, you must correct the expense before you can submit the report.

> [!TIP]
> When you see a soft warning, add a clear justification. This helps your approver understand the context and speeds up the approval process.

## Where policy status appears

You can see the policy status of your expenses in several places:

- **Expense list** - Each expense shows a policy badge that indicates whether it's compliant, has a warning, or is blocked.
- **Expense details** - Open an expense to see specific policy messages and any justifications you've added.
- **Report summary** - When you open an expense report, the summary shows the overall policy status across all expenses in the report. This gives you a quick way to spot issues before you submit.

## Related information

[Expense Agent overview](expense-agent-overview.md)  
[Upload receipts and create expenses](expense-agent-upload-receipts.md)  
[Edit and manage expenses](expense-agent-edit-expenses.md)  
[Expense and report statuses](expense-agent-statuses.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
