---
title: Close income statement accounts
description: At year closing, you must run the Close Income Statement batch job to close the accounting periods that make up the fiscal year.
author: jswymer
ms.topic: how-to
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.date: 08/05/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Close income statement accounts

When a fiscal year is over, you must close the periods that comprise it. To do this, you run the **Close Income Statement** batch job. This job transfers the year's result to an account in the balance sheet and closes the income statement accounts. You do this by creating lines in a journal, which you then can post.

## To run the Close Income Statement batch job

1. Close the fiscal year. The fiscal year must closed before the batch job can be run. For more information, see [Close Accounting Periods](year-close-account-periods.md).
2. [!INCLUDE[open-search](includes/open-search.md)], enter **Close Income Statement**, and then choose the related link.
3. Choose the **OK** button to run the batch job.

## About the Close Income Statement batch job

The batch job processes all general accounts of the income statement type and creates entries that cancel out their respective balances. That is, each entry is the sum of all the general ledger entries on the account in the fiscal year. These new entries are placed in a journal in which you must specify a balancing account and retained earnings account in the balance sheet before you post. When you post the journal, an entry is posted to each income statement account so that its balance becomes zero and at the same time the year's result is transferred to the balance sheet.

You must post the journal yourself. The batch job doesn't post the entries automatically, except when an additional reporting currency is being used. When an additional reporting currency is being used, the batch job posts entries directly to the general ledger.

The date on the lines that the batch job inserts in the journal is always a closing date for the fiscal year. The closing date is a fictitious date between the last day of the old fiscal year and the first day of the new year. The advantage of posting on a closing date is that you maintain the correct balances for the ordinary dates of the fiscal year.

The **Close Income Statement** batch job can be used several times. You can post in a previous fiscal year, even after the income statement accounts have been closed, if you run the batch job again.

## Related information

[Closing Books](year-close-books.md)    
[Post the Year-End Closing Entry](year-how-post-year-end-close-entry.md)    
[Work with Accounting Periods and Fiscal Years](finance-accounting-periods-and-fiscal-years.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
