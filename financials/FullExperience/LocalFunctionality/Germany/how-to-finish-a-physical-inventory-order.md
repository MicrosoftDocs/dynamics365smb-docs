---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# How to: Finish a Physical Inventory Order
After you have entered all data for the physical inventory order, you can finish the physical inventory order.  
  
 It is only possible to finish the physical inventory order if the following is true:  
  
-   For all related physical inventory recordings, the Status field is set to **Finished**.  
  
-   In all physical inventory order lines, the quantity expected has been calculated.  
  
     ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> shows this by setting a check mark in the field Qty. Exp. Calculated of the physical inventory order line.  
  
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
 [How to: Enter Physical Inventory Orders](../how-to-enter-physical-inventory-orders.md)   
 [How to: Post Physical Inventory Orders](../how-to-post-physical-inventory-orders.md)   
 [How to: Calculate Quantity On Hand for a Physical Inventory Order](../how-to-calculate-quantity-on-hand-for-a-physical-inventory-order.md)   
 [How to: Finish a Physical Inventory Recording](../how-to-finish-a-physical-inventory-recording.md)   
 [How to: Analyze Physical Inventory Differences](../how-to-analyze-physical-inventory-differences.md)   
 [Physical Inventory Order Lines With Item Tracking Lines](../physical-inventory-order-lines-with-item-tracking-lines.md)