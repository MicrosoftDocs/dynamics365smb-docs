---
title: Automate reminders in collections
description: This article explains how you save time in collections by automating the processes of creating, issuing, and sending reminders to customers.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: how-to
ms.search.keywords: collection, remindes
ms.search.form: 
ms.date: 03/12/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Automate reminders in collections

Make your collections more effective by automating the process of creating, issuing, and sending reminders to your customers. Automation can significantly reduce the time you'll spend on this workload, provide a better overview of the process, and give you full control over each step.

You set up reminder automation on the **Reminder Automation** page, where you create the individual automations. You can combine the steps to the create, issue, and send reminders, or you can create separate automations for each step if that's better for your collection proccesses.

On the **Reminder Automation** page, you define the individual actions (steps) in the automations. You can set filters for reminder terms for the automation as a whole, and set additional filters for each action in the automation. You can also attach outstanding invoices attached as PDFs to the emails.

After you set up an automation, you can start it and it'll run until you put it on hold or stop it. If you want to control how the automation runs, you can open the **Job Queue Entries** page and set the recurrence to daily, or every Tuesday, for example.

## Automate the reminders flow

The following sections describe how to set up reminders to create, issue, and send automatically.

### Set up automations for reminder actions

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminders Automation**, and then choose the related link.
1. Choose **New**, and then fill in the fields on the **General** FastTab.
1. In the **Reminder Terms Filter** field, choose the reminder term or terms to use this automation for.
1. In the **Cadence** field, choose how often the automation runs.
1. On the **Actions** FastTab, choose **New**, and then choose whether the automation creates, issues, or sends reminders. Click **OK**.
1. Depending on the type of action the automation performs, fill in the fields as necessary on the setup page. To learn more about the settings, go to [Settings for different reminder actions](#settings-for-different-reminder-actions).

## Settings for different automations

The setup settings differ for each type of automation. The following sections describe how to use them.

### Create

* Set the highest level on all reminder lines.  
* Create reminders for entries that are on hold. For example, this setting is useful if you're in an ongoing dispute with a customer and want them to see the big picture.
* Create reminders for all unpaid invoices, and not just those that are overdue. The report displays overdue invoices and those that are just unpaid in separate sections.
* Set filters to make the reminder more specific. 

### Issue

### Send

> [!NOTE]
> The Send automation requires that you've set up email in [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more about setting up email, go to [Set up email](admin-how-setup-email.md).

From the **Reminder Terms Setup** page, you can choose the **Customer Communication** action to set up texts for each reminder terms level.

* On the **Attachment Text** FastTab

On the **Reminder Level Communication** page, you can enter texts to show on the reminder , and body texts for emails on the **Email Text** FastTab. The texts let you tailor messages for each reminder level, which makes it more flexible and accomodates business policies for communicating payment requests.

When you send an email, the reminder is a report you attach to the email. You define the report that generates the reminder on the **Report Selection Reminder/Finance Charge** page, where you also select the report that holds the email body text in the **Email Body Layout Name** field. When you send emails to your customers, the texts on the **Email Text** FastTab is inserted in the report selected in the **Email Body Layout Name** field. The standard report has a text field for this text. If you want, you can edit this report, for example, to add or remove content. The layout of these reports can be edited on the **Report Layouts** page.

You can create custom email texts for each reminder level so your messages suit your business's collection policies and practices.

## Change action settings for an automation

You can change settings for automations at any time. On the **Actions** FastTab, choose **Setup**, and then make your changes.


## See also

[Set Up Reminder Terms and Levels](finance-setup-reminders.md)  
[Send Reminders of Outstanding Balances](receivables-send-reminders.md)  
