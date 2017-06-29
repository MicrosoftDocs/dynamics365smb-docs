---
title: "How to: Account for the Cost to Dispose a Fixed Asset"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "fixed assets, accounting for disposal costs"
ms.assetid: 20cf9d52-09d6-46ed-bab2-9212a458b0c7
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Account for the Cost to Dispose a Fixed Asset
The maintenance on disposal feature allows you to account for the amount spent to dispose a fixed asset \(FA\) as an expense. You can post operations related to spending for the disposal of a fixed asset so that they will be reflected in the FA Write\-Off Act forms.  
  
 Fixed asset expenses can be posted from general ledger journals, fixed asset journals, and purchase documents. This procedure shows how to post the expenses on a fixed asset disposal by using a general ledger journal.  
  
 The expenses on a fixed asset disposal are printed on the FA Write\-Off FA\-4 Report, and the FA Write\-Off FA\-4A report. This procedure shows how to print the Fixed Assets Write\-Off Fixed Assets\-4 report for the expenses on a fixed asset disposal.  
  
### To set up a maintenance code  
  
1.  In the **Search** box, enter **FA Setup**, and then choose the related link.  
  
2.  On the **General** FastTab of the **Fixed Asset Setup** window, fill in the **On Disposal Maintenance Code** field. If the maintenance code does not exist, you must create it in the **Maintenance** window.  
  
3.  Choose the **OK** button.  
  
### To post expenses on a fixed asset disposal  
  
1.  In the **Search** box, enter **FA G\/L Journals**, and then choose the related link.  
  
2.  In the **Fixed Asset G\/L Journal** window, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Account Type**|Select **Fixed Asset** as the account type.|  
    |**Account No.**|Specifies the number of the fixed asset for disposal for which expenses are made.|  
    |**FA Posting Type**|Select **Maintenance** as the fixed asset posting type.|  
    |**Maintenance Code**|Specifies the maintenance code that was specified in the **On Disposal Maintenance Code** field of the **Fixed Asset Setup** window.|  
  
3.  Choose the **OK** button.  
  
### To print a report with expenses on a fixed asset disposal  
  
1.  In the **Search** box, enter **FA Writeoffs**, and then choose the related link.  
  
2.  In the **FA Writeoff Act** window, enter the expenses that are posted for the fixed asset.  
  
3.  Choose the **OK** button.  
  
4.  In the **Search** box, enter **Assessed Tax Codes**, and then choose the related link.  
  
5.  On the **Home** tab, in the **Process** group, choose **Print**.  
  
     If the expenses on the disposal are made in advance, they are displayed on the second page of the report.  
  
     After the fixed asset write\-off report is posted, it becomes the posted fixed asset write\-off report. You can print the Fixed Assets Write\-Off Fixed Asset\-4A report in the Posted FA Reports window.  
  
## See Also  
 Fixed Asset Setup   
 [Fixed Assets Accounting Setup](../../Finance/fixed-assets-accounting-setup.md)   
 Fixed Asset Card   
 Calculate Assessed Tax   
 Assessed Tax Code