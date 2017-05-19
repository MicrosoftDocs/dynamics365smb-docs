---
title: "Prepare Reminders"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "preparing reminders"
  - "reminders, entries on hold"
ms.assetid: 67f10c84-a75e-4be2-a608-fe6ac4dc53f9
caps.latest.revision: 3
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-my"
  - "en-nz"
  - "en-ph"
  - "en-sg"
  - "en-zw"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Prepare Reminders
You can use reminders to remind customers about overdue amounts. You can also use reminders to calculate finance charges such as interest or fees and include them on the reminder.  
  
> [!NOTE]  
>  Use finance charge memos if you want to debit customers for interest or fees without reminding them of overdue amounts.  
>   
>  If a customer has an overdue balance and you do not want to issue a reminder, you can simply remind the customer by sending a statement that lists the overdue balances. To do this, when you run the **Statement** report, select the **Show Overdue Entries** field on the **Options** FastTab.  
  
 Before you can create reminders, you need to set up reminder terms and assign them to your customers. Each reminder terms code predefined reminder levels. Each reminder level includes rules about when the reminder will be issued, for example, how many days after the invoice due date or the date of the previous reminder. The contents of the **Finance Charge Terms** table determines whether interest is calculated on the reminder.  
  
 You can periodically run the **Create Reminders** batch job to create reminders for all customers with overdue balances, or you can manually create a reminder for a specific customer and have the lines calculated and filled in automatically.  
  
 After you create the reminders, you can modify them. The text that appears at the beginning and end of a reminder is determined by the reminder level terms, and can be seen in the **Description** column. If a calculated amount has been inserted automatically in the beginning or ending text, the text will not be adjusted if you delete lines. Then you must use the **Update Reminder Text** function.  
  
## Using Reminder Levels  
 The first time a reminder is created for a customer, the setting from level 1 is used. When the reminder is issued, the level number is registered on the reminder entries that are created and linked to the individual customer ledger entries. If it is necessary to remind the customer again, all reminder entries linked to open customer ledger entries are checked to locate the highest level number. The conditions from the next level number will then be used for the new reminder.  
  
 If you create more reminders than you have defined levels for, the conditions for the highest level will be used. You can create as many reminders as are allowed by the **Max. No of Reminders** field in the reminder terms.  
  
## Entries on Hold  
 A customer ledger entry with the **On Hold** field filled in will not prompt the creation of a reminder. However, if a reminder is created on the basis of another entry, an overdue entry marked on hold will also be included on the reminder. Interest is not calculated on lines with these entries.  
  
## Issuing Reminders  
 After you have created reminders and made any needed modifications, you can either print test reports or issue the reminders.  
  
 When you issue a reminder, the data is transferred to a separate table for issued reminders. At the same time, reminder entries are posted. If interest or an additional fee has been calculated, entries are posted to the customer ledger and the general ledger.  
  
 You can print the reminders when you issue them or print the reminders later.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Automatically create reminders for customers with overdue amounts.|[How to: Create Reminders Automatically](../Finance/how-to-create-reminders-automatically.md)|  
|Learn about the batch job that creates reminders automatically.|[\($ B\_188 Create Reminders $\)](../Finance/-$-b_188-create-reminders-$-.md)|  
|Create a reminder manually and have the lines filled in automatically.|[How to: Create Reminders Manually](../Finance/how-to-create-reminders-manually.md)|  
|Replace the beginning and ending text in a reminder with text from a different level.|[How to: Replace Reminder Text](../Finance/how-to-replace-reminder-text.md)|  
|View a summary of the amounts on a reminder.|[How to: View Reminder Statistics](../Finance/how-to-view-reminder-statistics.md)|  
|Post entries for one or more reminders and, if you choose, print the reminders.|[\($ B\_190 Issue Reminders $\)](../Finance/-$-b_190-issue-reminders-$-.md)|  
|Get an overview of the reminder entries that have been created for a specific customer.|[How to: View Reminder and Finance Charge Entries](../Finance/how-to-view-reminder-and-finance-charge-entries.md)|  
  
## See Also  
 [Set Up Reminders](../Finance/set-up-reminders.md)   
 [Working with \($ P\_1 Product Name $\)](../WorkingWithDynamics/working-with-$-p_1-product-name-$-.md)   
 [Manage Receivables](../Finance/manage-receivables.md)