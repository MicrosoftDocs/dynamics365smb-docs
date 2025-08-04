---
title: Fiscal Periods and Fiscal Years (FR)
description: A fiscal year usually consists of 12 monthly periods. In the French version of Business Central, you can have two open fiscal years simultaneously.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: fiscal period, fiscal years, open fiscal years, accounting period, close years, French version
ms.date: 04/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Fiscal periods and fiscal years in the French version

A fiscal year is typically divided into 12 monthly fiscal periods. In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can have two fiscal years open at the same time. You can't create a third fiscal year if there are two fiscal years open.  

To close a fiscal year, you must close the accounting periods within that year.  

You can only reopen a closed accounting period if the period falls within an open fiscal year. Learn more in [Close Years](how-to-close-years.md). You can't reopen a closed fiscal year.  

## Close fiscal periods and fiscal years

After a fiscal year is complete, you must close the accounting periods within that fiscal year. This is to ensure that general ledger entries aren't posted for that period. Learn more in [Fiscally Close Accounting Periods](how-to-fiscally-close-years.md).  

A fiscal year can be closed if all of the following criteria are met:  

- The posting dates on the **User Setup** page and the **General Ledger Setup** page don't fall within the year that you're closing. Learn more in [Specify Posting Periods](../../finance-how-specify-posting-periods.md) and [Understanding the General Ledger and the COA](../../finance-general-ledger.md).  

- The fiscal year is closed using the **Close Year** function on the **Accounting Periods** page. Learn more in [Closing Years and Periods](../../year-close-years-periods.md).  

- All the unposted journal lines for the year are posted or deleted.  

- All closing entries are up to date.  

When you close a fiscal period, the earliest open fiscal period is closed. The **Allow Posting From** field on the **General Ledger Setup** page is updated with the start date for the next open period, if the existing date in this field isn't already a later date. If the **Allow Posting To** field on the **General Ledger Setup** page is within the closed period, then the value in the **Allow Posting To** field is updated with the end date for the first open fiscal period. Learn more in [Understanding the General Ledger and the COA](../../finance-general-ledger.md).  

At the end of the year, you must do the following actions:  

- Close the fiscal year using the **Close Year** function.  
- Generate a year-end closing entry.  
- Post the year-end closing entry, along with the offset equity account entries.  
- Close the fiscal year using the **Fiscally Close Year** function.  

## Related information

- [Post the Year-End Closing Entry](how-to-post-the-year-end-closing-entry.md)  
- [Fiscally Close Accounting Periods](how-to-fiscally-close-accounting-periods.md)  
- [Closing Years and Periods](../../year-close-years-periods.md)  
- [Post the Year-End Closing Entry](how-to-post-the-year-end-closing-entry.md)  
- [Fiscally Close Years](how-to-fiscally-close-years.md)  
- [Reopen Accounting Periods](how-to-reopen-accounting-periods.md)  
- [Close Income Statement Accounts](how-to-close-income-statement-accounts.md)  
- [Specify Posting Periods](../../finance-how-specify-posting-periods.md)  
- [Understanding the General Ledger and the COA](../../finance-general-ledger.md)  
- [France Local Functionality](france-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
