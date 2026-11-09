---
title: Approve Expense Reports and Travel Requests
description: Review expense reports, policy results, and planned travel in Expense Agent. Approve reports and travel requests or send them back with comments.
author: jswymer
ms.topic: how-to
ms.date: 11/04/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ai-usage: ai-assisted
ms.update-cycle: 180-days
ms.collection:
  - bap-ai-copilot
---

# Approve or send back expense reports and travel requests

[!INCLUDE [online_only](../includes/online_only.md)]

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

As an approver, you review expense reports that employees submit. In the web app, you can approve a report or send it back to the employee with comments if something needs attention. For reports that require interim approval, use [!INCLUDE[prod_short](../includes/prod_short.md)] instead, as described in [Understand interim approval](#understand-interim-approval).

When the connected Business Central environment supports travel requests, you also review planned trips in the same approval queue. A travel request asks for approval before spending. An expense report asks for approval of the actual expenses.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Review a submitted expense report

1. Open Expense Agent and go to the **For my approval** tab.
1. Select the expense report you want to review.
1. Review the report lines, including amounts, categories, and any attached receipts.
1. If the report shows a compliance warning, select the warning to open **These expenses need your review**. Select an expense to open its details, and then review the status and policy issue explanations in the **Summary** section.

> [!TIP]
> The report-level compliance warning appears only when one or more expenses need attention. When all expenses are compliant, the warning isn't shown to approvers.

## Understand interim approval

Interim approval adds a review step before final approval. When you enable Expense Agent, you can assign an interim approver in [!INCLUDE[prod_short](../includes/prod_short.md)] after the report is submitted. The interim approver must be different from the report's expense user and the final approver.

> [!IMPORTANT]
> The web and mobile apps don't currently support the complete interim approval flow. Assign interim approvers and complete both approval stages in [!INCLUDE[prod_short](../includes/prod_short.md)]. The web app procedures in this article apply to reports without an interim approver.

In [!INCLUDE[prod_short](../includes/prod_short.md)], a report with an interim approver follows this flow:

1. The report is submitted and waits for the interim approver.
1. The interim approver reviews the report and selects **Approve**.
1. The report status changes to **Interim Approved** and waits for the final approver.
1. The final approver reviews the report and selects **Approve**.
1. The report status changes to **Approved**.

The interim approver can't give final approval. After the report has the **Interim Approved** status, only the current final approver can approve or reject it. Learn how to assign an interim approver and process both stages in [Review and approve expense reports](expense-management-approve-reports.md).

## Approve an expense report

1. Open the submitted expense report.
1. Review the report lines and any compliance warnings.
1. Select **Approve**.
1. In the confirmation dialog, review the expense count and total amount, and then select **Approve**.

For a report without an interim approver, approval changes the status to **Approved**, and the employee is notified. After final approval, the report moves from the employee's **Submitted** tab to their **Approved** tab. Interim approval alone doesn't complete approval or make the report ready for posting.

## Approve a report with policy issues

Policy flags are advisory and don't prevent an approver from approving a report. Review each flagged expense and its explanation before deciding whether to approve the report or send it back.

1. Open the submitted expense report.
1. Select the compliance warning to open **These expenses need your review**, and then review the affected expenses.
1. Select **Approve**.
1. If a warning says that one or more policy evaluations aren't current, choose whether to continue with approval or cancel and wait for current results.

Approving the report doesn't remove or change its policy issue information. The policy evaluation entry from submission stays in the report's activity timeline, so it's still available for reference after you approve and the report is posted. For instructions, go to [Review your approval history](#review-your-approval-history).

## Send back an expense report

If a report has issues that the employee needs to fix, you can send it back with comments that explain what needs to change.

1. Open the submitted expense report.
1. Select **Send back**.
1. In the **Send back** dialog, enter your comments in the **Comment for submitter** field. Be specific about which expenses need attention and why.
1. Select **Send back**.

The report status changes back to **Draft**, and the employee can review your comments in the app, make changes, and resubmit. They also receive an email notification if outgoing email and approval notifications are configured.

Administrators configure outgoing email and approval notifications through **Configure Expense Agent**. Learn more in [Configure notification settings](expense-management-setup.md#configure-notification-settings).

For a report with an interim approver, use [!INCLUDE[prod_short](../includes/prod_short.md)] for approval decisions. After corrections and resubmission, the report returns to the assigned interim approver if that approver is still eligible. Final approval is required again.

> [!NOTE]
> Approval workflows are configured and managed in [!INCLUDE [prod_short](../includes/prod_short.md)]. Contact your administrator if you have questions about approval rules or workflow settings.

## Review and decide on a travel request

Travel requests appear alongside expense reports in **For my approval** in the web app or **Approvals** in the mobile app. You need an internet connection and access to the company to approve or send back a request.

1. Open the approval queue and select the travel request.
1. Review its purpose, expected dates, travelers, estimated costs, and any per diem details. If the employee resubmitted the request with a reply, review that reply as well.
1. Select **Approve** to approve the trip, or select **Send back** to request changes.
1. If you send the request back, enter a comment explaining what needs to change and confirm **Send back**. If an approval confirmation is shown, review the estimated total and confirm **Approve**.

Approval changes the request to **Approved**. Business Central creates linked expense reports for the travelers. Sending the request back makes it editable again and preserves your comments so the employee can revise and resubmit it.

Approving travel doesn't approve the resulting expense reports. Those reports go through the usual expense review after employees add and submit their actual expenses.

### View the travel request linked to an expense report

When you review a pending expense report linked to a travel request, select the request number beside **For travel request** to open its details. You can compare the approved plan with the actual expenses.

The linked request opens read-only. Viewing it through an expense report doesn't let you edit the request or make a separate travel approval decision.

## Review your approval history

Go to the **Approval history** tab to see the reports you approved or sent back. When travel requests and activity history are supported, travel request decisions appear there too. In the mobile app, select **Archived** from **Approvals**.

1. Open Expense Agent and go to the **Approval history** tab.
1. Select a report to expand its activity timeline.
1. Review the timeline, which includes submission, your approval or send-back decision with any comments, and the policy evaluation entry recorded at submission.

The timeline shows the policy evaluation results as they were at the time of submission, even if the expenses or policies changed afterward. Learn more in [How expense policy and rules compliance work](expense-agent-policy-compliance.md#review-the-submission-policy-snapshot).

Travel requests and their linked reports have separate timelines. The travel request timeline includes linked report creation. Posting events belong to the expense report timeline.

## Related information

[Expense Agent overview](expense-agent-overview.md)  
[Create and submit expense reports](expense-agent-expense-reports.md)  

[Plan and submit travel requests](expense-agent-travel-requests.md)

[How expense policy compliance works](expense-agent-policy-compliance.md)  
[Troubleshoot common issues in Expense Agent](expense-agent-troubleshoot.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
