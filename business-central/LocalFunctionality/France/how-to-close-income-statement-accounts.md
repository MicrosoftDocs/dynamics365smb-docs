---
title: How to Close Income Statement Accounts [FR]
description: Learn how to close the income statement accounts in the French version of Business Central
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: income statement accounts, close income statement, close fiscal year, French version
ms.date: 04/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Close income statement accounts in the French version

Before you can run the **Close Income Statement** batch job, you must close the fiscal year. Learn more in [Fiscally Close Years](how-to-fiscally-close-years.md).  

## Steps to close income statement accounts  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Close Income Statement**, and then choose the relevant link.  
1. On the **Close Income Statement** page, on the **Options** FastTab, specify the conditions of the batch job.  
1. Choose the **OK** button.  

   When the batch job is finished, you must close the accounts.  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the relevant link.  
1. Select the general journal that contains the closing entries.  
1. Enter one line with a balancing entry that posts the net income to the correct general ledger account under owners' equity on the balance sheet.  
1. Choose the **Post** action to post the journal.  

## Related information

[Fiscally Close Years](how-to-fiscally-close-years.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
