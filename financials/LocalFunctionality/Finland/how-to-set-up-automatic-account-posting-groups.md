---
    title: How to Set Up Automatic Account Posting Groups | Microsoft Docs
    description: To use automatic account codes, you must create an automatic account posting group.
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
# How to: Set Up Automatic Account Posting Groups
To use automatic account codes, you must create an automatic account posting group.  
  
### To set up automatic account posting groups  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Auto. Acc. Groups**, and then choose the related link.  
  
2.  On the **Actions** tab, choose **New**.  
  
3.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |-----------|-----------------|  
    |**No.**|Enter a unique alphanumeric number for the automatic account posting group.|  
    |**Description**|Enter a description for the automatic account posting group.|  
  
4.  On the **Automatic Acc. Line** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |-----------|-----------------|  
    |**Allocation Percentage**|Enter the percentage of the source line amount that is to be allocated.|  
    |**G/L Account No.**|Enter the general ledger account number to which the allocation should be posted.|  
  
    > [!NOTE]  
    >  The **Total Balance** field totals the **Allocation Percentage** field for automatic account lines in a posting group. If the total allocation percent for a posting group does not balance to zero, an error message will be displayed when the item is posted.  
  
5.  Click **OK**.  
  
## See Also  
 [Automatic Account Codes](automatic-account-codes.md)   
 [OBSOLETE: Accrual Accounting](OBSOLETE:%20Accrual%20Accounting.md)   
 [OBSOLETE: How to: Set Up Accrual Accounting](OBSOLETE:%20How%20to:%20Set%20Up%20Accrual%20Accounting.md)   
 Allocation Percentage   
 G-L Account No.   
 [Total Balance](../Sweden/total-balance.md)   
 [About Posting Groups](about-posting-groups.md)   
 [How to: Fill and Post General Journals](../../../archive/WorkingWithDynamics/how-to-fill-and-post-general-journals.md)   
 [How to: Set Up Dimensions and Dimension Values](how-to-set-up-dimensions-and-dimension-values.md)