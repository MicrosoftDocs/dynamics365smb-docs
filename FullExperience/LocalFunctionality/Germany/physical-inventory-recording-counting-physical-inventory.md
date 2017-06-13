---
title: "Physical Inventory Recording - Counting Physical Inventory"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "physical inventory, counting"
  - "inventory, counting"
ms.assetid: 4f30b803-4746-42ae-9202-3b9937683d45
caps.latest.revision: 5
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# Physical Inventory Recording - Counting Physical Inventory
After you have created a physical inventory order and after you have entered the physical inventory order lines, you can take the physical inventory. Therefore you can use the physical inventory recording documents.  
  
 A physical inventory recording is related to only one physical inventory order. A physical inventory order may have relations to more than one physical inventory recordings.  
  
 A physical inventory recoding consists of a physical inventory recording header and a number of physical inventory recording lines. The physical inventory recording header contains the information, that are common for all physical inventory recording lines.  
  
 This lines contain the items, locations, bins and the recorded quantities.  
  
 You can create lines manually or you can have the program to create new physical inventory recordings automatically. You can print physical inventory recording lists.  
  
 By setting the [Status](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005352_11-status-$-.md) to finished, you tell the program, that the current physical inventory recording has been finished.  
  
> [!NOTE]  
>  When you finish the current physical inventory recording, the program assigns every physical inventory recording line to one line of the related physical inventory order. The program assigns this physical inventory order lines with the same values in the 4 fields [Item No.](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_20-item-no.-$-.md), [Variant Code](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_21-variant-code-$-.md), [Location Code](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_22-location-code-$-.md) and [Bin Code](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_23-bin-code-$-.md) like in the physical inventory recording line.  
>   
>  If there is no such physical inventory order line the program will automatically insert a new line when finishing the physical inventory recording. The program will note this by placing a check mark in the field [Recorded without Order](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_80-recorded-without-order-$-.md) on the physical inventory order line.  
>   
>  If there are more than one such physical inventory order lines, an error message appears. You can have the program to show you the duplicate lines.  
  
## See Also  
 [How to: Create a Physical Inventory Recording](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-create-a-physical-inventory-recording.md)   
 [How to: Finish a Physical Inventory Recording](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-finish-a-physical-inventory-recording.md)   
 [How to: View Duplicate Physical Inventory Order Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-view-duplicate-physical-inventory-order-lines.md)   
 [Physical Inventory Order Lines With Item Tracking Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/physical-inventory-order-lines-with-item-tracking-lines.md)