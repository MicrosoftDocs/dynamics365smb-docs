---
title: "How to: Create Multiple Fixed Asset Cards"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "fixed assets, setting up automatic creation of"
  - "fixed assets, creating cards"
ms.assetid: dd883c1b-4c5b-4aa8-be65-5c9c982ae26a
caps.latest.revision: 23
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "it-it"
---
# How to: Create Multiple Fixed Asset Cards
You can create multiple fixed asset cards automatically during purchase invoice posting. For example, if your company purchases 200 computers of the same kind from the same vendor, you do not have to manually create a fixed asset card for each computer; the fixed asset cards can be created automatically.  
  
### To create multiple fixed asset cards  
  
1.  In the **Search** box, enter **Fixed Assets**, and then choose the related link.  
  
2.  Under **Lists**, choose **Fixed Assets**.  
  
3.  In the **Fixed Asset List** window, on the **Home** tab, choose **New**.  
  
4.  In the **Fixed Asset Card** window, fill in the relevant fields.  
  
     You will use the value of the **No.** field when you generate the remaining fixed assets later.  
  
5.  In the **Search** box, enter **Purchase Orders**, and then choose the related link.  
  
6.  Create a new purchase order, or open the existing purchase order.  
  
7.  Expand the **Lines** FastTab.  
  
8.  Fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Type**|Select **Fixed Asset**.|  
    |**No.**|Specify the fixed asset number.<br /><br /> **NOTE:** This should be the same fixed asset number that you entered in the **Fixed Asset** list.|  
    |**No. of Fixed Asset Cards**|Specify the relevant number of duplicates for your fixed asset.<br /><br /> **NOTE:** During invoice posting, duplicate fixed asset cards are automatically generated and added to the fixed asset list. The only difference between the duplicate fixed asset cards is the number assigned to each fixed asset.|  
  
9. Choose the **OK** button.  
  
## See Also  
 [Manage Fixed Assets](../../Finance/manage-fixed-assets.md)   
 [Italian Fixed Assets](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/italian-fixed-assets.md)