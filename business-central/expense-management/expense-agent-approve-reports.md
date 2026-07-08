---
title: Approve or Send Back Expense Reports
description: Learn how to review submitted expense reports and either approve them or send them back with comments in Expense Agent.
author: brentholtorf
ms.topic: how-to
ms.date: 04/15/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-assisted
---

# Approve or send back expense reports

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

As an approver, you review expense reports that employees submit. You can approve a report to move it forward in the process, or send it back to the employee with comments if something needs attention.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Review a submitted expense report

1. Open Expense Agent and go to the **For My Approval** tab.
1. Select the expense report you want to review.
1. Review the report lines, including amounts, categories, and any attached receipts.
1. Check the policy compliance summary for warnings or issues.

> [!TIP]
> Select an individual expense line to see its full details, including the receipt image and any policy notes.

## Approve an expense report

1. Open the submitted expense report.
1. Review the report lines and policy summary.
1. Select **Approve**.

The report status changes to **Approved**, and the employee is notified.

## Send back an expense report

If a report has issues that the employee needs to fix, you can send it back with comments that explain what needs to change.

1. Open the submitted expense report.
1. Select **Send Back**.
1. In **Request clarification**, enter your comments in the **Add comments** field. Be specific about which expenses need attention and why.
1. Select **Send back**.

The report status changes back to **Draft**, and the employee is notified with your comments. They can make changes and resubmit.

> [!NOTE]
> Approval workflows are configured and managed in [!INCLUDE [prod_short](../includes/prod_short.md)]. Contact your administrator if you have questions about approval rules or workflow settings.

## Next steps

- [Expense Agent overview](expense-agent-overview.md)  

## Related information

[Expense Agent overview](expense-agent-overview.md)  
[Create and submit expense reports](expense-agent-expense-reports.md)  
[How expense policy compliance works](expense-agent-policy-compliance.md)  
[Troubleshoot common issues in Expense Agent](expense-agent-troubleshoot.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
