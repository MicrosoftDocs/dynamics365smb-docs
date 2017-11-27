---
    title: How to Print Goods and Service Tax Settlement Reports
    description: You must submit a periodic report of goods and services tax (GST) settlement. You can create this settlement from the **BAS Calc. Schedule List** window.

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
# How to: Print Goods and Service Tax Settlement Reports
You must submit a periodic report of goods and services tax (GST) settlement. You can create this settlement from the **BAS Calc. Schedule List** window.  

> [!IMPORTANT]  
>  Before you calculate the GST settlement, you must export the business activity statement (BAS). For more information, see [How to: Export Business Activity Statements](how-to-export-business-activity-statements.md).  

### To print a goods and service tax settlement  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **BAS Calculation Sheets**, and then choose the related link.  

2.  Choose the appropriate BAS calculation sheet, and then, on the **Actions** tab, choose **Calculate GST Statement**.  

3.  On the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Settlement Account Type**|The settlement account type.|  
    |**Settlement Account No.**|The general ledger account number or vendor number, based on the type selected in the **Settlement Account Type** field.|  
    |**Rounding G/L Account No.**|The account to which the truncated cents will be posted.|  
    |**Posting Date**|The posting date for the settlement entries.|  
    |**Document No.**|The document number of the settlement entries.|  
    |**Description**|The settlement description.|  
    |**Post**|Select to post the withholding tax settlement entries.|  
    |**Inter Company**|Select if the posting is inter company.|  

4.  On the **BAS Calculation Sheet** FastTab, select the appropriate filters.  

5.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## See Also  
 [How to: Print Goods and Services Tax Sales and Purchase Reports](how-to-print-goods-and-services-tax-sales-and-purchase-reports.md)   
 [How to: Set Up Goods and Service Tax Posting](how-to-set-up-goods-and-service-tax-posting.md)   
 [Business Activity Statements](business-activity-statements.md)
