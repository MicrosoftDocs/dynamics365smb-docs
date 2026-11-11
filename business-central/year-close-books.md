---
title: Close the Books
description: Learn about the process of closing the books for a fiscal year or period, and what happens after you close at the end of a year.
author: jswymer
ms.topic: overview
ms.devlang: al
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.search.form: 100
ms.date: 11/11/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Close the books
After you ensure that all your accounts are up-to-date, and you allocate costs and income, then you can close the books for a fiscal year or period.

You aren't required to close a year, but doing so will make working in the system easier for you because you'll be able to take advantage of the convenient filtering options provided. You also don't have to worry about losing details of transactions when you close because all details are retained, even after you close the year.

## Follow the year-end closing process
The process for closing the book includes these main tasks:

1. Close the fiscal year.

    A fiscal year consists of accounting periods defined on the **Accounting Periods** page. A typical fiscal year contains 12 periods of one month each, but you can also choose another method of defining a year.

    Learn more in [Close Accounting Periods](year-close-account-periods.md).
1. Post any prior-year adjusting entries.

    You might need to post adjustments for prepaid or accrued items after closing a fiscal year. These transactions are called adjusting entries. General ledger entries posted to a closed fiscal year have the **Prior-Year Entry** checkbox selected. You can still post to the closed year if the posting date is within the allowed posting periods. Learn more in [Specify posting periods](finance-how-specify-posting-periods.md).
1. Transfer balances from the income statement accounts to the balance sheet.

    After a fiscal year has been closed and all prior-year entries have been posted, the income statement accounts must be closed and the net income for the year must be transferred to an account under owners' equity on the balance sheet. Use the Close Income Statement batch job for this purpose. The batch job processes all general ledger accounts of the type Income Statement and creates entries that reverse their balances. These entries are placed in a journal from which they can be posted. The batch job doesn't post them automatically, except when an additional reporting currency is used. When an additional reporting currency is used, the batch job posts directly to the general ledger.

    Learn more in [Close Income Statement](year-close-income-statement.md).
1. Post the year-end closing entry along with the offsetting equity account entries.

    If the **Close Income Statement** batch job created journal lines, review them before posting. If you didn't specify a retained earnings account in the batch job, enter a balancing entry that posts the net income to the correct general ledger account under owners' equity on the balance sheet. Then post the journal. If you use an additional reporting currency, the batch job has already posted the closing entries directly.

    Learn more in [Post Year-End Closing Entry](year-how-post-year-end-close-entry.md).

## What happens when you close

The **Close Year** action on the **Accounting Periods** page marks the fiscal year's periods as closed. You can't reopen the fiscal year. This action doesn't transfer income statement balances or create closing entries. General ledger entries posted to the closed year have the **Prior-Year Entry** checkbox selected.

The **Close Income Statement** batch job creates the closing entries. Unless you use an additional reporting currency, you review and post the generated journal lines to transfer the year's result to retained earnings. You can adjust the offsetting equity entries before posting. For example, if your company has several divisions, you can allocate the result to each division's equity account.

You can still post to a closed fiscal year if the posting date is allowed. If you post more entries to income statement accounts, run **Close Income Statement** again and post any generated journal lines.

## Related information

[Work with accounting periods and fiscal years](finance-accounting-periods-and-fiscal-years.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]