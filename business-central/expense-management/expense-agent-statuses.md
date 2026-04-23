---
title: Expense and Report Statuses in Expense Agent
description: Learn what each expense and report status means in Expense Agent, and how statuses track your expenses through the workflow.
author: brentholtorf
ms.topic: conceptual
ms.date: 04/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Understand expense and report statuses

[!INCLUDE[prod_short](../includes/prod_short.md)] Expense Agent uses statuses to track where each expense and report is in the workflow. Knowing what each status means helps you understand what action to take next.

## Expense statuses

The following table describes the statuses that an individual expense can have.

| Status | Description |
|---|---|
| Processing | The receipt is being scanned and validated. You can't edit the expense yet. |
| Open | The expense is ready for you to review and add to a report. |
| Pending report | The expense is added to a draft report that hasn't been submitted yet. |
| Added to report | The expense is part of a submitted report and is moving through the approval workflow. |

## Expense report statuses

The following table describes the statuses that an expense report can have.

| Status | Description |
|---|---|
| Draft | The report is being prepared. You can add, remove, or edit expenses. |
| Submitted | The report is sent for approval. You can't make changes until the reviewer responds. |
| Approved | The reviewer approved the report. It's now ready for payment processing. |
| Paid | Payment was processed. This status is for reference only—payment is handled outside Expense Agent. |

## Where statuses appear

You can see status badges in several places:

- **Expense list** — Each expense shows its current status next to the amount and date.
- **Report list** — The dashboard shows expense reports grouped into three tabs: **Drafts**, **Submitted**, and **Approved**. Each tab shows the count of reports in that status.
- **Detail panels** — When you open an expense or report, the status appears at the top of the detail view.

## Related information

- [Expense Agent overview](expense-agent-overview.md)
- [Edit expenses in Expense Agent](expense-agent-edit-expenses.md)
- [Create and submit expense reports](expense-agent-expense-reports.md)
- [Approve expense reports](expense-agent-approve-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
