---
title: How to Fiscally Close Years
description: Learn the process of fiscally closing periods in a fiscal year to prevent further general ledger postings.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: fiscal closing, close fiscal period, close accounting period, close fiscal year, French version
ms.date: 04/15/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Fiscally close years

When a fiscal year is complete, you must fiscally close the periods that it comprises to make sure that no more general ledger entries can be posted.  

Before fiscal closing is allowed, the following actions must be ensured:  

- The fiscal year is closed first. Learn more in [Close Years](how-to-close-years.md).  
- All journal lines that aren't posted for the year are either posted or deleted before the year is fiscally closed.
- All closing entries are up-to-date.  

## Process to fiscally close years  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Accounting Periods**, and then choose the relevant link.  
1. Choose the **Fiscally Close Year** checkbox.  

   If more than one fiscal year isn't fiscally closed, the earliest one should be fiscally closed. A message appears that identifies the year that should be closed and explains the consequences of closing it.  

1. To fiscally close the year, choose the **Yes** button.  

When the fiscal year is fiscally closed, the **Fiscally Closed** field for all the periods in the year is selected. The fiscally closed year can't be opened again, and you can't clear the **Fiscally Closed** field.  

## Related information

- [Close Years](how-to-close-years.md)
- [Year End Processes Overview](year-end-processes-overview.md)
- [Post the Year-End Closing Entry](how-to-post-the-year-end-closing-entry.md)
- [Closing Years and Periods](../../year-close-years-periods.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
