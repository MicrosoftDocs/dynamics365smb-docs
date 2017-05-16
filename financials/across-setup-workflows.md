---
title: 'Setting Up Workflows| Microsoft Docs'
description: 'Learn how to interlink steps in a business process by setting up workflows.'
services: project-madeira
documentationcenter: ''
author: bholtorf

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/05/2017
ms.author: bholtorf

---
# Setting Up Workflows
This topic describes how to connect tasks in a business process by setting up workflows to ensure that you reach your goals. Workflows send email messages to people to let them know that an event has occurred and they need to do something about it. These can be tasks that people do, such as requesting or granting approval for a new vendor, system tasks like automatically posting something to the general ledger, or both.  
  
In addition to this topic, we've also created a short video that shows how to set up workflows. To watch the video, go to [Set up approval workflows](https://go.microsoft.com/fwlink/?linkid=843246).  

**Note**: To use workflows, you must choose the **Suite** user experience for your company. For more information, see [Customizing Your Dynamics 365 for Financials Experience](ui-experiences.md).  

Setting up workflows from scratch can be tricky, especially if you're just getting started. To make it easier, we provide tools that can help you set up some workflows that businesses often use. We recommend that you use these tools when you set up workflows: 

* Assisted setups that help you set up a few approval workflows
* Workflow templates that we've prepared for you. You can use them as is, or customize them.

**Note**: Because workflows send email messages to notify people, you'll need to set up email in [!INCLUDE[d365fin](includes/d365fin_md.md)] for each person. For more information, see [Set Up Email](madeira-how-setup-email.md).

### What are workflows, really?
Workflows are ordered, repeatable sequences of steps. Each step consists of:

* _Events_ that start a workflow. Examples of events are when someone creates or changes information about a vendor or customer, requests approval when creating a purchase order, or changes the unit price of an item.  
* _Conditions_ under which the event starts a workflow. Examples of conditions are when something has a certain status, when a certain user does something, or when an event affects a certain type of document.   
* _Responses_, which are the actions that happen in each step. There can be more than one response in a step. Examples of responses are changing the status of a document, sending a message to an approver, or reverting a change someone made.

We provide events, conditions, and responses for the scenarios that [!INCLUDE[d365fin](includes/d365fin_md.md)] supports. When you choose an event, the conditions and responses that are available are designed for that event.

You define the sequence of steps on the **Workflow** page. The first step is at the top, and you can create a hierarchy of steps by using the **Decrease Indent** and **Increase Indent** actions on the **Manage** tab. When you indent a step, the previous step must be completed first. If you leave all steps at the same level in the hierarchy, they all happen at the same time when the event occurs.

### How do I involve people in a workflow?
Workflows involve people who tackle the tasks in a business process, and often also involve people who approve things. There are two ways to involve people in workflows:

* Assign them to a workflow group
* Assign them to an approval user setup

To involve someone in a workflow, you must add them to a workflow user group. If the workflow involves approvals, you need to add both the requestors and the approvers to an approval user setup.  

Workflow user groups define when a person becomes involved in the workflow, relative to the others in the group, according to the sequence number you specify. For example, to specify when the someone gives an approval, relative to other approvers, when you use the **Workflow User Group** option in the **Approver Type** field on the related workflow response. To define that an approval request is not approved until multiple approvers approve it, with no hierarchy, set up a flat wokflow user group by assigning the same sequence number to the relevant approvers.

When you set up approvers, you can specify the amounts, in local currency, that they're allowed to approve for sales and purchases. For example, this is useful when you set up a hierarchy of multiple approvers, where some approve smaller amounts, and others approve larger. You can also designate people as substitute approvers who can help out, for example, when an approver is absent.

## To assign people to participate in workflows
To set up a workflow user, follow these steps:

1. Choose the **Search for Page or Report** icon, enter **Workflow User Groups**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].

To assign approvers, follow these steps:

1. Choose the **Search for Page or Report** icon, enter **Approval User Setup**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To set up workflow email messages
Workflows send email messages to notify the people involved in a workflow. For example, when User 1 requests approval of a new record, [!INCLUDE[d365fin](includes/d365fin_md.md)] sends email message to User 2, the approver. On the next workflow step, the event can be that User 2 approves the record, and [!INCLUDE[d365fin](includes/d365fin_md.md)] sends a message to User 3 to start processing the approved record. For workflow steps that involve approval, each message is tied to an approval entry.  
  
You set up workflow email messages in the following places:  
  
* You choose when, and how, people are notified on the **Notification Setup** page.  
* For approval workflows, you specify the message recipients by filling a line in the **Approval User Setup** page for each user. For example, if User 2 is specified in the **Approver ID** field on the line for User 1, then the approval request message is sent to User 1.  
* You set up the general content and layout of messages on the **Notification Templates** page. We provide some default templates, one for notifying about approval requests, one for notifying about new records, and one for notifying about overdue approval requests. If you want, you can chenge the content of the templates. To do that, export the template, modify the HTML, and then import it.  
* You set up content and rules for notification emails from the **Workflow** page by choosing options on the **Workflow Response Options** page.  
* To send e-mails using an SMTP server, fill in fields on the **SMTP Mail Setup** page. You can also use the **Set up email** assisted setup guide. To see a short video about setting up email, go to [Set up email](https://go.microsoft.com/fwlink/?linkid=843243). 

## To use assisted setups to create approval workflows for customers, items, and payments
The following table describes the assisted setup guides that we provide. The guides walk you through the steps to assign an approver    

| Assisted Setup Guide | Description |
|---|---|
|**Set up a customer approval workflow**| Notify an approver when someone creates a new customer, or changes information on a customer card. |
|**Set up an item approval workflow**| Notify an approver when someone creates a new item, or changes information on an item card. |
|**Set up a payment approval workflow**| Use this workflow when you want someone to approve. |

To use an assisted setup guide to create a customer, item, or payment approval workflow, follow these steps:  
  
1. Choose the **Search for Page or Report** icon, enter **assisted setup**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].

## To use workflow templates to create workflows
We provide workflow templates that you can use as a basis for creating your own workflows. Afterward, you can customize your new workflow.

1. Choose the **Search for Page or Report** icon, enter **workflow templates**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].

## See Also
[How to: Use Approval Workflows](across-how-use-approval-workflows.md)  
[Sales](sales-manage-sales.md)    
[Incoming Documents](across-income-documents.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
