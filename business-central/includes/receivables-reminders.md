---
author: brentholtorf
ms.topic: include
ms.date: 03/12/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
You can use reminders to remind customers about overdue amounts. You can also use reminders to calculate finance charges such as interest or fees and include them on the reminder.

> [!TIP]
> The information in this article is accurate, however, it describes a mostly manual process. [!INCLUDE [prod_short](prod_short.md)] offers tools that you can use to automate the processes of creating, issuing, and sending reminders. Automating these steps can save you a considerable amount of time spent on collections. To learn more, go to [Automate reminders in collections](../finance-automate-reminders.md).

Before you can create reminders, you must set up reminder terms and assign them to your customers. For more information, see [Set Up Reminder Terms and Levels](../finance-setup-reminders.md). [!INCLUDE [reminder-terms](reminder-terms.md)] The contents of the **Finance Charge Terms** page determines whether interest is calculated on the reminder.  

You can periodically run the **Create Reminders** batch job to create reminders for all customers with overdue balances, or you can manually create a reminder for a specific customer and have the lines calculated and filled in automatically.  

After you create the reminders, you can modify them. The text that appears at the beginning and end of a reminder is determined by the reminder level terms, and can be seen in the **Description** column. If a calculated amount has been inserted automatically in the beginning or ending text, the text will not be adjusted if you delete lines. Then you must use the **Update Reminder Text** function.  

A customer ledger entry with the **On Hold** field filled in will not prompt the creation of a reminder. However, if a reminder is created on the basis of another entry, an overdue entry marked on hold will also be included on the reminder. Interest is not calculated on lines with these entries.

After you have created reminders and made any needed modifications, you can either print test reports or issue the reminders, typically as email.

### To create a reminder automatically

A reminder is similar to an invoice. When you create a reminder, a reminder header as well as one or more reminder lines must be filled in. You can use a function to create reminders for all customers automatically.

1. Choose the ![Lightbulb that opens the Tell Me feature 0.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminders**, and then choose the related link.
2. On the **Reminder** page, choose the **Create Reminders** action.
3. On the **Create Reminders** page, fill in the fields to define how and to whom the reminders are created.
4. Choose the **OK** button.

### To create a reminder manually

On the **Reminder** page, you can fill in the **General** FastTab manually and then have the lines filled in automatically.

1. Choose the ![Lightbulb that opens the Tell Me feature again 2.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminders**, and then choose the related link.
2. Choose the **New** action.
3. On the **General** FastTab, fill in the fields as necessary.
4. Choose the **Suggest Reminder Lines** action.
5. In the **Suggest Reminder Lines** batch job, fill in the fields to define how and to whom the reminders are created.
6. Select the **Include Entries On Hold** check box if you want the reminders to contain overdue open entries that are on hold.
7. Select the **Only Entries with Overdue Amounts** check box if you want the reminders to contain only overdue open entries. Only invoices and payments will be shown as these are the entries for which your customers' payments may be overdue.

    > [!Important]
    > Open entries that are on hold will be inserted, irrespective of the setting in the **Only Entries with Overdue Amounts** check box.

8. Choose the **OK** button.

### To replace reminder texts

There are several ways you can determine the text that appears on the printed reminder. In some cases, you may want to replace the beginning and ending texts that have been defined for the current level with those from a different level.

1. Choose the ![Lightbulb that opens the Tell Me feature yet again 3.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminders**, and then choose the related link.
2. Open the relevant reminder, and then choose the **Update Reminder Text** action.
3. On the **Update Reminder Text** page, enter the required level in the **Reminder Level** field.
4. Choose the **OK** button to update the beginning and ending texts.

### To issue a reminder

After you have created reminders and made any needed modifications, you can either print test reports or issue the reminders.

When you issue a reminder, the data is transferred to a separate page for issued reminders. At the same time, reminder entries are posted. If interest or an additional fee has been calculated, entries are posted to the customer ledger and the general ledger.

When a reminder is issued, the entries are posted according to your specifications on the **Reminder Terms** page. This specification determines whether interest and/or additional fees are posted to the customer's account and the general ledger. Setup on the **Customer Posting Groups** page determines which accounts are posted to.

For each customer ledger entry on the finance charge memo, an entry is created on the **Reminder/Fin. Charge Entries** page.

If the **Post Interest** or the **Post Additional Fee** check boxes are selected on the **Reminder Terms** page, then the following entries are also created:

- One entry on the **Customer Ledger Entries** page
- One receivables entry in the relevant G/L account
- One interest and/or one additional fee entry in the relevant G/L account

In addition, issuing the reminder may result in VAT entries.

1. Choose the ![Lightbulb that opens the Tell Me feature also here 4.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminders**, and then choose the related link.
2. Select the relevant reminder, and then choose the **Issue** action.
3. On the **Issue Reminders** page, fill in the fields as necessary.
4. Choose the **OK** button

The reminder is either printed for sent to an specified email as a PDF attachment.

### To cancel an issued reminder

If reminders were issued in error, you can cancel them before they are sent out. You can do this either one by one or as a batch.

1. On the **Issued Reminders** page, select one or more lines for issued reminders that you want to cancel, and then choose the **Cancel** action.
2. On the **Cancel Issued Reminders** page, fill in the fields as necessary, and then choose the **OK** button.


