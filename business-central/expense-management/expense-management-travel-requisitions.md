---
title: Manage Travel Requests in Business Central
description: Learn how to create, submit, track, and close travel requests, estimate travel costs, and link approved requests to expense reports in Business Central.
author: jswymer
ms.topic: how-to
ms.date: 09/26/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: solsen
ms.search.form: 7136, 7129, 7137, 7101
ai-usage: ai-assisted
---

# Manage travel requests

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Travel requests help organizations review planned travel before employees incur expenses. A request records the purpose, travelers, dates, estimated costs, and travel policy acknowledgment. After approval, you can link a request to an expense report and compare posted spending with the total expected amount.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

> [!IMPORTANT]
> In version 29, you manage travel requests in [!INCLUDE[prod_short](../includes/prod_short.md)]. Travel requests aren't available in the Expense Agent web or mobile experience.

## Before you start

To create and manage travel requests, you need the **Expense Management - Edit** permission set. To view requests, you need **Expense Management - Read**. Administrators who configure expense management can use **Expense Management - Admin**.

Complete these setup tasks:

- Set up an expense user for each person who requests travel or is added as a traveler.
- Set up the expense categories, G/L accounts, posting groups, currencies, and dimensions that your organization uses for travel expenses.
- If Expense Agent is enabled, use the **Expense Approval Setup** page to assign an **Approver No.** to each **Expense User No.** that submits requests.

The **Spend Request No. Series** field on the **General Ledger Setup** page is optional. This field uses the internal name *spend request* because travel requests use that underlying record. If you configure the field, travel requests use the defined numbering scheme. Otherwise, [!INCLUDE[prod_short](../includes/prod_short.md)] derives the next sequential number when you create a request.

Learn more in [Set up expense users and teams](expense-management-users-teams.md) and [Set up expense management](expense-management-setup.md).

## Create and complete a travel request

1. [!INCLUDE[open-search](../includes/open-search.md)], enter **Travel Requests**, and then select the related link.
1. Select **New** to open a **Travel Request** card.
1. In **Requested For**, select the expense user whose travel is being requested. The selected expense user is automatically added to **Travelers**.
1. Enter the **Purpose**, **Currency Code**, and **Total Expected Amount**.
1. Enter the **Expected Start Date** and **Expected End Date**. Enter the **Actual Start Date and Time** and **Actual End Date and Time** when that information is available.
1. For international travel, turn on **International Travel** and specify the **Origin Country** and **Destination Country**.
1. Turn on **Travel Policy Acknowledgment** after the traveler acknowledges the policy. Turn on **Per Diem Included** if the request includes per diem costs.
1. Specify the shortcut dimensions, or select **Dimensions** to add other dimensions.
1. Select **Travelers** and add any other expense users who will travel.

If you change **Requested For**, [!INCLUDE [prod_short](../includes/prod_short.md)] asks whether to replace the traveler added for the previous expense user.

The **Expected End Date** can't be earlier than the **Expected Start Date**. The **Total Expected Amount** can't be less than the total amount on the lines.

### Add estimated cost lines

On the **Lines** FastTab, add one or more cost estimates. Use the following fields.

| Field | Description |
| --- | --- |
| **Type** | Select **Category** for an estimate associated with a specific expense category. Select **Lump Sum** for an overall estimate that isn't assigned to a category. |
| **Expense Category** | Select an active expense category. This field is available only when **Type** is **Category**. |
| **Description** | Describe the estimated cost. |
| **Currency Code** | Specify the currency for the estimate. When you change the currency on an open request, the current exchange rate is used to calculate the local-currency amount. |
| **Amount** | Enter the expected amount in the selected currency. |
| **Amount (LCY)** | Shows the expected amount converted to local currency. |
| **G/L Account No.** | Specify the account when your organization's posting setup requires one for the estimate. |

## Submit and track a travel request

Select **Release** when the request is ready. The request changes from **Open** to **Submitted** and is locked for editing. Before submission, the request must have:

- A **Requested For** expense user
- An **Expected Start Date** and **Expected End Date**
- **Travel Policy Acknowledgment** turned on
- At least one traveler
- A **Destination Country** if **International Travel** is turned on

When Expense Agent is disabled, submission automatically changes the request to **Approved** because no Expense Agent approver is available. When Expense Agent is enabled, the request remains **Submitted** until the configured approver decision is processed. Version 29 doesn't use standard [!INCLUDE [prod_short](../includes/prod_short.md)] workflow templates for travel request approval.

Travel requests use these statuses.

| Status | Description |
| --- | --- |
| **Open** | The request is being prepared and can be edited. |
| **Submitted** | The request was submitted and is locked for editing. |
| **Approved** | The request can be linked to an expense report. |
| **Rejected** | The request wasn't approved. |
| **Closed** | The request is no longer available for new spending. |

You can reopen a **Submitted**, **Approved**, or **Rejected** request if no spending has been posted for it. You can't reopen a **Closed** request or a request that has posted spending.

## Link a travel request to an expense report

On an expense report, select an approved request in **Travel Request No.** The expense user on the report must be a traveler on the request. You can only link refundable expense lines. Use the **Travel Request** action on the report or line to open the related request.

Version 29 doesn't automatically create an expense report from a travel request.

When you assign a request to a refundable expense amount, [!INCLUDE [prod_short](../includes/prod_short.md)] compares the new refundable amount plus previously posted spending with the request's total expected amount in local currency. If the total is exceeded, the user assigning the request receives a nonblocking notification. Processing can continue.

Learn more in [Create and submit expense reports](expense-management-submit-report.md).

## Close a travel request and review posted spending

Select **Close** when the request should no longer be used. You can also mark a request to close when the linked expense report is posted. In that case, posting changes an approved request to **Closed** and records the closing document number.

Posting linked expenses creates the relationship between the travel request and the G/L entries. Use **Posted to G/L** to review posted relationships. **Posting preview** shows the same relationship as **Posted to G/L Preview**. These pages include the G/L account, posting date, document number, and amount.

Use **Total Spent Amount (LCY)** to review posted spending and **Remaining Amount (LCY)** to compare it with the total expected amount in local currency.

## Related information

[Manage employee expenses](expense-management-overview.md)

[Set up expense management](expense-management-setup.md)

[Create and submit expense reports](expense-management-submit-report.md)

[Post expense reports](expense-management-post-reports.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
