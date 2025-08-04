---
title: Optional activities for closing periods
description: This article outlines the optional processes and activities for closing accounting periods in Business Central.  
author: jswymer
ms.topic: overview
ms.devlang: al
ms.search.keywords: year closing, close accounting period, close fiscal year, aging, creditor payments, vendor payments
ms.date: 08/02/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Overview of tasks to close accounting periods

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't force you to close periods, however, there are many period-end (month-end) activities that you can do. This article provides an overview of optional processes and activities for closing periods.  

## General ledger

* Specify system-wide and user-specific posting periods.  

    This specifies the dates between which you allow posting. Depending on your business, you might want to allow posting at the start of the period, or toward the end. Learn more at [Specify Posting Periods](finance-how-specify-posting-periods.md).  
* Make all necessary general ledger (G/L) adjustments.  
* Update and post recurring journals.  
  <!--* Process Consolidations-->
* Run financial reports as follows:  
  * Open the **Financial Reports** page, then choose the **Print** action.  

## Sales and receivables

* Post all sales orders, invoices, credit memos, and return orders.  
* Post all cash receipt journals.  
* Update and post recurring journals related to sales and receivables.  
* Reconcile accounts receivable to the general ledger.  
* Run the **Delete Invoiced Sales Orders** batch job.  

## Purchases and payables

* Post all purchase orders, invoices, credit memos, and return orders.  
* Post all payment journals.  
* Update and post recurring journals related to purchases and payables.  
* Run the **Aged Accounts Payable** report and reconcile accounts payable to the general ledger.  
* Run the **Delete Invoiced Purchase Orders** batch job.  

## Fixed assets

* Post all maintenance costs that have been posted through the fixed asset journals or invoices.
* Post adjustments.
* Post appreciation.
* Post depreciation.
* Update and post the recurring fixed asset journal.

## Intercompany

* Process intercompany transactions.

## Calculate and process sales tax

* Complete tax statements.  

## Related information

[Closing Years and Periods](year-close-years-periods.md)  
[Closing Books](year-close-books.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
