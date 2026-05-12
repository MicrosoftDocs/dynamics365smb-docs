---
title: Expense and Expense Report Statuses in Expense Agent
description: Learn what each expense and report status means in Expense Agent, and how statuses track your expenses through the workflow.
author: brentholtorf
ms.topic: concept-article
ms.date: 04/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-generated
---

# Understand expense and expense report statuses

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

[!INCLUDE[prod_short](../includes/prod_short.md)] Expense Agent uses statuses to track where each expense and expense report is in the workflow. Knowing what each status means helps you understand what action to take next.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Expense statuses

The following table describes the statuses that an individual expense can have.

| Status | Description |
| --- | --- |
| Processing | The receipt is being scanned and validated. You can't edit the expense yet. |
| Open | The expense is ready for you to review and add to a report. |
| Pending report | The expense is added to a draft report that isn't submitted. |
| Added to report | The expense is part of a submitted report and is moving through the approval workflow. |

## Expense report statuses

The following table describes the statuses that an expense report can have.

| Status | Description |
| --- | --- |
| Draft | The expense report is being prepared. You can add, remove, or edit expenses. |
| Submitted | The expense report is sent for approval. You can't make changes until the reviewer responds. |
| Approved | The reviewer approved the expense report. It's now ready for payment processing. |
| Rejected | The reviewer rejected the expense report. You must edit or remove expenses based on the approver request. |
| Paid | Payment was processed. This status is for reference only—payment is handled outside Expense Agent. |

## Where statuses appear

Several pages show status badges.

| Pages | Description |
| --- | --- |
| Expense list | Each expense shows its current status next to the amount and date. |
| Report list | The dashboard shows expense reports grouped into three tabs: **Drafts**, **Submitted**, and **Approved**. Each tab shows the count of reports in that status. |
| Detail panels | When you open an expense or report, the status appears at the top of the detail view. |

## Related information

[Expense Agent overview](expense-agent-overview.md)  
[Edit expenses in Expense Agent](expense-agent-edit-expenses.md)  
[Create and submit expense reports](expense-agent-expense-reports.md)  
[Approve expense reports](expense-agent-approve-reports.md)  
[Troubleshoot common issues in Expense Agent](expense-agent-troubleshoot.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
