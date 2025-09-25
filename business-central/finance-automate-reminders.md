---
title: Automate reminders in collections
description: Save time in collections by automating the processes of creating, issuing, and sending reminders to customers.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: collection, remindes
ms.search.form: 
ms.date: 03/12/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Automate reminders in collections

Make your collections more effective by automating the process of creating, issuing, and sending reminders to your customers. Automation can significantly reduce the time you spend on collections, provide a better overview of the process, and give you full control over each step.

On the **Reminder Automation** page, you define the individual actions (steps). You can combine the steps to create, issue, and send reminders, or you can create a separate automation for each step if that's better for your collection processes. Automations are based on reminder terms and reminder levels. To learn more, go to [Set Up Reminder Terms and Levels](finance-setup-reminders.md). You can set filters for reminder terms for an automation as a whole, and set filters for each action in the automation. You can also attach outstanding invoices to emails as PDF files.

Automation happens through a job queue entry. When you set up an automation, use the **Cadence** field to specify how and when it runs. If you choose **Manual**, the automation runs one time when you use the **Start** action. You can also choose **Weekly**, **Monthly**, or choose **Custom** to set up a more detailed cadence. If you choose **Custom**, you must enter a date formula. To learn more about entering a date formula, go to [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas). When you choose an option other than **Manual**, the automation runs until you pause it to put it on hold. If you want to be even more specific about when it runs, use the **Job queue entries** action to open the **Job Queue Entries** page and adjust the recurrence, for example to daily or a specific weekday.

## Automate the reminders flow

The following sections describe how to set up reminders to create, issue, and send automatically.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Reminders Automation**, and then choose the related link.
1. Choose **New**, and then fill in the fields on the **General** FastTab.
1. In the **Reminder Terms Filter** field, choose the reminder term or terms to use this automation for.
1. In the **Cadence** field, choose how often the automation runs.
1. On the **Actions** FastTab, choose **New**, and then choose whether the automation creates, issues, or sends reminders. Choose **OK**.
1. Depending on the type of action the automation performs, fill in the fields as necessary on the setup page. To learn more about the settings, go to [Settings for reminder actions](#settings-for-reminder-actions).
1. After you set up the actions for the automation, you can use the **Move up** and **Move down** actions to adjust the order in which they run.

## Settings for reminder actions

The setup settings differ for the Create, Issue, and Send reminder actions. The following sections describe how to use them.

### Create

* Set the highest level on all reminder lines.  
* Create reminders for entries that are on hold. For example, this setting is useful if you're in an ongoing dispute with a customer and want them to see the big picture.
* Create reminders for all unpaid invoices, and not just invoices that are overdue. The report displays overdue invoices and invoices that are unpaid but not overdue in separate sections.
* Set filters to make the reminder more specific.

### Issue

When you issue a reminder, you create entries in the customer ledger that contain the posting date and tax date. Use the settings on the **Issue Reminders Setup** page to specify whether to replace that information on the issued reminder with the information from the created reminder. For example, if you created the reminder yesterday, and issue it today, the due date moves one day.

### Send

> [!NOTE]
> The Send automation requires that you've set up email in [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more about setting up email, go to [Set up email](admin-how-setup-email.md).

The content of the emails, such as attachment texts, email body texts, and language come from the setup for the reminder term. To learn more about email settings, go to [Set Up Reminder Terms and Levels](finance-setup-reminders.md).

Use the settings on the **Send Reminders Setup** page control the following:

* General settings, such as the description, and how many times you send the same reminder.
* Settings for what to include in the reminder.
* Settings for tracking the reminders you send by creating interactions, whether you print or send the reminder by email, and whether you want to attach overdue invoices only, all invoices, or no invoices. 

## Access the history of a reminder

[!INCLUDE [prod_short](includes/prod_short.md)] keeps track of each time an automation runs. You can access the history by choosing the **Log entries** action. You can also use the **Issued Reminders** action to access a list of the reminders you've issued.

## Handle errors

On the **Actions** FastTab, for each action you can specify whether you want the automation to stop if the action has an error. If you do, the automation won't process the actions that come afterward. To turn this feature on or off, use the **Set stop on error** or **Clear stop on error** actions.

## Change action settings for an automation

You can change settings for an automation at any time. On the **Actions** FastTab, choose **Setup**, and then make your changes.

## Related information

[Set Up Reminder Terms and Levels](finance-setup-reminders.md)  
[Send Reminders of Outstanding Balances](receivables-send-reminders.md)  
