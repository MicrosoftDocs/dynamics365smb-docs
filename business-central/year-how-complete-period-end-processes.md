---
title: Overview of Tasks to Close Accounting Periods
description: Review optional period-end tasks in Business Central, including posting journals, reconciling balances, running reports, and completing tax statements.
author: jswymer
ms.topic: overview
ms.devlang: al
ms.search.keywords: year closing, close accounting period, close fiscal year, aging, creditor payments, vendor payments
ms.date: 11/11/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Overview of tasks to close accounting periods

[!INCLUDE[prod_short](includes/prod_short.md)] doesn't force you to close periods, however, there are many period-end (month-end) activities that you can do. This article provides an overview of optional processes and activities for closing periods.  

## Complete general ledger tasks

* Specify system-wide and user-specific posting periods.  

    Posting periods specify the dates between which posting is allowed. Depending on your business, you might restrict posting dates at the start of the period-end process or after completing it. Closing a fiscal year doesn't prevent further posting to that year. Learn more in [Specify posting periods](finance-how-specify-posting-periods.md).
* Make all necessary general ledger (G/L) adjustments.  
* Update and post recurring journals.  
  <!--* Process Consolidations-->
* Run financial reports as follows:  
  * Open the **Financial Reports** page, select a report, and then choose **Print/PDF**.

## Complete sales and receivables tasks

* Post all sales orders, invoices, credit memos, and return orders.  
* Post all cash receipt journals.  
* Update and post recurring journals related to sales and receivables.  
* Reconcile accounts receivable to the general ledger.  
* Run the **Delete Invoiced Sales Orders** batch job.  

## Complete purchases and payables tasks

* Post all purchase orders, invoices, credit memos, and return orders.  
* Post all payment journals.  
* Update and post recurring journals related to purchases and payables.  
* Run the **Aged Accounts Payable (Excel)** report and reconcile accounts payable to the general ledger.
* Run the **Delete Invoiced Purchase Orders** batch job.  

## Complete fixed asset tasks

* Post any outstanding maintenance costs through fixed asset journals or invoices.
* Post adjustments.
* Post appreciation.
* Post depreciation.
* Update and post the recurring fixed asset journal.

## Process intercompany transactions

* Process intercompany transactions.

## Calculate and process sales tax

* Complete tax statements.  

## Related information

[Closing Years and Periods](year-close-years-periods.md)  
[Closing Books](year-close-books.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
