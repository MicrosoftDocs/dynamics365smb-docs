---
title: "How to: Account for the Cost  to Dispose a Fixed Asset"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "fixed assets, accounting for disposal costs"
ms.assetid: 40bbcd3a-a19a-44cc-9bf3-a36415cd6981
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Account for the Cost  to Dispose a Fixed Asset
The maintenance on disposal feature enables you to account for the amount spent to dispose a fixed asset \(FA\) as an expense. You can post operations related to spending for the disposal of a fixed asset so that they will be reflected in the FA Write\-Off Act forms.  
  
 The expenses of a fixed asset disposal can be posted from general ledger journals, fixed asset journals, and purchase documents. The following procedure shows how to post the expenses for a fixed asset disposal by using the Fixed Asset General Ledger Journal.  
  
 The expenses on a fixed asset disposal can be printed in the [FA Write\-off Act FA\-4](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-r_12493-fa-write-off-act-fa-4-$-.md) report and the [FA Writeoff Act FA\-4a](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-r_14990-fa-writeoff-act-fa-4a-$-.md) report.  
  
### To set up a maintenance code  
  
1.  In the **Search** box, enter **FA Setup**, and then choose the related link.  
  
2.  In the **Fixed Asset Setup** window, on the **General** FastTab, enter a maintenance code in the **On Disposal Maintenance Code** field.  
  
3.  Choose the **OK** button.  
  
### To post expenses on a fixed asset disposal  
  
1.  In the **Search** box, enter **FA G\/L Journals**, and then choose the related link.  
  
2.  In the **Fixed Asset G\/L Journal** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Account Type**|Select **Fixed Asset** as the account type.|  
    |**Account No.**|Specifies the number of the fixed asset for disposal for which the expenses are made.|  
    |**FA Posting Type**|Select **Maintenance** as the fixed asset posting type.|  
    |**Maintenance Code**|Specifies the maintenance code that is entered in the **On Disposal Maintenance Code** field of the **Fixed Asset Setup** window.|  
  
3.  Choose the **OK** button.  
  
### To print a report with expenses on a fixed asset disposal  
  
1.  In the **Search** box, enter **FA Writeoff Act**, and then choose the related link.  
  
2.  In the **FA Writeoff Act** window, enter the expenses that are posted for the fixed asset.  
  
3.  Choose the **Print** button to print the report or choose the **Preview** button to view it on the screen. Choose the **Cancel** button to save the information without printing the report.  
  
    > [!NOTE]  
    >  If the expenses on the disposal of the fixed asset are made in advance, they are displayed on the second page of the report.  
  
     After the fixed asset write\-off report is posted, it becomes the posted fixed asset write\-off report.  
  
## See Also  
 [Fixed Asset Setup](../Topic/\($%20N_5607%20Fixed%20Asset%20Setup%20$\).md)   
 [Fixed Assets Accounting Setup](../../Finance/fixed-assets-accounting-setup.md)   
 [Fixed Asset Card](../Topic/\($%20N_5600%20Fixed%20Asset%20Card%20$\).md)