---
author: brentholtorf
ms.topic: include
ms.date: 04/01/2021
ms.author: bholtorf
---
To use automatic account codes, you must create an automatic account posting group.  

## To set up automatic account posting groups  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Automatic Account Groups**, and then choose the related link.  
2. Choose the **New** action.  
3. On the **General** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----------|-----------------|  
    |**No.**|Enter a unique alphanumeric number for the automatic account posting group.|  
    |**Description**|Enter a description for the automatic account posting group.|  

4. On the **Automatic Acc. Line** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |-----------|-----------------|  
    |**Allocation Percentage**|Enter the percentage of the source line amount that is to be allocated.|  
    |**G/L Account No.**|Enter the general ledger account number to which the allocation should be posted.|  

    > [!NOTE]  
    >  The **Total Balance** field totals the **Allocation Percentage** field for automatic account lines in a posting group. If the total allocation percent for a posting group does not balance to zero, an error message will be displayed when the item is posted.  

5. Choose the **OK** button.  
