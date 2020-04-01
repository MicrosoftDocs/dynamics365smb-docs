---
    title: How to Close a Fiscal Year
    description: To evaluate profit and loss, a fiscal year closing report is provided at the end of each fiscal year.

    services: project-madeira 
    documentationcenter: ''
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
# Close a Fiscal Year
To evaluate profit and loss, a fiscal year closing report is provided at the end of each fiscal year.  

Fiscal year closing involves the following steps:  

- Closing the fiscal year using the **Accounting Period** option.  
- Generating a year-end closing entry using the **Close Income Statement** option.  
- Posting the year-end closing entry.  

## To close a fiscal year  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Accounting Periods**, and then choose the related link.  
2.  To close an accounting period, select the accounting period, and then choose the **Close Year** action.  
3.  To confirm that you want to close the fiscal year, choose the **Yes** button.  

    > [!IMPORTANT]  
    >  After the fiscal year is closed it cannot be opened again, and the period in the fiscal year cannot be changed.  

## To generate a year-end closing entry using the Close Income Statement option  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Close Income Statement**, and then choose the related link.  
2.  On the **Options** tab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Fiscal Year Ending Date**|The ending date for the fiscal year.|  
    |**Gen. Journal Template**|The name of the general journal template in which to place the entries.|  
    |**Gen. Journal Batch**|The name of the general journal batch in which to place the entries.|  
    |**Balancing Account No.**|Select the relevant account number.|  
    |**Document No.**|The batch job automatically populates this field with the next available number for the journal batch if you fill in the **Gen. Journal Template** and **Gen. Journal Batch** fields. You can also enter a number into this field manually.|  
    |**Net Profit Account No.**|Select the unique net profit account number.|  
    |**Net Loss Account No.**|Select the unique net loss account number.|  
    |**Posting Description**|Enter a description. The default text is **Close Income Statement**.|  
    |**Business Unit Code**|Select this check box if you require an entry for each business unit code.|  
    |**Dimensions**|Optionally, select the field to select the dimension codes if you require an entry for each dimension used in the general ledger account.|  
    |**Inventory Period Closed**|This field indicates that the inventory periods with ending dates greater than or equal to the last date of the accounting period are closed.|  

3.  Choose the **OK**  button to create the journal entries.  

## To post the year-end closing entry  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journals**, and then choose the related link.  
2.  In the **Batch** field, specify the batch that contains the closing entries.  
3.  Add the relevant entries to the journal lines.  
4.  To post the journal, choose the **Post** action.  

An entry is posted to each income statement account so that it has a zero balance. The year-end result is transferred to the balance sheet.  

## See Also  
 [Closing Years and Periods](../../year-close-years-periods.md)   
 [Italy Local Functionality](italy-local-functionality.md)
