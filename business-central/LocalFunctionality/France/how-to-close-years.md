---
title: Close Years [FR]
description: Learn how to close fiscal years and manage accounting periods in the French version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: close fiscal years, close accounting periods, French version
ms.date: 04/15/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Close years in the French version

When a fiscal year is over, you must close the periods that it comprises.  

## Close a year  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Accounting Periods**, and then choose the relevant link.  
1. Choose the **Close Year** action.  

    If more than one fiscal year is open, the earliest one should be closed. A message appears to identify the year that should be closed and explains the consequences of closing it.  

1. To close the year, choose the **Yes** button.  

When the fiscal year is closed, the **Closed** and **Date Locked** fields are selected for all the periods in the year. At this point the fiscal year can't be opened again, and you can't clear the **Closed** or **Date Locked** fields.  

> [!WARNING]  
> You can't close a fiscal year before you create a new one. When a fiscal year is closed, you can't change the starting date of the following fiscal year.  

Even though a fiscal year is closed, you can still post general ledger entries to it until you fiscally close the fiscal year. When you do this, the entries are marked as posted to a closed fiscal year, and the Prior-Year Entry field is selected. Learn more in [Fiscally Close Years](how-to-fiscally-close-years.md).  

After a fiscal year is closed, you must close the income statement accounts and transfer the year's results to an account in the balance sheet. You can repeat this each time you post to the closed fiscal year.  

After a fiscal year is fiscally closed, it can't be opened again, and general ledger entries can't be posted.  

## Related information

- [Fiscally Close Years](how-to-fiscally-close-years.md)
- [Year End Processes Overview](year-end-processes-overview.md)
- [Post the Year-End Closing Entry](how-to-post-the-year-end-closing-entry.md)
- [Closing Years and Periods](../../year-close-years-periods.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
