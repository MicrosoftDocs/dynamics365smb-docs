---
title: Set Up Multiple Interest Rates for Delayed Payment
description: This topic tells you how to calculate finance charges with multiple interest rates for a specific period. 
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 6, 431, 432, 572
ms.date: 06/16/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Set Up Multiple Interest Rates for Delayed Payment

You can use different interest rates for different periods for delayed payments in trade transactions. [!INCLUDE [multiple-interest-rates-def](includes/multiple-interest-rates-def.md)]

For example, a government specifies the maximum interest to be levied for a consumer. This interest rate can be changed twice a year on 01 January and 01 July. The interest rate between businesses (B2B) is agreed by the parties and there is no limit to that customer group. The announced rate is usually four percent more than the normal bank interest.

When you create finance charge terms and reminder terms, for delayed payment penalty, you can specify multiple interest rates so that the penalty fee is calculated from different interest rates in different periods.  

## To set up multiple interest rates

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Finance Charge Terms**, and then choose the related link.  
2. On the **Finance Charge Terms** page, select the required finance term, and then choose the **Interest Rates** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Choose the **OK** button.  
5. [!INCLUDE[open-search](includes/open-search.md)], enter **Reminder Terms**, and then choose the related link.  
6. On the **Reminder Terms** page, select the required reminder term, and then choose the **Levels** action.  
7. On the **Reminder Levels** page, for the relevant reminder levels, select the **Calculate Interest** field.  

When you issue a finance charge memo, the memo shows the finance charges with multiple interest rates for a specific time period. The memo also contains the contact details of the customer, the company issuing the memo, the additional amount, and the total amount. The opening entry on the memo is displayed in bold. The finance charges are calculated with multiple interest rates for a specific time period and are printed after the opening entry of the memo.  

## Related information

[Collect Outstanding Balances](receivables-collect-outstanding-balances.md)  
[Setting Up Finance](finance-setup-finance.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
