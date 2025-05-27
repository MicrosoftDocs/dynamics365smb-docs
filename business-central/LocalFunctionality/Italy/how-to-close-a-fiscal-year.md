---
title: How to Close a Fiscal Year
description: Learn to close a fiscal year, create a closing entry with the Close Income Statement option, and post it.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: close fiscal year, create closing entry, close income statement option, post closing entry, Italian version
ms.date: 05/20/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Close a fiscal year

To evaluate profit and loss, a fiscal year closing report is provided at the end of each fiscal year.  

Fiscal year closing involves the following steps:  

- Closing the fiscal year using the **Accounting Period** option.  
- Generating a year-end closing entry using the **Close Income Statement** option.  
- Posting the year-end closing entry.  

## Steps to close a fiscal year

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Accounting Periods**, and then choose the related link.  
1. To close an accounting period, select the accounting period, and then choose the **Close Year** action.  
1. To confirm that you want to close the fiscal year, choose the **Yes** button.  

    > [!IMPORTANT]  
    > After the fiscal year is closed it can't be opened again, and the period in the fiscal year can't be changed.  

## Generate a year-end closing entry using the Close Income Statement option  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Close Income Statement**, and then choose the related link.  
1. On the **Options** tab, fill in the fields as described in the following table.  

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
    |**Business Unit Code**|Select this checkbox if you require an entry for each business unit code.|  
    |**Dimensions**|Optionally, select the field to select the dimension codes if you require an entry for each dimension used in the general ledger account.|  
    |**Inventory Period Closed**|This field indicates that the inventory periods with ending dates greater than or equal to the last date of the accounting period are closed.|  

1. Choose the **OK**  button to create the journal entries.  

## Post the year-end closing entry  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link.  
1. In the **Batch** field, specify the batch that contains the closing entries.  
1. Add the relevant entries to the journal lines.  
1. To post the journal, choose the **Post** action.  

An entry is posted to each income statement account so that it has a zero balance. The year-end result is transferred to the balance sheet.  

## Related information

- [Closing Years and Periods](../../year-close-years-periods.md)
- [Italy Local Functionality](italy-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
