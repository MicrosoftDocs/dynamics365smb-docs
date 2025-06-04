---
title: How to print account book reports [ES]
description: Learn how to print the Official Account Book report and the Official Account Summarize Book report with the Spanish version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 11/22/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Print account book reports in the Spanish version
Account book reports display all the general ledger entries created in a specific period. The two account book reports are:  

- **Official Account Book** report - Displays information for every general ledger entry, grouped by transaction.  
- **Official Account Summarized Book** report - Displays a summary of general entries, grouped by heading or posting accounts.  

When sending these reports to the authorities or auditors, you can include additional pages that precede your report. To do this, you need to manually set the report's first page number. For example, if you have three pages of information preceding your report, you can set the first page of the report to indicate page 4.  

## To print an official account book report  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Account - Official Acc. Book**, and then choose the related link.  
2.  In the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Closing Transaction Description**|Enter the description for the closing period transaction.|  
    |**Opening Transaction Description**|Enter the description for the opening period transaction.|  
    |**First Page**|Enter the number that you want to include on the first page of the report.|  
    |**Show Amounts in Add. Currency**|Select to show the report amounts in additional reporting currency (ACY).|  

3.  In the **GL Register** FastTab, select appropriate filters.  
4.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## To print an official account of a summarized book report  

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Official Acc.Summarized Book**, and then choose the related link.  
2.  In the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**From Date**|Enter the start date of the report.|  
    |**To Date**|Enter the end date of the report.|  
    |**Include Closing Entries**|Select to include the closing entries in the report.|  
    |**Show Amounts in Add. Currency**|Select to show the report amounts in additional reporting currency (ACY).|  
    |**First page**|Enter the number that you want to include on the first page of the report.|  
    |**Account Type**|Select **Posting** or **Heading**. **Posting** implies that entries can be posted to the account, and **Heading** implies that entries can't be posted to the account.|  

3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  

## Related information  
 [Spain Local Functionality](spain-local-functionality.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
