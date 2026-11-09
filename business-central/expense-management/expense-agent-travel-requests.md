---
title: Create and Submit Travel Requests in Expense Agent
description: Plan a business trip in Expense Agent, estimate costs, add travelers and per diem details, and submit a travel request before you incur expenses.
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

# Plan and submit travel requests in Expense Agent

[!INCLUDE [online_only](../includes/online_only.md)]

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Use a travel request to get approval for a business trip before you incur expenses. In Expense Agent, you can describe the trip, add travelers, estimate costs, and include per diem details. When the request is approved, [!INCLUDE [prod_short](../includes/prod_short.md)] creates linked expense reports for recording the trip's expenses.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Before you start

You can create and manage travel requests in the Expense Agent web and mobile apps. Creating, editing, submitting, approving, and deleting requests require an internet connection and access to the company.

You need an expense user record and an assigned approver to submit a request. Any additional travelers must be available in the traveler list. Learn more in [Set up expense users and teams](expense-management-users-teams.md).

## Create a travel request

1. In the web app, select **Create travel request** in **Quick actions**. In the mobile app, go to **Expenses**, select **+**, and then select **Create travel request**.
1. On the **Details** tab, enter a **Purpose** that explains the trip.
1. Enter the **Expected start date** and **Expected end date**. The end date can't be before the start date.
1. Review the **Currency** and change it if needed.
1. In **Additional travelers**, select other employees who will travel with you. You don't need to add yourself.
1. If the trip includes per diem allowances, open the **Per diem allowance** tab, select the **Per diem location**, and enter the **Departure time** and **Return time**. The times apply to the expected start and end dates.
1. On the **Estimated expenses** tab, select **Add estimated expense** and complete the cost details. Add at least one estimate, as described in [Add estimated costs](#add-estimated-costs).
1. To save without submitting, select **Create draft**. To send the request for approval now, open the menu next to **Create draft** and select **Submit**.

[!INCLUDE [prod_short](../includes/prod_short.md)] records you as the requester and adds you as a traveler. **Total amount** is calculated from the estimates after the request is created. You don't enter the total directly.

### Add estimated costs

Each estimate describes an expected cost, such as a flight or hotel stay. Complete these fields for each estimate.

| Field | Description |
| --- | --- |
| **Description** | Explain what the estimated cost covers. |
| **Cost type** | Select **Category** to associate the estimate with an expense category. Select **Lump sum** for an estimate that isn't assigned to a category. |
| **Category** | Select an active expense category when **Cost type** is **Category**. |
| **Amount** | Enter the estimated amount. |
| **Currency** | Select the currency for the estimate. |

If you select a per diem category without entering per diem details, the **Per diem allowance** tab shows a reminder. The category doesn't automatically add those details or prevent saving. Once you enter a location or either time, you must complete all three fields before saving or submitting. The return must be after departure.

## Edit and submit a draft

Saved drafts appear alongside draft expense reports. In the web app, go to **Drafts**. In the mobile app, go to **Expenses** and use the document picker to select the request.

In the web app, use the **Document type** filter to show **Travel requests**, **Expense reports**, or **All**.

1. Open the travel request for review.
1. Select **Edit** and make your changes.
1. To save for later, select **Save**. To submit now, open the menu next to **Save** and select **Submit**.

To submit a saved draft without editing it, reopen the request for review and select **Submit**.

The request changes to **Pending approval** and appears on **Submitted**. You can't edit it while it awaits a decision. Approvers review travel requests alongside expense reports. Learn more in [Review and decide on a travel request](expense-agent-approve-reports.md#review-and-decide-on-a-travel-request).

If saving succeeds but submission fails, the request remains saved. Open the existing draft and try submitting again rather than creating another request.

To discard a draft, select **More actions** on the request, select **Delete**, and confirm. Deleting the request also removes its estimated costs and traveler entries.

## Revise a request that's sent back

When an approver sends a request back, it becomes editable again. The request shows the approver's name and comments.

1. Find the returned request in **Drafts** in the web app or **Expenses** in the mobile app.
1. Open the request and review the approver's comments.
1. Select **Edit** and make the requested changes.
1. Open the menu next to **Save** and select **Resubmit**.
1. In the confirmation, review the feedback. To explain your changes, enter a reply in **Reply to approver (optional)**. Select **Resubmit**.

The request returns to the approval queue. The approver can review your reply with the revised request.

To save your changes for later, select **Save** instead of **Resubmit**. When you're ready, reopen the request for review and select **Resubmit**.

## Record expenses after travel approval

When the approver approves a request, [!INCLUDE [prod_short](../includes/prod_short.md)] creates linked expense reports for the travelers. In Expense Agent, you see only your own report. Open your draft report to review and add expenses.

Receipt matching uses the linked request's expected trip dates rather than the report's calendar month. Receipts dated up to three days before or after the trip can also be considered. A receipt isn't guaranteed to match the trip report, so review the assignment and [move the expense](expense-agent-expense-reports.md#move-an-expense-to-a-different-report) if needed.

Travel approval doesn't approve the expenses you incur. Review and submit the linked expense report for approval through the usual process. Learn more in [Create and submit expense reports](expense-agent-expense-reports.md).

### Create a replacement expense report

If you created the request and your linked report was deleted, you can recreate that report. Find the approved request on **Approved** in the web app or **Submitted** in the mobile app, open it for review, and select **Create expense report** when the action is available. If you're an additional traveler whose report is missing, contact the requester or your administrator.

If the trip is no longer needed and **Delete** is available, you can select it and confirm the deletion. Business Central blocks deletion if any expense report or report line still references the request, including another traveler's report or a posted report. Deleting your own report isn't sufficient if other linked records remain. Deleting an eligible travel request also removes its estimated costs and traveler entries.

## View travel request history

When activity history is available, go to **History** in the web app to review travel request events alongside expense report events. The request timeline records events such as creation, submission, approval, being sent back, and linked report creation.

The linked expense report has its own timeline. Its **Created** event identifies the approved travel request that it came from. When a travel request link is available, select it to view the request without editing it.

## Related information

[Manage expenses with Expense Agent](expense-agent-overview.md)

[Create and submit expense reports](expense-agent-expense-reports.md)

[Approve or send back expense reports and travel requests](expense-agent-approve-reports.md)

[Manage travel requests in Business Central](expense-management-travel-requisitions.md)

[Troubleshoot common issues in Expense Agent](expense-agent-troubleshoot.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
