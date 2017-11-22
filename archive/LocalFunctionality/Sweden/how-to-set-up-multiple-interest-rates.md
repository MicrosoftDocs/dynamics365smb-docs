---
    title: How to Set Up Multiple Interest Rates
    description: You can calculate finance charges with multiple interest rates for a specific period. The interest calculation is similar for all financial charges, with variation only in the rate of interest for a specific period.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Set Up Multiple Interest Rates
You can calculate finance charges with multiple interest rates for a specific period. The interest calculation is similar for all financial charges, with variation only in the rate of interest for a specific period.  

For example, you can charge customers accordingly if they pay late.  

## To set up multiple interest rates  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Finance Charge Terms**, and then choose the related link.    
2.  In the **Finance Charge Terms** window, select the required finance term, and then choose the **Interest Rates** action.  
3.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Start Date**|Enter the start date for each finance charge interest rate code.|  
    |**Interest Rate**|Enter the percentage that must be used to calculate interest.|  
    |**Interest Period (Days)**|Enter the period for each finance charge interest rate.|  

4.  Choose the **OK** button.  
5.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Reminder Terms**, and then choose the related link.  
6.  In the **Reminder Terms** window, select the required reminder term, and then choose the **Levels** action.  
7.  In the **Reminder Levels** window, select the **Calculate Interest** field.  

When you issue a finance charge memo, the memo shows the finance charges with multiple interest rates for a specific time period. The memo also contains the contact details of the customer, the company issuing the memo, the additional amount, and the total amount. The opening entry on the memo is displayed in bold. The finance charges are calculated with multiple interest rates for a specific time period and are printed after the opening entry of the memo.  

## See Also  
 [How to: Collect Outstanding Balances](../../receivables-collect-outstanding-balances.md)
