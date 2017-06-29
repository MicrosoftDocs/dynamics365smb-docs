---
title: "How to: Close a Fiscal Year"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "fiscal years, closing"
  - "closing, fiscal years"
  - "year-end closing, posting"
  - "year-end closing, entries"
ms.assetid: 9f7fd695-e85c-4e96-8bc2-ad5f87dcb67a
caps.latest.revision: 35
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "it-it"
---
# How to: Close a Fiscal Year
To evaluate profit and loss, a fiscal year closing report is provided at the end of each fiscal year.  
  
 Fiscal year closing involves the following steps:  
  
-   Closing the fiscal year using the **Accounting Period** option.  
  
-   Generating a year\-end closing entry using the **Close Income Statement** option.  
  
-   Posting the year\-end closing entry.  
  
### To close a fiscal year  
  
1.  In the **Search** box, enter **Accounting Periods**, and then choose the related link.  
  
2.  To close an accounting period, select the accounting period, and then, on the **Actions** tab, choose **Close Year**.  
  
3.  To confirm that you want to close the fiscal year, choose the **Yes** button.  
  
    > [!IMPORTANT]  
    >  After the fiscal year is closed it cannot be opened again, and the period in the fiscal year cannot be changed.  
  
### To generate a year\-end closing entry using the Close Income Statement option  
  
1.  In the **Search** box, enter **Close Income Statement**, and then choose the related link.  
  
2.  On the **Options** tab, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
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
  
### To post the year\-end closing entry  
  
1.  In the **Search** box, enter **General Journals**, and then choose the related link.  
  
2.  In the **Batch** field, specify the batch that contains the closing entries.  
  
3.  Add the relevant entries to the journal lines.  
  
4.  To post the journal, on the **Home** tab, in the **Process** group, choose **Post**.  
  
     An entry is posted to each income statement account so that it has a zero balance. The year\-end result is transferred to the balance sheet.  
  
## See Also  
 [About Year\-End Processes](../../Finance/about-year-end-processes.md)   
 [Italy Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/italy-local-functionality.md)