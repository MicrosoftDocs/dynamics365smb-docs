---
title: "How to: Enter Physical Inventory Orders"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "inventory, assigning physical inventory"
  - "inventory, physical orders"
  - "physical inventory, orders"
  - "physical inventory, recording"
ms.assetid: 9f8ecf55-4915-48dc-95dc-2e519bac2242
caps.latest.revision: 48
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "de-de"
---
# How to: Enter Physical Inventory Orders
A physical inventory order is a complete document that consists of a physical inventory order header and some physical inventory order lines. The information on a physical inventory header describes how to take the physical inventory. You can fill in the header manually. You can create a physical inventory order and relate it to one or more physical inventory recordings.  
  
 The physical inventory order lines contain the information about the items and their locations. You can create the physical inventory order lines manually, or you can let the program automatically create physical inventory order lines for you. You can do this by using batch jobs.  
  
 Before you can create physical inventory orders you have to set up properties for physical inventory. For more information, see [How to: Set Up Physical Inventory Documents](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-set-up-physical-inventory-documents.md).  
  
### To create a physical inventory order  
  
1.  In the **Search** box, enter **\($ N\_5005350 Phys. Inventory Order $\)**, and then choose the related link.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  Fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Description**|Sets a description for the physical inventory order.|  
    |**Location Code**|Sets location code for the item in the order line.|  
    |**Person Responsible**|Select the code for the person responsible for taking the inventory.<br /><br /> Optionally, you can add this information later.|  
    |**Order Date**|Sets the creation date for the physical inventory order.|  
    |**Posting Date**|Sets the posting date for the physical inventory order.|  
  
 You can add lines to the physical inventory order manually, or [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] can create new physical inventory order lines automatically. To create new physical inventory order lines automatically, you have two possibilities:  
  
-   You can create new physical inventory order lines based on inventory items and item ledger entries.  
  
-   You can create new physical inventory order lines based on existing or posted physical inventory orders by using the copy function.  
  
 Both batch jobs will check if there is already a line with the same values in the following fields on a physical inventory order line: [\($ T\_5005351\_20 Item No. $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_20-item-no.-$-.md), [\($ T\_5005351\_21 Variant Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_21-variant-code-$-.md), [\($ T\_5005351\_22 Location Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_22-location-code-$-.md), and [\($ T\_5005351\_23 Bin Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-t_5005351_23-bin-code-$-.md). In this case the new line is not inserted automatically to avoid duplicate lines.  
  
### To automatically add physical inventory order lines from inventory  
  
1.  In the **\($ N\_5005350 Phys. Inventory Order $\)** window, on the **Actions** tab, in the **Functions** group, choose **Calculate Lines**.  
  
2.  In the **\($ B\_5005360 Calc. Phys. Invt. Order Lines $\)** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Calculate Qty. Expected**|Select to calculate and insert the quantity expected data for newly created physical inventory order lines.|  
    |**Items Not on Inventory**|Select to insert physical inventory order lines for items that have a value of zero in the **Quantity Expected** field.|  
  
3.  Optionally, on the **Item** FastTab, select the appropriate filters, and then choose the **OK** button.  
  
4.  When the batch job completes, choose the **OK** button.  
  
### To automatically add physical inventory order lines by copying documents  
  
1.  In the **\($ N\_5005350 Phys. Inventory Order $\)** window, on the **Actions** tab, in the **Functions** group, choose **Copy Document**.  
  
2.  In the **\($ B\_5005362 Copy Phys. Invt. Order $\)** window, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Document Type**|Specify the type of document to copy.|  
    |**Document No.**|Specify the document to copy.|  
    |**Calculate Qty. Expected**|Select to calculate and insert the quantity expected data for newly created physical inventory order lines.|  
  
3.  When the batch job completes, choose the **OK** button.  
  
     You can run the batch job more than once. If there are already existing lines for the physical inventory order, the program will append the new lines at the end.  
  
 For each physical inventory order, you can create one or more physical inventory recordings. There you can document the physical count. For more information, see [How to: Create a Physical Inventory Recording](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-create-a-physical-inventory-recording.md).  
  
 You can compare and document the expected quantities from the physical inventory order lines with the \(counted\) quantities from the physical inventory recording lines. You can post the physical inventory differences.  
  
## See Also  
 [Physical Inventory Documents](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/physical-inventory-documents.md)   
 [How to: Enter Dimensions for Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-enter-dimensions-for-physical-inventory-orders.md)   
 [How to: View Duplicate Physical Inventory Order Lines](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-view-duplicate-physical-inventory-order-lines.md)   
 [How to: Create a Physical Inventory Recording](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-create-a-physical-inventory-recording.md)   
 [How to: Calculate Quantity On Hand for a Physical Inventory Order](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-calculate-quantity-on-hand-for-a-physical-inventory-order.md)   
 [How to: Post Physical Inventory Orders](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Germany/how-to-post-physical-inventory-orders.md)   
 [\($ B\_5005360 Calc. Phys. Invt. Order Lines $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-b_5005360-calc.-phys.-invt.-order-lines-$-.md)   
 [\($ B\_5005362 Copy Phys. Invt. Order $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/-$-b_5005362-copy-phys.-invt.-order-$-.md)