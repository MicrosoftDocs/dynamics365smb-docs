---
title: How-to topic template #Required; page title displayed in search results. Don't enclose in quotation marks.
description: How-to description #Required; article description that's displayed in search results. Don't enclose in quotation marks. Do end with a period.
author: rhanajoy #Required; your GitHub user alias, with correct capitalization.
ms.author: rhcassid #Required; your Microsoft alias; optional team alias.
ms.reviewer: kfend #Required; Microsoft alias of content publishing team member.
ms.topic: how-to #Required; don't change.
ms.collection: get-started #Required; If this isn't a getting started article, don't remove the attribute, but leave the value blank. The values for this attribute will be updated over time.
ms.date: 11/13/2024
ms.custom: bap-template #Required; don't change.
---

# Process sales quotes and orders using the sales order agent 

Once the sales order agent is activated, it monitors the mailbox for incoming emails about sales quote requests. It matches senders to registered customers, finds requested items in the inventory, and creates sales quotes. It can then send the quotes to prospects and convert them to sales orders depending on the replies.  

## Get started

You collaborate with the sales order agent to review and convert quotes into orders using the **Tasks** view in the **Copilot** pane. 

To access this view, select the  sales order agent badge on the right side of the navigation menu at the top. A red circle with a number on the icon indicates tasks needing attention.  

A screenshot of a computer

The Tasks view opens in the Copilot pane, showing tasks recently created by the sales order agent, with those requiring attention‒like reviewing an incoming or outgoing email‒at the top of the list.  

For each sales quote request, the sales order agent adds a “task” in the Tasks view for tracking, reviewing, and processing the quote into an order. A task can consist of multiple steps that make up a “timeline” of the entire process. 

## Understand the general flow

Processing a sales quote request into an order involves 3 participants: 

- Customer who requests a sales quote via an email 
- Sales order agent, which handles the incoming request and creates the quote and order  
- Internal Business Central user who reviews tasks (reviewer)

The general flow is as follows: 

1. Customer: Sends email to Business Central mailbox asking for a sales quote for items. 
1. Sales order agent: Picks up unread email from inbox and creates a task with a step for reviewing incoming request. 
1. Reviewer: Reviews/confirms the step with email.  
1. Sales order agent: 

    1. Finds the requested items. 
    1. Finds the contact. 
    1. Creates the sales quote. 
    1. Adds review step with a reply email with attached sales quote as pdf. 
1. Reviewer: Reviews/confirms email and sales quotes. 
1. Sales order agent: Sends email and sales quote PDF to customer. 
1. Customer: Review sales quote and sends email requesting order. 
1. Sales order agent: Picks up email and adds review step 
1. Reviewer: Reviews/confirms the confirmation email for a sale order. 
1. Sales order agent: 

    1. Converts quote to order.
    1. Adds review task with outgoing email confirming order.
1. Reviewer: Reviews/confirms outgoing email. 
1. Sales order agent: Sends email to customer. 

## View sales order agent task timeline 

To view the steps that a task has gone through chronologically, click the task in the Tasks view or select **...** (More options) > **Show Details**.  

## Review steps 

Your intervention is required for various steps in the process of creating a sale order, for example: 

- Review and confirm incoming email requests for sales quotes from customers. 
- Review and confirm the sales quote and outgoing email created by the sales order agent for the customer. 
- Provide assistance to the sales order agent for resolving a problem. 

Steps requiring your intervention are listed under **Needs Attention** in the Tasks view. To review a step: 

1. On the step, select … (More options) > Review.  

   The Tasks view switches to display the Review pane, and the Agent Task Message window opens to display the contents of the incoming or outgoing email.  
1. Review the contents of the email and make changes as needed. 
1. When you’re satisfied with the content, select Confirm on in the Review pane.  

After confirming the step, the sales order agent moves the task on for more processing. After some time, a new notification appears on the sales order agent badge. Follow the same flow to verify and approve the results.

## Next steps

<!--Remove all the comments in this template before you sign-off or merge to the main branch.-->
