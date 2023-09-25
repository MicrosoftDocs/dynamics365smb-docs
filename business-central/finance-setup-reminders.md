---
title: Set Up Reminder Terms and Levels
description: Learn how to set up Business Central so that you can send a reminder to a customer about a payment that is due and add charges, or fees to the payment because of the delay.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment due, debt, overdue, fee, charge, reminder
ms.search.form: 431, 432, 436, 478
ms.date: 02/09/2022
ms.author: bholtorf

---
# Set Up Reminder Terms and Levels

You can use reminders to remind customers about overdue amounts. [!INCLUDE [reminder-terms](includes/reminder-terms.md)]

## Reminder terms

If customers have overdue payments, you must decide when and how to send them a reminder. In addition, you may want to debit their accounts for interest or fees. You can set up any number of reminder terms.  

> [!NOTE]
> If you want to calculate interest on overdue payments, you can do so when you create reminders. If, however, you just want to calculate interest and inform your customers about this without sending reminders, you should use [finance charge memos](finance-setup-finance-charges.md). For more information, see [Reminders](receivables-collect-outstanding-balances.md#reminders) or [Finance Charges](receivables-collect-outstanding-balances.md#finance-charges), respectively.

### To set up reminder terms

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminder Terms**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  
3. To use more than one combination of reminder terms, set up a code for each one.

## Reminder levels

For each reminder terms code, you can define an unlimited number of reminder levels. The first time a reminder is created for a customer, the setting from level 1 is used. When the reminder is issued, the level number is registered on the reminder entries that are created and linked to the individual customer ledger entries. If it is necessary to remind the customer again, all reminder entries linked to open customer ledger entries are checked to locate the highest level number. The conditions from the next level number will then be used for the new reminder.

If you create more reminders than you have defined levels for, the conditions for the highest level will be used. You can create as many reminders as are allowed by the **Max. No of Reminders** field in the reminder terms.

### To set up reminder levels

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Reminder Terms**, and then choose the related link.  
2. On the **Reminder Terms** page, select the line with the terms you want to set up levels for, and then choose **Levels** action.  
3. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

    > [!TIP]
    > The setting of the **Calculate Interest** field determines if interest will appear on the reminder when the reminder is issued. However, the **Post Interest** field in the **Reminder Terms** page determines if the calculated interest must be posted to G/L and customer accounts.
    >
    > To indicate that interest should be calculated, choose the **Calculate Interest** field.

    Optionally, for each reminder level, specify additional fees in both LCY and in foreign currency. You can define many additional fees in foreign currencies for each code on the **Reminder Levels** page.  

    The additional fees can be calculated in three different ways that are defined by the value of the **Add. Fee Calculation Type** field.  

    - **Fixed**

        Fees are calculated based on the values of the **Additional Fee** fields on the line for the reminder level itself.  
    - **Single Dynamic**

        Fees are calculated based on the values of the fields on the relevant line in the **Additional Fee Setup** page for that reminder level.
    - **Accumulated Dynamic**

        Fees are calculated based on the values of the fields on the combined lines in the **Additional Fee Setup** page for that reminder level.

4. Choose the **Currencies** action.
5. On the **Currencies for Reminder Levels** page, define for each reminder level code and corresponding reminder level number a currency code and an additional fee.

    > [!NOTE]  
    > When you create reminders in a foreign currency, the foreign currency conditions that you set up here will be used to create reminders. If there are no foreign currency reminder conditions set up, the LCY reminder conditions that are set up on the **Reminder Levels** page will be used and then converted to the relevant currency.

    For each reminder level, you can specify text that will be printed before (**Beginning Text**) or after (**Ending Text**) on the entries on the reminder.

6. Choose the **Beginning Text** or **Ending Text** actions respectively, and fill in the **Reminder Text** page.
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
    > The due date is calculated according to the date formula that you enter. For more information, see [Use Date Formulas](ui-enter-date-ranges.md#use-date-formulas).

After you have set up the reminder terms, with additional levels and text, enter one of the codes on each of the customer cards. For more information, see [Register New Customers](sales-how-register-new-customers.md).  

## See also

[Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Send Reminders of Outstanding Balances](receivables-send-reminders.md)  
[Set Up Finance Charge Terms](finance-setup-finance-charges.md)  
[Setting Up Finance](finance-setup-finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
