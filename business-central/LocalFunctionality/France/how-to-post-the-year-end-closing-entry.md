---
title: How to Post the Year-End Closing Entry [FR]
description: Learn how to post the year-end closing entries after you use the Close Income Statement batch job.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: year end closing, close income statement, close income statement batch job, French version
ms.date: 04/16/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Post the year-end closing entry in the French version

After you use the **Close Income Statement** batch job to generate the year-end closing entry or entries, you must open the journal you specified in the batch job, and then review and post the entries.  

## Steps to post the year-end closing entry  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journal**, and then choose the related link.  
1. Review the entries.  
1. Choose the **Post** action.  
1. In the posting confirmation page, choose the **Yes** button.  

If an error is detected, an error message displays. If the posting is successful, the system removes the posted entries from the journal.  

Once posted, an entry is posted to each income statement account so that its balance becomes zero, and the year's result is transferred to the balance sheet.  

## Related information

- [Year End Processes Overview](year-end-processes-overview.md)
- [Close Years](how-to-close-years.md)
- [Fiscally Close Years](how-to-fiscally-close-years.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
