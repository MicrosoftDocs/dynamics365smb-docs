---
title: Approve or reject documents in workflows
description: Request, reject, or delegate an approval of, for example, a purchase or sales document, as part of a workflow.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: reject, delegate, request
ms.search.form: 654, 662, 1500, 
ms.date: 06/10/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# How to use approval workflows

When a record, such as a purchase document or a customer card, needs to be approved by someone in your organization, you send an approval request as part of a workflow. Based on how the workflow is set up, the appropriate approver is then notified that the record requires their approval.

You set up approval workflows on the **Workflow** page. You must also set up approval users, including any relevant amount limits, on the **Approval User Setup** page. Learn more at [Set Up Approval Workflows](across-set-up-workflows.md).  

In addition to the approval workflows described in this article, you can perform various other workflow tasks. Learn more at [Use Approval Workflows](across-use-workflows.md).

Core approval workflows for purchases documents, sales documents, payment journals, customer cards, and item cards are ready to start as guides. Learn more at [Getting Ready for Doing Business](ui-get-ready-business.md).

## Request a record approval

The following task is performed by an approval user.

1. On the page that presents the record, choose the **Send Approval Request** action.
2. To see all your approval requests, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Approval Request Entries**, then choose the related link.  

The status of the approval entry is updated from **Created** to **Open**. The status of the record, such as a purchase invoice, is updated from **Open** to **Pending Approval** and remains locked for processing until all approvers have approved the record.

When all required approvers have approved the record, the status changes to **Released**. You can then continue working with the record.

## Cancel approval requests

The following task is performed by an approval user with approver rights.

A customer may want to change an order after it's been submitted for approval. In this case, you can cancel the approval process, make the necessary changes to the order, then request approval again.

- On the page displaying the record, choose the **Cancel Approval Request** action.

When the approval request has been canceled, the status of the related approval entry is changed to **Canceled**. The status of the record is updated from **Pending Approval** to **Open**. At this point, the approval process can start again.

## Approve or reject approval requests

The following task is performed by an approval user with approver rights.

You can process approval requests on the **Requests to Approve** page, including approving multiple requests at a time. Alternatively, you can approve individual records by choosing the link in the notification that you receive.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Requests to Approve**, and then choose the related link.
2. Select one or more lines of the record(s) you want to approve or reject.
3. Choose the **Approve**, **Reject**, or **Delegate** actions.

When a record has been approved or rejected, the approval status in the **Status** field changes to **Approved** or **Rejected**, respectively.

If an approver hierarchy is set up, the record status is **Pending Approval** until all requested approvers have approved the record. Then the record status changes to **Released**.

At the same time, the approval status changes from **Created** to **Open** as soon as an approval request for the record is created. If the request is rejected, the approval status changes to **Rejected**. The status remains **Open** or **Rejected** until all approvers have approved the request.

## Delegate approval requests

The following task is performed by an approval user with approver rights.

To prevent records from piling up or otherwise blocking the workflow, the approver and the approval administrator can delegate an approval request to a substitute approver. The substitute can either be a designated substitute, the direct approver, or the approval administrator, in that order of priority. You typically use this feature if an approver is unavailable or unable to approve requests before the due date.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Requests to Approve**, then choose the related link.
2. Select one or more lines of approval requests you want to delegate to a substitute approver, then choose the **Delegate** action.

A notification to approve the request is sent to the substitute approver.

## Manage overdue approval requests

The following task is performed by an approval user with approver rights.

At regular intervals you'll need to remind approval workflow users of overdue approval requests; you'll use the **Send Overdue Approval Notifications** function to do so.

The **Send Overdue Approval Notifications** function checks for all open approval requests currently overdue. Each approver with at least one overdue approval entry receives a notification with the list of all their overdue approval requests. The notification is also sent to their approver and all the requesters of the overdue approvals. This last step helps if the overdue approval entry must be delegated to a substitute.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Overdue Approval Requests**, and then choose the related link.
2. On the **Overdue Approval Requests** page, choose the **Send Overdue Approval Notifications** action.

## Related information

[Use Approval Workflows](across-use-workflows.md)  
[Workflow](across-workflow.md)  
[Set Up Approval Users](across-how-to-set-up-approval-users.md)  
[Sales](sales-manage-sales.md)  
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
