---
title: Set Up Reminder Terms and Levels
description: Set up Business Central so you can send reminders about payments due and add charges, or fees because of the delay.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: payment due, debt, overdue, fee, charge, reminder
ms.search.form: 431, 432, 436, 478
ms.date: 06/10/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Set up reminder terms and levels

You can use reminders to inform customers about overdue amounts and to request payment. [!INCLUDE [reminder-terms](includes/reminder-terms.md)]

> [!TIP]
> After you set up reminder terms and levels, you can include them in automated processes for creating, issuing, and sending reminders. To learn more about the automated process, go to [Automate reminders in collections](finance-automate-reminders.md).

## Reminder terms

If customers have overdue payments, you must decide when and how to send a reminder. In addition, you might want to debit their accounts for interest or fees. You can set up any number of reminder terms.  

> [!NOTE]
> If you want to calculate interest on overdue payments, you can do so when you create reminders. If, however, you just want to calculate interest and inform your customers about this without sending a reminder, use a [finance charge memo](finance-setup-finance-charges.md). To learn more, go to [Reminders](receivables-collect-outstanding-balances.md#reminders) or [Finance Charges](receivables-collect-outstanding-balances.md#finance-charges).

### Set up attachment and email body texts for communications

On the **Reminder Terms Setup** page, you can set up attachment texts and standard email messages to use either for all reminder levels, or create specific messages for each level. For example, the message you send for the first reminder level might have a different tone or content than the second or third. To create attachment and email message texts for all levels, choose **Customer Communication** at the top of the page. To create messages for specific lines, on the **Reminder Level** FastTab, choose a line and then choose the **Customer Communication** action on the FastTab.

By default, attachment and email texts use your language setting. If you issue reminders to customers in other countries, however, you might want to communicate in different languages. You can create texts for each language that [!INCLUDE [prod_short](includes/prod_short.md)] supports by using the **Add text for language** action. If you do, ensure that the languages are the same for attachment texts and email texts. If they don't match, and the reminder term has more than one level, the automation might not be able to customize the message for one or more levels. To verify that the languages match, use the **Overview communications** action and compare the communications for the texts.

When you send an email, the reminder is a report you attach to the email. You define the report that generates the reminder on the **Report Selection Reminder/Finance Charge** page, where you also select the report that holds the email body text in the **Email Body Layout Name** field. When you send emails to your customers, the texts on the **Email Text** FastTab are inserted in the report selected in the **Email Body Layout Name** field. The standard report has a text field for this text. If you want, you can edit this report, for example, to add or remove content. Edit the layout of these reports on the **Report Layouts** page. To learn more about report layouts, go to [Get Started Creating Report Layouts](ui-get-started-layouts.md).

> [!NOTE]
> Communicating by email directly from [!INCLUDE [prod_short](includes/prod_short.md)] requires that you're set up to do that. To learn more about connecting email accounts with [!INCLUDE [prod_short](includes/prod_short.md)], go to [Set up email](admin-how-setup-email.md).

### Set up reminder terms

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminder Terms**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  
3. To use more than one combination of reminder terms, set up a code for each one.

## Reminder levels

For each reminder term, you can define an unlimited number of reminder levels, though most companies use only two or three levels. The first time a reminder is created for a customer, the setting from level 1 is used. When the reminder is issued, the level number is registered on the reminder entries that are created and linked to the individual customer ledger entries. If it's necessary to remind the customer again, all reminder entries linked to open customer ledger entries are checked to locate the highest level number. The conditions from the next level number will then be used for the new reminder.

If you create more reminders than you define levels for, the conditions for the highest level are used. You can create as many reminders as are allowed by the **Max. No of Reminders** field in the reminder terms.

### To set up reminder levels

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminder Terms**, and then choose the related link.  
2. On the **Reminder Terms** page, select the line with the terms you want to set up levels for, and then choose the **Levels** action.  
3. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

    > [!TIP]
    > The setting of the **Calculate Interest** field determines if interest will appear on the reminder when the reminder is issued. However, the **Post Interest** field in the **Reminder Terms** page determines if the calculated interest must be posted to G/L and customer accounts.
    >
    > To indicate that interest should be calculated, choose the **Calculate Interest** field.

    Optionally, for each reminder level, specify extra fees in both local and foreign currencies. You can define many extra fees in foreign currencies for each code on the **Reminder Levels** page.  

    The extra fees can be calculated in three different ways that are defined by the value of the **Add. Fee Calculation Type** field.  

    - **Fixed**

        Fees are calculated based on the values of the **Additional Fee** fields on the line for the reminder level itself.  
    - **Single Dynamic**

        Fees are calculated based on the values of the fields on the relevant line in the **Additional Fee Setup** page for that reminder level.
    - **Accumulated Dynamic**

        Fees are calculated based on the values of the fields on the combined lines in the **Additional Fee Setup** page for that reminder level.

4. Choose the **Currencies** action.
5. On the **Currencies for Reminder Levels** page, define for each reminder level code and corresponding reminder level number a currency code and an extra fee.

    > [!NOTE]  
    > When you create reminders in a foreign currency, the foreign currency conditions that you set up here will be used to create reminders. If there are no foreign currency reminder conditions set up, the LCY reminder conditions that are set up on the **Reminder Levels** page will be used and then converted to the relevant currency.

    For each reminder level, you can specify text that will be printed before (**Beginning Text**) or after (**Ending Text**) on the entries on the reminder.

6. Choose the **Beginning Text** or **Ending Text** actions respectively, and fill in the **Reminder Text** page.
7. To automatically insert related values in the reminder text, you can enter the following placeholders in the **Text** field.  

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

    For example, if you write **You owe %9 %7 due on %2.**, the reminder contains the following text: **You owe USD 1.200,50 due on 02-02-2024.**.

    > [!NOTE]
    > [!INCLUDE [prod_short](includes/prod_short.md)] calculates the due date according to the date formula that you enter. To learn more, go to [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas).

8. To specify the language for an email message, choose the **Add text for language** action. The **Language Code** field updates to show your selection. On the **Email Text** FastTab, enter the content of the message in the selected language.

After you set up the reminder terms, you can assign them to customers on Customer Card pages. To learn more, go to [Register New Customers](sales-how-register-new-customers.md).  

## Related information

[Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Send Reminders of Outstanding Balances](receivables-send-reminders.md)  
[Set Up Finance Charge Terms](finance-setup-finance-charges.md)  
[Setting Up Finance](finance-setup-finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
