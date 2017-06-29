---
title: "How to: Finish a Physical Inventory Order"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "physical inventory, finishing orders"
ms.assetid: 2baf024c-a60b-48d9-bc18-23fa5c2cefd9
caps.latest.revision: 8
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Finish a Physical Inventory Order
After you have entered all data for the physical inventory order, you can finish the physical inventory order.  
  
 It is only possible to finish the physical inventory order if the following is true:  
  
-   For all related physical inventory recordings, the Status field is set to **Finished**.  
  
-   In all physical inventory order lines, the quantity expected has been calculated.  
  
     ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> shows this by setting a check mark in the field Qty. Exp. Calculated of the physical inventory order line.  
  
-   Every physical inventory order line has been counted by at least one inventory recording line.  
  
     This is indicated by selecting the In Recording Lines field of the physical inventory order line. For a physical inventory order line, you can view a list of the physical inventory recording lines.  
  
### To finish a physical inventory order  
  
1.  In the **Search** box, enter **Phys. Inventory Order**, and then choose the related link.  
  
2.  Open the physical inventory order that you want to finish.  
  
3.  On the **Home** tab, in the **Functions** group, choose **Finish**.  
  
     The status of the physical inventory header is set to **Finished**. You can no longer change the physical inventory order header or the physical inventory order lines.  
  
 When finishing the physical inventory order, the expected quantity and the recorded quantities of the physical inventory header are compared and the differences calculated.  
  
 You have to finish the physical inventory order header first before you can evaluate differences and before you can post the physical inventory order.  
  
## See Also  
 [How to: Enter Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-enter-physical-inventory-orders.md)   
 [How to: Post Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-post-physical-inventory-orders.md)   
 [How to: Calculate Quantity On Hand for a Physical Inventory Order](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-calculate-quantity-on-hand-for-a-physical-inventory-order.md)   
 [How to: Finish a Physical Inventory Recording](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-finish-a-physical-inventory-recording.md)   
 [How to: Analyze Physical Inventory Differences](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-analyze-physical-inventory-differences.md)   
 [Physical Inventory Order Lines With Item Tracking Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/physical-inventory-order-lines-with-item-tracking-lines.md)