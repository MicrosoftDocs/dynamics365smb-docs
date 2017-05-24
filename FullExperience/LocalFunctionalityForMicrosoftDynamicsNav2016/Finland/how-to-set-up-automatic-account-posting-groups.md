---
title: "How to: Set Up Automatic Account Posting Groups"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "automatic account codes, setting up"
  - "account codes, setting up automation"
ms.assetid: 91c3d134-cf33-47ca-b2b3-e469e9d74e59
caps.latest.revision: 15
ms.author: "edupont"
manager: "pchapman"
translation.priority.ht: 
  - "fi-fi"
  - "sv-se"
---
# How to: Set Up Automatic Account Posting Groups
To use automatic account codes, you must create an automatic account posting group.  
  
### To set up automatic account posting groups  
  
1.  In the **Search** box, enter **Auto. Acc. Groups**, and then choose the related link.  
  
2.  On the **Actions** tab, choose **New**.  
  
3.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |-----------|-----------------|  
    |**No.**|Enter a unique alphanumeric number for the automatic account posting group.|  
    |**Description**|Enter a description for the automatic account posting group.|  
  
4.  On the **Automatic Acc. Line** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |-----------|-----------------|  
    |**\($ T\_11204\_4 Allocation Percentage  $\)**|Enter the percentage of the source line amount that is to be allocated.|  
    |**\($ T\_11204\_3 G\/L Account No. $\)**|Enter the general ledger account number to which the allocation should be posted.|  
  
    > [!NOTE]  
    >  The **Total Balance** field totals the **\($ T\_11204\_4 Allocation Percentage  $\)** field for automatic account lines in a posting group. If the total allocation percent for a posting group does not balance to zero, an error message will be displayed when the item is posted.  
  
5.  Click **OK**.  
  
## See Also  
 [Automatic Account Codes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/automatic-account-codes.md)   
 [OBSOLETE: Accrual Accounting](../Topic/OBSOLETE:%20Accrual%20Accounting.md)   
 [OBSOLETE: How to: Set Up Accrual Accounting](../Topic/OBSOLETE:%20How%20to:%20Set%20Up%20Accrual%20Accounting.md)   
 [\($ T\_11204\_4 Allocation Percentage $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/-$-t_11204_4-allocation-percentage-$-.md)   
 [\($ T\_11204\_3 G\-L Account No. $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Finland/-$-t_11204_3-g-l-account-no.-$-.md)   
 [Total Balance](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Sweden/total-balance.md)   
 [About Posting Groups](../../Finance/about-posting-groups.md)   
 [How to: Fill and Post General Journals](../../Finance/how-to-fill-and-post-general-journals.md)   
 [How to: Set Up Dimensions and Dimension Values](../../Finance/how-to-set-up-dimensions-and-dimension-values.md)