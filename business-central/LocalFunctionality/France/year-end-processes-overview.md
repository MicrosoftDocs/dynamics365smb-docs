---
title: Year End Processes Overview [FR]
description: Overview of the fiscal year-end closing processes in the French version of Business Central, including compliance with French regulations.
author: brentholtorf
ms.topic: overview
ms.devlang: al
ms.search.keywords: fiscal closing process, year-end closing, year end process, French version
ms.date: 04/16/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Year end processes overview in the French version

Year end closing in [!INCLUDE[prod_short](../../includes/prod_short.md)] involves three steps:  

1. Closing the fiscal year. Learn more in [Fiscally Close Accounting Periods](how-to-fiscally-close-accounting-periods.md).  
1. Generating a year-end closing entry using the **Close Income Statement** option along with the offsetting equity account entries. Learn more in [Posting the year-end closing entry](how-to-post-the-year-end-closing-entry.md).  
1. Fiscally closing the fiscal year. Learn more in [Fiscally Close Years](how-to-fiscally-close-years.md).  

According to the French law *NF Logiciel compatibilité informatisée* the system has to refuse the creation of a third open fiscal year, so only two open fiscal years are allowed at the same time.  

So in time you're required to close a year. You also don't have to worry about losing details of transactions when you close because all details are retained, even after you (fiscally) close the year.  

When you close at the end of the year, the system moves your earnings from calculated earnings, or the Current Earnings account, to a posted account, or the Retained Earnings account. The system also marks the fiscal year as "closed," and marks all subsequent entries for the closed year as "prior year entries."  

The system then generates a closing entry, but it doesn't post the entry automatically. You're given the opportunity to make the offsetting equity account entry or entries, which allows you to decide how to allocate your closing entry. For example, if your company has several divisions, you can let the system generate a single closing entry for all the divisions, and you can then make an offsetting entry for each division's equity account.  

Once a year is fiscally closed, you can't post in this fiscal year.  

## Related information

- [Fiscally Close Accounting Periods](how-to-fiscally-close-accounting-periods.md)  
- [Posting the year-end closing entry](how-to-post-the-year-end-closing-entry.md)  
- [Fiscally Close Years](how-to-fiscally-close-years.md)  
- [Fiscal Periods and Fiscal Years](fiscal-periods-and-fiscal-years.md)  
- [Closing Years and Periods](../../year-close-years-periods.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
