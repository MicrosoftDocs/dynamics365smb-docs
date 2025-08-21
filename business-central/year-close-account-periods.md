---
title: Close accounting periods for a fiscal year
description: This article describes how to close the accounting periods that make up the fiscal year for year end closing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.search.form: 100,
ms.date: 08/05/2024
ms.service: dynamics-365-business-central
---

# Close accounting periods

When a fiscal year is over, you must close the periods that comprise it.

## To close accounting periods

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Accounting Periods**, and then choose the related link.
2. On the **Accounting Periods** page, choose the **Close Year** action.

    If more than one fiscal year is open, the earliest one is automatically selected to be closed. A message identifies the year that will close and the results of its closing.
3. To close the year, choose the **Yes** button.

The fiscal year is closed, and the **Closed** and **Date Locked** fields for all the periods in the year are selected. The fiscal year can't be opened again and you can't remove the check mark from the **Closed** or **Date Locked** fields.

> [!NOTE]  
> You can't close a fiscal year before you create a new one. Notice that after a fiscal year is closed, you can't change the starting date of the following fiscal year.

Although a fiscal year is closed, you can still post general ledger entries to it. When you do, the entries are marked as posted to a closed fiscal year and the **Prior-Year Entry** field is selected.

After a fiscal year is closed, you must close the income statement accounts and transfer the year's results to an account in the balance sheet. You can repeat this every time that you post to the closed fiscal year.

## Related information

[Closing Books](year-close-books.md)    
[Post the Year-End Closing Entry](year-how-post-year-end-close-entry.md)    
[Work with Accounting Periods and Fiscal Years](finance-accounting-periods-and-fiscal-years.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
