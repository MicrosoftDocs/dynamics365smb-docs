---
title: Set Up Finance Charge Terms
description: Learn how to set up Business Central so that you can inform customers of added charges by sending finance charge memos.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: payment due, debt, overdue, fee, charge
ms.search.form: 6, 494
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Set Up Finance Charge Terms

When a customer does not pay by the due date, you can have finance charges calculated automatically and add them to the overdue amounts on the customer's account. You can inform customers of the added charges by sending finance charge memos. But first, you must set up a code that represents each finance charge calculation. Then you can enter this code in the Fin. Charge Terms Code field on customer cards.  

## Finance charge terms

You must set up finance charge terms for each finance charge calculation, and then assign the terms to the customer in the **Fin. Charge Terms Code** field on the **Customer** page.

Finance charges can be calculated using either the average daily balance or the balance due methods.

* Average daily balance  
  
  The number of days the payment is overdue is taken into account:  
  *Average Daily Balance method* - *Finance Charge* = *Overdue Amount* x *(Days Overdue / Interest Period)* x *(Interest Rate/100)*

* Balance due  
  
  The finance charge is a percentage of the overdue amount:  
  *Balance Due method* - *Finance Charge* = *Overdue Amount* x *(Interest Rate / 100)*

Additionally, each term in the Finance Charge Terms table is linked to a subtable, the Finance Charge Text table. For each set of finance charge terms, you can define a beginning and/or an ending text to include on the finance charge memo.

### To set up finance charge terms

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Finance Charge Terms**, and then choose the related link.  
2. Fill in the fields as necessary.
3. To use more than one combination of finance charge terms, set up a code for each one.

    For each finance charge term, you can specify individual conditions that can include additional fees in both LCY and in foreign currency. You can define additional fees in foreign currencies for each term on the **Finance Charge Terms** page.
4. Choose the **Currencies** action.
5. On the **Currencies for Fin. Chrg. Terms** page, define for each term a currency code and an additional fee.

    > [!NOTE]  
    > When you create finance charges in a foreign currency, the foreign currency conditions that you set up here will be used to create finance charge memos. If there are no foreign currency finance charge conditions set up, the LCY finance charge conditions specified on the **Finance Charge Terms** page will be used and then converted to the relevant currency.

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

## Related information

[Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Set Up Reminder Terms and Levels](finance-setup-reminders.md)  
[Setting Up Finance](finance-setup-finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
