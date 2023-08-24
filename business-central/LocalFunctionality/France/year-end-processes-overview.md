---
    title: Year End Processes Overview [FR]
    description: This is an overview of the processes involved in the fiscal year end closing entry in Business Central.

    author: brentholtorf
    ms.topic: overview
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/18/2021
    ms.author: bholtorf

---
# Year End Processes Overview in the French Version

Year end closing in [!INCLUDE[prod_short](../../includes/prod_short.md)] involves three steps:  

1. Closing the fiscal year. For more information, see [Fiscally Close Accounting Periods](how-to-fiscally-close-accounting-periods.md).  
2. Generating a year-end closing entry using the **Close Income Statement** option along with the offsetting equity account entries. For more information, see [Posting the year-end closing entry](how-to-post-the-year-end-closing-entry.md).  
3. Fiscally closing the fiscal year. For more information, see [Fiscally Close Years](how-to-fiscally-close-years.md).  

According to the French law *NF Logiciel compatibilité informatisée* the system has to refuse the creation of a third open fiscal year, so only two open fiscal years are allowed at the same time.  

So in time you are required to close a year. You also do not have to worry about losing details of transactions when you close because all details are retained, even after you (fiscally) close the year.  

When you close at the end of the year, the system moves your earnings from calculated earnings, or the Current Earnings account, to a posted account, or the Retained Earnings account. The system also marks the fiscal year as "closed," and marks all subsequent entries for the closed year as "prior year entries."  

The system then generates a closing entry, but it does not post the entry automatically. You are given the opportunity to make the offsetting equity account entry or entries, which allows you to decide how to allocate your closing entry. For example, if your company has several divisions, you can let the system generate a single closing entry for all the divisions, and you can then make an offsetting entry for each division's equity account.  

Once a year has been fiscally closed you will not be able to post in this fiscal year.  

## See Also

[Fiscally Close Accounting Periods](how-to-fiscally-close-accounting-periods.md)  
[Posting the year-end closing entry](how-to-post-the-year-end-closing-entry.md)  
[Fiscally Close Years](how-to-fiscally-close-years.md)  
[Fiscal Periods and Fiscal Years](fiscal-periods-and-fiscal-years.md)  
[Closing Years and Periods](../../year-close-years-periods.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]