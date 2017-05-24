---
title: "How to: Calculate Quantity On Hand for a Physical Inventory Order"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "physical inventory, quantity on hand"
  - "calculating, quantity on hand"
ms.assetid: c67a5b30-134a-45fd-ab70-c762b38f3bd3
caps.latest.revision: 8
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Calculate Quantity On Hand for a Physical Inventory Order
After you have created the physical inventory order and after you have entered the physical inventory order lines, you must have the program calculate the field [\($ T\_5005351\_50 Qty. Expected \(Base\) $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_50-qty.-expected-base-$-.md) for every physical inventory order line.  
  
 If [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] created this physical inventory order lines automatically, you could decide in the request page for the batch job whether to calculate the expected quantity or not. If you have created the physical inventory order lines manually or if you changed them in the meantime, you have to calculate the expected quantities manually. You can calculate quantities in two ways as described in the following section.  
  
### To calculate the expected quantity on the physical inventory order  
  
1.  In the **Search** box, enter **\($ N\_5005350 Phys. Inventory Order $\)**, and then choose the related link.  
  
2.  Open the physical inventory order that you want to calculate the expected quantity for.  
  
3.  To calculate the expected quantity of only one physical inventory order line, on the **Actions** tab, in the **Functions** group, choose **Calculate Qty. Expected**, and then choose **This Line**.  
  
4.  To calculate the expected quantity in all physical inventory order lines, on the **Actions** tab, in the **Functions** group, choose **Calculate Qty. Expected**, and then choose **All Lines**.  
  
     In the dialog that appears, choose to calculate the quantities for all lines or for those lines that have not yet been calculated.  
  
 If [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] has already calculated the expected quantity, it shows this by placing a check mark in the [\($ T\_5005351\_51 Qty. Exp. Calculated $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_51-qty.-exp.-calculated-$-.md) field in the inventory order line.  
  
> [!NOTE]  
>  The process of taking the inventory and recording it in the physical inventory recording is independent from the calculation of the expected quantities.  
  
 You must calculate the expected quantities for all physical inventory order lines of a physical inventory order before you can set the [\($ T\_5005350\_11 Status $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005350_11-status-$-.md) field to **Finished**. This is because [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] compares the expected and the recorded quantities and calculates the differences for posting.  
  
## See Also  
 [How to: Enter Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-enter-physical-inventory-orders.md)   
 [Physical Inventory Recording \- Counting Physical Inventory](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/physical-inventory-recording-counting-physical-inventory.md)   
 [How to: Finish a Physical Inventory Order](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-finish-a-physical-inventory-order.md)   
 [How to: Finish a Physical Inventory Recording](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-finish-a-physical-inventory-recording.md)   
 [Physical Inventory Order Lines With Item Tracking Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/physical-inventory-order-lines-with-item-tracking-lines.md)