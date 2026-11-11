---
title: Close Income Statement Accounts
description: Learn how to run the Close Income Statement batch job to close income statement balances and transfer the year's result to retained earnings.
author: jswymer
ms.topic: how-to
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.date: 11/11/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Close income statement accounts

After you close a fiscal year on the **Accounting Periods** page, run the **Close Income Statement** batch job to close income statement balances. The batch job creates journal lines that reverse those balances and transfer the year's result to retained earnings when you post the journal. It doesn't close the accounting periods.

## To run the Close Income Statement batch job

If you use an additional reporting currency, the batch job posts entries directly to the general ledger. Review the options before running it. You must specify a retained earnings account, and the batch job uses the **Details** option for posting to that account.

1. Close the fiscal year. Learn more in [Close accounting periods](year-close-account-periods.md).
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Close Income Statement**, and then choose the related link.
1. Check that **Fiscal Year Ending Date** is the last ordinary date of the fiscal year to close.
1. In **Gen. Journal Template** and **Gen. Journal Batch**, select where to create the closing journal lines. Fill in **Document No.** to identify the entries.
1. In **Retained Earnings Acc.**, select the balance sheet account that receives the year's result. If you don't use an additional reporting currency, you can leave this field blank and complete the retained earnings entry in the journal before posting.
1. In **Post to Retained Earnings Acc.**, choose **Balance** to create a summarized retained earnings line, or **Details** to use the retained earnings account as the balancing account on each closing line.
1. To close balances separately by business unit or dimension, select **Business Unit Code** or choose the dimensions under **Close by**.
1. Choose **OK** to run the batch job.
1. If the batch job created journal lines, open the selected journal batch, review and complete the lines, and post the journal. Learn more in [Post the year-end closing entry](year-how-post-year-end-close-entry.md).

## About the Close Income Statement batch job

The batch job processes posting accounts of the **Income Statement** type and creates entries that reverse their balances. The entries can be split by business unit or dimension, depending on your **Close by** choices. If you specify **Retained Earnings Acc.**, the batch job also creates the balancing entries for that account. Otherwise, complete the retained earnings entry in the journal before posting. When you post the journal, the income statement balances become zero and the year's result is transferred to the balance sheet.

You must post the journal yourself. The batch job doesn't post the entries automatically, except when an additional reporting currency is being used. When an additional reporting currency is being used, the batch job posts entries directly to the general ledger.

The date on the lines that the batch job inserts in the journal is always a closing date for the fiscal year. The closing date is a fictitious date between the last day of the old fiscal year and the first day of the new year. The advantage of posting on a closing date is that you maintain the correct balances for the ordinary dates of the fiscal year.

You can run the **Close Income Statement** batch job several times. If you post more entries to income statement accounts in the closed year, run the batch job again and post any generated journal lines. Posting to the closed year must still be within the allowed posting periods. Learn more in [Specify posting periods](finance-how-specify-posting-periods.md).

## Related information

[Closing Books](year-close-books.md)    
[Post the Year-End Closing Entry](year-how-post-year-end-close-entry.md)    
[Work with Accounting Periods and Fiscal Years](finance-accounting-periods-and-fiscal-years.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
