---
    title: How to Limit the Posting Period
    description: You can limit the period by which posting is permitted on three different levels, by company, by user, and by template.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Limit the Posting Period
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can limit the period by which posting is permitted on three different levels: **by company**, **by user**, and **by template**.  

Limiting posting periods can be useful when a company closes its sales journal at the end of each month. This keeps salespeople from registering sales documents from the previous month. At the same time, the purchase journal may stay open to register incoming purchase invoices from the previous month.  

When you post on the **General Journal Templates** page, the contents of the **Allow Posting From** field and **Allow Posting To** field are checked for a date interval. The date interval indicates when you can post to a journal template. If the field is blank, the **User Setup** page is checked for a date interval for the current user. If the **User Setup** page does not contain an interval, the **Allow Posting From** field and the **Allow Posting To** field on the **General Ledger Setup** page is checked for a date interval at the company level.  

## To limit the posting periods by company  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Setup**, and then choose the related link.  
2.  To specify the start of the period, choose the **Allow Posting From** field, and then enter the earliest date on which posting to the company is enabled.  
3.  To specify the end of the period, choose the **Allow Posting To** field, and then enter the last date on which posting to the company is enabled.  

## To limit the posting periods by user  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Setup**, and then choose the related link.  
2.  To specify the start of the period, choose the **Allow Posting From** field, and then enter the earliest date on which the user can post to the company.  
3.  To specify the end of the period, choose the **Allow Posting To** field, and then enter the last date the user will be able to post to the company.  

## To limit the posting periods by template  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journal Templates**, and then choose the related link.  
2.  To specify the start of the period, choose the **Allow Posting From** field, and then enter the earliest date on which the user can post to the company.  
3.  To specify the end of the period, choose the **Allow Posting To** field, and then enter the last date the user will be able to post to the company.  

## See Also  
 [Belgium Local Functionality](belgium-local-functionality.md)   
 [Specify Posting Periods](../../finance-how-specify-posting-periods.md)
