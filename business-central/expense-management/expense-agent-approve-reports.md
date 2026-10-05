---
title: Approve or Send Back Expense Reports
description: Learn how to review submitted expense reports and policy results, then approve them or send them back with comments in Expense Agent.
author: jswymer
ms.topic: how-to
ms.date: 10/02/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-assisted
ms.update-cycle: 180-days
ms.collection:
  - bap-ai-copilot
---

# Approve or send back expense reports

[!INCLUDE [online_only](../includes/online_only.md)]

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

As an approver, you review expense reports that employees submit. You can approve a report to move it forward in the process, or send it back to the employee with comments if something needs attention.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Review a submitted expense report

1. Open Expense Agent and go to the **For My Approval** tab.
1. Select the expense report you want to review.
1. Review the report lines, including amounts, categories, and any attached receipts.
1. If the report shows a compliance warning, select the warning to open **These expenses need your review**. Select an expense to open its details, and then review the status and policy issue explanations in the **Summary** section.

> [!TIP]
> The report-level compliance warning appears only when one or more expenses need attention. When all expenses are compliant, the warning isn't shown to approvers.

## Approve an expense report

1. Open the submitted expense report.
1. Review the report lines and any compliance warnings.
1. Select **Approve**.
1. In the confirmation dialog, review the expense count and total amount, and then select **Approve**.

The report status changes to **Approved**, and the employee is notified.

## Approve a report with policy issues

Policy flags are advisory and don't prevent an approver from approving a report. Review each flagged expense and its explanation before deciding whether to approve the report or send it back.

1. Open the submitted expense report.
1. Select the compliance warning to open **These expenses need your review**, and then review the affected expenses.
1. Select **Approve**.
1. If a warning says that one or more policy evaluations aren't current, choose whether to continue with approval or cancel and wait for current results.

Approving the report doesn't remove or change its policy issue information.

## Send back an expense report

If a report has issues that the employee needs to fix, you can send it back with comments that explain what needs to change.

1. Open the submitted expense report.
1. Select **Send back**.
1. In the **Send back** dialog, enter your comments in the **Comment for submitter** field. Be specific about which expenses need attention and why.
1. Select **Send back**.

The report status changes back to **Draft**, and the employee is notified with your comments. They can make changes and resubmit.

> [!NOTE]
> Approval workflows are configured and managed in [!INCLUDE [prod_short](../includes/prod_short.md)]. Contact your administrator if you have questions about approval rules or workflow settings.

## Related information

[Expense Agent overview](expense-agent-overview.md)  
[Create and submit expense reports](expense-agent-expense-reports.md)  
[How expense policy compliance works](expense-agent-policy-compliance.md)  
[Troubleshoot common issues in Expense Agent](expense-agent-troubleshoot.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
