---
title: Remind or Fine Customers of Overdue Payments| Microsoft Docs
description: Describes how to send a reminder to a customer about a payment that is due and add charges, or fees to the payment because of the delay.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment due, debt, overdue, fee, charge, reminder
ms.date: 04/02/2020
ms.author: sgroespe

---
# Collect Outstanding Balances
Managing receivables includes checking whether amounts due are paid on time. If customers have overdue payments, you can begin by sending the Customer Statement report as a reminder. Alternatively, you can issue reminders.

You can use reminders to remind customers about overdue amounts. You can also use reminders to calculate finance charges, such as interest or fees and include them on the reminder. Use finance charge memos if you want to debit customers for interest or fees without reminding them of overdue amounts.

## Reminders
Before you can create reminders, you must set up reminder terms and assign them to your customers. Each reminder term has predefined reminder levels. Each reminder level includes rules about when the reminder will be issued, for example, how many days after the invoice due date or the date of the previous reminder. The contents of the **Finance Charge Terms** page determines whether interest is calculated on the reminder.  

You can periodically run the **Create Reminders** batch job to create reminders for all customers with overdue balances, or you can manually create a reminder for a specific customer and have the lines calculated and filled in automatically.  

After you create the reminders, you can modify them. The text that appears at the beginning and end of a reminder is determined by the reminder level terms, and can be seen in the **Description** column. If a calculated amount has been inserted automatically in the beginning or ending text, the text will not be adjusted if you delete lines. Then you must use the **Update Reminder Text** function.  

A customer ledger entry with the **On Hold** field filled in will not prompt the creation of a reminder. However, if a reminder is created on the basis of another entry, an overdue entry marked on hold will also be included on the reminder. Interest is not calculated on lines with these entries.

After you have created reminders and made any needed modifications, you can either print test reports or issue the reminders, typically as email.

## Finance Charges
When a customer does not pay by the due date, you can have finance charges calculated automatically and add them to the overdue amounts on the customer's account. You can inform customers of the added charges by sending finance charge memos.  

> [!NOTE]  
> You use finance charge memos to calculate interest and finance charges and to inform your customers about interest and finance charges without reminding them of overdue payments. Alternatively, you can calculate interest on overdue payments when you create reminders.  

You can manually create a finance charge memo for an individual customer, and fill in the lines automatically. Alternatively, you can use the **Create Finance Charge Memos** function job to create finance charge memos for all or selected customers with overdue balances.  

After you create the finance charge memos, you can modify them. The text that appears at the beginning and end of the finance charge memo is determined by the finance charge terms, and can be seen in the **Description** column on the lines. If a calculated amount has been inserted automatically in the beginning or ending text, the text will not be adjusted if you delete lines. Then you must use the **Update Finance Charge Text** function.  

After you have created finance charge memos and made any needed modifications, you can either print test reports or issue the finance charge memos, typically as email.

## Multiple Interest rates
When you set up finance charge terms and reminder terms, for delayed payment penalty, you can specify multiple interest rates so that the penalty fee is calculated from different interest rates in different periods. If multiple interest rates are not set up, then the interest rate and period that is defined in the **Finance Charge Terms** and **Reminder Terms** pages for the whole period of calculation will be used. For more information, see [Set Up Multiple Interest Rates](finance-how-to-set-up-multiple-interest-rates.md).  

## To send the Customer Statement report
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Statement**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Under **Output Options**, select how to send the report to the customer.

> [!NOTE]  
>   If you are using multiple currencies, the Customer Statement report is always printed in the customer's currency. The last date in a statement period is also used as the statement date and the aging date, if aging is included.

## To set up reminder terms
If customers have overdue payments, you must decide when and how to send them a reminder. In addition, you may want to debit their accounts for interest or fees. You can set up any number of reminder terms. For each reminder terms code, you can define an unlimited number of reminder levels.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminder Terms**, and then choose the related link.  
2. Fill in the fields as necessary.  
3. To use more than one combination of reminder terms, set up a code for each one.

## To set up reminder levels
The first time a reminder is created for a customer, the setting from level 1 is used. When the reminder is issued, the level number is registered on the reminder entries that are created and linked to the individual customer ledger entries. If it is necessary to remind the customer again, all reminder entries linked to open customer ledger entries are checked to locate the highest level number. The conditions from the next level number will then be used for the new reminder.

If you create more reminders than you have defined levels for, the conditions for the highest level will be used. You can create as many reminders as are allowed by the **Max. No of Reminders** field in the reminder terms.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminder Terms**, and then choose the related link.  
2. On the **Reminder Terms** page, select the line with the terms you want to set up levels for, and then choose **Levels** action.  
3. Fill in the fields as necessary.  

    For each reminder level, you can specify individual conditions, which can include additional fees in both LCY and in foreign currency. You can define many additional fees in foreign currencies for each code on the **Reminder Levels** page.
4. Choose the **Currencies** action.
5. On the **Currencies for Reminder Levels** page, define for each reminder level code and corresponding reminder level number a currency code and an additional fee.

    > [!NOTE]  
    > When you create reminders in a foreign currency, the foreign currency conditions that you set up here will be used to create reminders. If there are no foreign currency reminder conditions set up, the LCY reminder conditions that are set up on the **Reminder Levels** page will be used and then converted to the relevant currency.

    For each reminder level, you can specify text that will be printed before (**Beginning Text**) or after (**Ending Text**) on the entries on the reminder.

6. Choose the **Beginning Text** or **Ending Text** actions respectively, and fill on the **Reminder Text** page.
7. To automatically insert related values in the resulting reminder text, enter the following placeholders in the **Text** field .  

|Placeholder|Value|  
|-----------------|-----------|  
|%1|Content of the **Document Date** field on the reminder header|  
|%2|Content of the **Due Date** field on the reminder header|  
|%3|Content of the **Interest Rate** field on the related finance charge terms|  
|%4|Content of the **Remaining Amount** field on the reminder header|  
|%5|Content of the **Interest Amount** field on the reminder header|  
|%6|Content of the **Additional Fee** field on the reminder header|  
|%7|The total amount of the reminder|  
|%8|Content of the **Reminder Level** field on the reminder header|  
|%9|Content of the **Currency Code** field on the reminder header|  
|%10|Content of the **Posting Date** field on the reminder header|  
|%11|The company name|  
|%12|Content of the **Add. Fee per Line** field on the reminder header|  

For example, if you write **You owe %9 %7 due on %2.**, then the resulting reminder will contain the following text: **You owe USD 1.200,50 due on 02-02-2014.**.

> [!NOTE]
> The due date is calculated according to the date formula that you enter. For more information, see [Using Date Formulas](ui-enter-date-ranges.md#using-date-formulas).

After you have set up the reminder terms, with additional levels and text, enter one of the codes on each of the customer cards. For more information, see [Register New Customers](sales-how-register-new-customers.md).

## To create a reminder automatically
A reminder is similar to an invoice. When you create a reminder, a reminder header as well as one or more reminder lines must be filled in. You can use a function to create reminders for all customers automatically.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminders**, and then choose the related link.
2. On the **Reminder** page, choose the **Create Reminders** action.
3. On the **Create Reminders** page, fill in the fields to define how and to whom the reminders are created.
4. Choose the **OK** button.

## To create a reminder manually
On the **Reminder** page, you can fill in the **General** FastTab manually and then have the lines filled in automatically.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminders**, and then choose the related link.
2. Choose the **New** action.
3. On the **General** FastTab, fill in the fields as necessary.
4. Choose the **Suggest Reminder Lines** action.
5. In the **Suggest Reminder Lines** batch job, fill in the fields to define how and to whom the reminders are created.
6. Select the **Include Entries On Hold** check box if you want the reminders to contain overdue open entries that are on hold.
7. Select the **Only Entries with Overdue Amounts** check box if you want the reminders to contain only overdue open entries. Only invoices and payments will be shown as these are the entries for which your customers' payments may be overdue.

    > [!Important]
    > Open entries that are on hold will be inserted, irrespective of the setting in the **Only Entries with Overdue Amounts** check box.

8. Choose the **OK** button.

## To replace reminder texts  
There are several ways you can determine the text that appears on the printed reminder. In some cases, you may want to replace the beginning and ending texts that have been defined for the current level with those from a different level.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminders**, and then choose the related link.
2. Open the relevant reminder, and then choose the **Update Reminder Text** action.
3. On the **Update Reminder Text** page, enter the required level in the **Reminder Level** field.
3. Choose the **OK** button to update the beginning and ending texts.

## To issue a reminder
After you have created reminders and made any needed modifications, you can either print test reports or issue the reminders.

When you issue a reminder, the data is transferred to a separate page for issued reminders. At the same time, reminder entries are posted. If interest or an additional fee has been calculated, entries are posted to the customer ledger and the general ledger.

When a reminder is issued, the entries are posted according to your specifications on the **Reminder Terms** page. This specification determines whether interest and/or additional fees are posted to the customer's account and the general ledger. Setup on the **Customer Posting Groups** page determines which accounts are posted to.

For each customer ledger entry on the finance charge memo, an entry is created on the **Reminder/Fin. Charge Entries** page.

If the **Post Interest** or the **Post Additional Fee** check boxes are selected on the **Reminder Terms** page, then the following entries are also created:

- One entry on the **Cust. Ledger Entries** page
- One receivables entry in the relevant G/L account
- One interest and/or one additional fee entry in the relevant G/L account

In addition, issuing the reminder may result in VAT entries.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminders**, and then choose the related link.
2. Select the relevant reminder, and then choose the **Issue** action.
3. On the **Issue Reminders** page, fill in the fields as necessary.
4. Choose the **OK** button

The reminder is either printed for sent to an specified email as a PDF attachment.

### To cancel an issued reminder
If reminders were issued in error, you can cancel them before they are sent out. You can do this either one by one or as a batch.
1. On the **Issued Reminders** page, select one or more lines for issued reminders that you want to cancel, and then choose the **Cancel** action.
2. On the **Cancel Issued Reminders** page, fill in the fields as necessary, and then choose the **OK** button.

## To set up finance charge terms
You must set up a code representing each finance charge calculation. Then you can enter this code in the **Fin. Charge Terms Code** field on customer or vendor cards.

Finance charges can be calculated using either the average daily balance method or the balance due method.

* Balance due method

    The finance charge is simply a percentage of the overdue amount:  
    *Balance Due method* - *Finance Charge* = *Overdue Amount* x *(Interest Rate / 100)*

*   Average daily balance method

    The number of days the payment is overdue is taken into account:  
    *Average Daily Balance method* - *Finance Charge* = *Overdue Amount* x *(Days Overdue / Interest Period)* x *(Interest Rate/100)*

In addition, each code in the Finance Charge Terms table is linked to a subtable, the Finance Charge Text table. For each set of finance charge terms, you can define a beginning and/or an ending text to be included on the finance charge memo.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Finance Charge Terms**, and then choose the related link.  
2. Fill in the fields as necessary.
3. To use more than one combination of finance charge terms, set up a code for each one.

    For each finance charge term, you can specify individual conditions, which can include additional fees in both LCY and in foreign currency. You can define many additional fees in foreign currencies for each code on the **Finance Charge Terms** page.
4. Choose the **Currencies** action.
5. On the **Currencies for Fin. Chrg. Terms** page, define for each term a currency code and an additional fee.

    > [!NOTE]  
    > When you create finance charges in a foreign currency, the foreign currency conditions that you set up here will be used to create finance charge memos. If there are no foreign currency finance charge conditions set up, then the LCY finance charge conditions that are set up on the **Finance Charge Terms** page will be used and then converted to the relevant currency.

    For each finance charge term, you can specify text that will be printed before (**Beginning Text**) or after (**Ending Text**) on the entries on the finance charge memo.  
6. Choose the **Beginning Text** or **Ending Text** actions respectively, and fill on the **Finance Charge Text** page.
7. To automatically insert related values in the resulting finance charge text, enter the following placeholders in the **Text** field.

|Placeholder|Value|  
|-----------------|-----------|  
|%1|Content of the **Document Date** field on the finance charge memo header|  
|%2|Content of the **Due Date** field on the finance charge memo header|  
|%3|Content of the **Interest Rate** field on the related finance charge terms|  
|%4|Content of the **Remaining Amount** field on the finance charge memo header|  
|%5|Content of the **Interest Amount** field on the finance charge memo header|  
|%6|Content of the **Additional Fee** field on the finance charge memo header|  
|%7|The total amount of the reminder|  
|%8|Content of the **Currency Code** field on the finance charge memo header|  
|%9|Content of the **Posting Date** field on the finance charge memo header|  

## To create a finance charge memo manually  
A finance charge memo is similar to an invoice. You can fill in a header manually and have the lines filled in for you, or you can create finance charge memos for all customers automatically.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Finance Charge Memos**, and then choose the related link.  
2. Choose the **New** action, and then fill in the fields as necessary.  
3. Choose **Suggest Fin. Charge Memo Lines** action.
4. On the **Suggest Finance Charge Memo Lines** page, set a filter on the **Cust. Ledger Entry** FastTab if you want to create finance charge memos only for specific entries.

    > [!NOTE]
    > Although they are listed, selecting **Payment** and **Credit Memo** as **Document Type** filters will not have any effect because the **Suggest Finance Charge Memo Lines** function only handles positive amounts.
5.  Choose the **OK** button to start the batch job.  

## To update finance charge memo texts  
In some cases, you may want to modify the beginning and ending text that you have set up for the finance charge terms. If you do this at a time when you have created, but not yet issued, finance charge memos, you can update the memos with the modified text.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Finance Charge Memo**, and then choose the related link.  
2. open the finance charge memo that you want to change text for, and then choose the **Update Finance Charge Text** action.
3. On the **Update Finance Charge Text** page, you can set a filter if you want to update several memos.
4. Choose the **OK** button to update the beginning and ending texts.  

## To issue finance charge memos
After you have created finance charge memos and made any needed modifications, you can either print test reports or issue the finance charge memos.

When a reminder is issued, the entries are posted according to your specifications on the **Finance Charge Terms** page. This specification determines whether interest and/or additional fees are posted to the customer's account and the general ledger. Setup on the **Customer Posting Groups** page determines which accounts are posted to.

For each customer ledger entry on the finance charge memo, an entry is created on the **Reminder/Fin. Charge Entries** page.

If the **Post Interest** or the **Post Additional Fee** check boxes are selected on the **Finance Charge Terms** page, then the following entries are also created:

- One entry on the **Cust. Ledger Entries** page
- One receivables entry in the relevant G/L account
- One interest and/or one additional fee entry in the relevant G/L account

In addition, issuing the finance charge memo may result in VAT entries.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Finance Charge Memos**, and then choose the related link.
2. Select the relevant memo, and then choose the **Issue** action.
3. On the **Issue Finance Charge Memos** page, fill in the fields as necessary.
4. Choose the **OK** button

The finance charge memo is either printed for sent to an specified email as a PDF attachment.

### To cancel an issued finance charge memo
If finance charge memos were issued in error, you can cancel them before they are sent out. You can do this either one by one or as a batch.
1. On the **Issued Finance Charge Memos** page, select one or more lines for issued finance charge memos that you want to cancel, and then choose the **Cancel** action.
2. On the **Cancel Issued Fin. Charge Memos** page, fill in the fields as necessary, and then choose the **OK** button.

## To view reminder and finance charge entries  
When you issue a reminder, a reminder entry is created on the **Reminder/Fin. Charge Entries** page for each reminder line that contains a customer ledger entry. You can then get an overview of the created reminder entries for a specific customer.    
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2. Open the relevant customer card, and then choose the **Ledger Entries** action.
3. On the **Customer Ledger Entries** page, select the line with the ledger entry you want to see the reminder entries for, and then choose the **Reminder/Fin. Charge Entries** action.

## See Related Training at [Microsoft Learn](/learn/paths/process-financial-periodic-activities-dynamics-365-business-central/)

## See Also
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
