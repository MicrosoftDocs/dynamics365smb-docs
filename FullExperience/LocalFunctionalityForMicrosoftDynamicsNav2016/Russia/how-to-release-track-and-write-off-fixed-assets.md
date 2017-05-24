---
title: "How to: Release, Track, and Write-Off Fixed Assets"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "fixed assets, writing off"
  - "write-offs, fixed assets"
ms.assetid: 3b44b96b-ed23-4ffe-a9f4-b025486caeaf
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# How to: Release, Track, and Write-Off Fixed Assets
You can manage your fixed assets utilizing the fixed assets acts features in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]. Fixed assets acts allow you to release, track, and write\-off the fixed assets of your organization.  
  
 The first step to managing your fixed assets is to set up fixed assets numbering and source codes.  
  
### To set up fixed asset numbering  
  
1.  In the **Search** box, enter **\($ N\_5607 Fixed Asset Setup $\)**, and then choose the related link.  
  
2.  On the **Numbering** FastTab, select a numbering series for each type of fixed asset transaction.  
  
3.  Choose the **OK** button to close the window and save your entries.  
  
### To set up fixed asset source codes  
  
1.  In the **Search** box, enter **\($ N\_279 Source Code Setup $\)**, and then choose the related link.  
  
2.  On the **Fixed Assets** FastTab, select a source code for each type of fixed asset.  
  
3.  Choose the **OK** button to close the window and save your entries.  
  
## Releasing Fixed Assets into Service  
 An asset is recognized as a fixed asset after it is released into service for the organization. You can use the **\($ N\_12474 FA Release Act $\)** window to release fixed assets into service.  
  
#### To release fixed assets into service  
  
1.  In the **Search** box, enter **\($ N\_12474 FA Release Act $\)**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12470\_2 No. $\)**|Enter the identification number that is assigned to the fixed asset release.|  
    |**\($ T\_12470\_3 Posting Description $\)**|Enter a description for the fixed asset release. A description is automatically created from the document type and release number.|  
    |**\($ T\_12470\_22 Reason Document No. $\)**|Enter the identification number of the source document that is the reason for the fixed asset release.|  
    |**\($ T\_12470\_23 Reason Document Date $\)**|Enter the date of the source document that is the reason for the fixed asset release. This information is used in fixed asset reports and entries.|  
    |**\($ T\_12470\_6 FA Posting Date $\)**|Enter the date on which the fixed asset release is posted. This information is used in fixed asset reports and entries.|  
    |**\($ T\_12470\_16 External Document No. $\)**|Enter the number of the external document that relates to this fixed asset release.|  
    |**\($ T\_12470\_20 Posting No. $\)**|Enter an identifying posting number to use for the fixed asset release entry.|  
    |**\($ T\_12470\_8 Shortcut Dimension 1 Code $\)**|Enter the department code that is associated with the fixed asset.|  
    |**\($ T\_12470\_9 Shortcut Dimension 2 Code $\)**|Enter the incexp code that is associated with the fixed asset.|  
  
3.  On the **Lines** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12477\_4 FA No. $\)**|Enter the identification number that is assigned to the fixed asset to be released.|  
    |**\($ T\_12477\_13 Description $\)**|Enter a description for the fixed asset.|  
    |**\($ T\_12477\_8 Depreciation Book Code $\)**|Enter the code for the depreciation book that is used to post depreciation for the fixed asset. The value is set using information from the **\($ N\_5607 Fixed Asset Setup $\)** window.|  
    |**\($ T\_12477\_46 New Depreciation Book Code $\)**|Enter an alternative depreciation book code that is used to post depreciation for the released fixed asset entry.|  
  
4.  Choose the **OK** button to post your entries and release the fixed assets into service.  
  
## Tracking the Movement of Fixed Assets  
 Tracking the location and status of fixed assets is an important function within most organizations. For example, you may want to record the movement of office equipment from a previous location to a new location. You can use the **\($ N\_12478 FA Movement Act $\)** window to track the movement of fixed assets and record the status of your fixed assets.  
  
#### To track the movement of fixed assets  
  
1.  In the **Search** box, enter **\($ N\_12478 FA Movement Act $\)**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12470\_2 No. $\)**|Enter an identification number that is assigned to the fixed asset movement entry.|  
    |**\($ T\_12470\_3 Posting Description $\)**|Enter a description for the fixed asset movement entry. A description is automatically created from the document type and movement number.|  
    |**\($ T\_12470\_22 Reason Document No. $\)**|Enter the identification number of the source document that is the reason for the fixed asset movement.|  
    |**\($ T\_12470\_23 Reason Document Date $\)**|Enter the date of the source document that is the reason for the fixed asset movement. This information is used in fixed asset reports and entries.|  
    |**\($ T\_12470\_24 FA Location Code $\)**|Specifies the location of the fixed asset before it being moved.|  
    |**\($ T\_12470\_25 New FA Location Code $\)**|Enter the new location for the fixed asset.|  
    |**\($ T\_12470\_6 FA Posting Date $\)**|Enter the date on which the fixed asset movement entry is posted. This information is used in fixed asset reports and entries.|  
    |**\($ T\_12470\_16 External Document No. $\)**|Enter the number of the external document that relates to this fixed asset movement entry.|  
    |**\($ T\_12470\_20 Posting No. $\)**|Enter an identifying posting number to use for the fixed asset movement entry.|  
    |**\($ T\_12470\_8 Shortcut Dimension 1 Code $\)**|Enter the department code that is associated with the fixed asset.|  
    |**\($ T\_12470\_9 Shortcut Dimension 2 Code $\)**|Enter the incexp code that is associated with the fixed asset.|  
  
3.  On the **Lines** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12477\_4 FA No. $\)**|Enter an identification number that is assigned to the fixed asset movement line entry.|  
    |**\($ T\_12477\_13 Description $\)**|Enter a description for the fixed asset movement line entry.|  
    |**\($ T\_12477\_30 Status $\)**|Enter the status of the fixed asset. The options include **Inventory**, **Montage**, **Operation**, **Maintenance**, **Repair**, **Disposed**, and **Written Off**.|  
    |**\($ T\_12477\_8 Depreciation Book Code $\)**|Enter the code for the depreciation book that is used to post depreciation for the fixed asset. The value is set using information from the **\($ N\_5607 Fixed Asset Setup $\)** window.|  
    |**\($ T\_12477\_46 New Depreciation Book Code $\)**|Enter a new depreciation book code that is used to post depreciation after the fixed asset movement entry is posted.|  
    |**\($ T\_12477\_36 Reason Code $\)**|Enter a reason code fixed asset movement entry.|  
  
4.  Choose the **OK** button to post your entries and record the movement of the fixed asset.  
  
## Writing Off the Value of a Fixed Asset  
 During the sale or disposal of a fixed asset, you may want to write\-off the remaining book value of the asset that has not been depreciated. You can use the **\($ N\_12470 FA Writeoff Act $\)** window to write\-off the remaining value of a fixed assets.  
  
#### To write\-off the value of a fixed asset  
  
1.  In the **Search** box, enter **\($ N\_12470 FA Writeoff Act $\)**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12470\_2 No. $\)**|Enter an identification number that is assigned to the fixed asset write\-off entry.|  
    |**\($ T\_12470\_3 Posting Description $\)**|Enter a description for the fixed asset write\-off entry. A description is automatically created from the document type and write\-off number.|  
    |**\($ T\_12470\_22 Reason Document No. $\)**|Enter the identification number of the source document that is the reason for the fixed asset write\-off.|  
    |**\($ T\_12470\_23 Reason Document Date $\)**|Enter the date of the source document that is the reason for the fixed asset write\-off. This information is used in fixed asset reports and entries.|  
    |**\($ T\_12470\_24 FA Location Code $\)**|Specifies the location of the fixed asset.|  
    |**\($ T\_12470\_26 FA Employee No. $\)**|Enter the employee number of the person who maintains possession of the fixed asset.|  
    |**\($ T\_12470\_6 FA Posting Date $\)**|Enter the date on which the fixed asset write\-off entry is posted. This information is used in fixed asset reports and entries.|  
    |**\($ T\_12470\_16 External Document No. $\)**|Enter the number of the external document that relates to this fixed asset write\-off entry.|  
    |**\($ T\_12470\_20 Posting No. $\)**|Enter an identifying posting number to use for the fixed asset write\-off entry.|  
    |**\($ T\_12470\_8 Shortcut Dimension 1 Code $\)**|Enter the department code that is associated with the fixed asset.|  
    |**\($ T\_12470\_9 Shortcut Dimension 2 Code $\)**|Enter the incexp code that is associated with the fixed asset.|  
  
3.  On the **Lines** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12477\_4 FA No. $\)**|Enter an identification number that is assigned to the fixed asset write\-off line entry.|  
    |**\($ T\_12477\_13 Description $\)**|Enter a description for the fixed asset write\-off line entry.|  
    |**\($ T\_12477\_8 Depreciation Book Code $\)**|Enter the code for the depreciation book that is used to post depreciation for the fixed asset. The value is set using information from the **\($ N\_5607 Fixed Asset Setup $\)** window.|  
    |**\($ T\_12477\_50 Item Receipt No. $\)**|Enter the receipt number from the item sale or disposal document.|  
    |**\($ T\_12477\_36 Reason Code $\)**|Enter a reason code for the fixed asset write\-off entry.|  
  
4.  Choose the **OK** button  to post your entries and record the write\-off of the fixed asset.  
  
## See Also  
 [How to: Create Fixed Assets](../../Finance/how-to-create-fixed-assets.md)   
 [\($ N\_5600 Fixed Asset Card $\)](../Topic/\($%20N_5600%20Fixed%20Asset%20Card%20$\).md)   
 [\($ N\_5601 Fixed Asset List $\)](../Topic/\($%20N_5601%20Fixed%20Asset%20List%20$\).md)   
 [\($ T\_5612 FA Depreciation Book $\)](../Topic/\($%20T_5612%20FA%20Depreciation%20Book%20$\).md)