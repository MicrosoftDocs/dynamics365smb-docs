---
title: Create Put-aways from Internal Put-aways
description: This topic covers how to pick and put away without a source document, both how to create an internal pick, and how to create an internal put-away. 
author: SorenGP


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 7354, 7356, 7357, 7358, 7359, 7361
ms.date: 06/24/2021
ms.author: edupont

---
# Pick and Put Away Without a Source Document
After items have been put away and before they are picked to fulfill the needs of a production order or shipment, they are stored in the warehouse as part of available inventory.  

Situations can arise where items must be taken out of the warehouse pick bins temporarily, perhaps to serve as demonstration models in a sales presentation. These items are still owned by the company and are part of inventory, but they are not available for picking. They are registered in a special purpose bin that you create for this purpose; technically, the items are in the warehouse, but physically, they could be in a conference or demonstration room.  

In other situations, the production unit might unexpectedly need a few parts for a process. You can pick items for the production bins using the internal pick. When the process is over and output is created, you post the consumption of the items and empty the production bin, which in turn decreases the quantity of the item at your location.  

Likewise, items can be returned to the warehouse to be put away. The items may have been taken out of available inventory for a production order, and then not used at all. To make them part of available inventory again, they must be put away in the bin.  

The **Internal Put-aways** enables you to perform put-aways without having to refer to a particular source document. You can easily set up all the information you need to create a put-away warehouse instruction.  

> [!NOTE]  
>  If you are not using internal picks and internal put-aways, these adjustments can be performed using the methods to move items from bin to bin or to post quantity adjustments in a bin.  
>   
>  When the location uses directed put-away and pick, and therefore uses bin types, you cannot manually move items in or out of a bin of bin type RECEIVE, because items that are in a RECEIVE-type bin must be registered as being put away before they are part of available inventory.  

## To create an internal pick  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Whse. Internal Pick**, and then choose the related link.  
2. Choose the **New** action.
3. Fill in the **No.** field, **Location Code** field, and the **To Bin Code** field on the **General** FastTab. The **To Bin Code** field specifies the bin where you want to place the picked items. For production purposes, this bin would be the inbound production bin or the open shop bin. For other purposes, choose a bin code of a bin type that is not used for picking, most likely a staging, shipping, or special purpose bin.  
4.  Select an item in the **Item No.** field, and fill in the quantities you want to pick.  
5. Choose the **Create Pick** action. A warehouse pick instruction is now ready for a warehouse employee to perform. Alternatively you can choose the **Release** action and create warehouse picks using the **Picks worksheet**. For more information see,  [Plan Picks in Worksheets](warehouse-how-to-plan-picks-in-worksheets.md)

## To create an internal put-away  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Whse. Internal Put-away**, and then choose the related link.  
2. Choose the **New** action.
3. Fill in the header of a new internal put-away with at least the **No.** and **Location Code**.
4. Fill in a line for each item you wish to move to the warehouse. You only have to fill in the **Item No.** and the **Quantity** fields.

  > [!NOTE]  
  > When you choose the **Item No.** field, the **Bin Contents List** opens instead of the **Item List**. This is because you want to put away an item that is in a particular bin - *bin content* - not just an item, and you already know the bin the item should be taken from.  <!--If you filled in **From Bin Code** in the header, the bin content will be filtered by value defined in the **From Bin Code**.-->
5. To fill the lines with the entire bin content or the filtered bin content of bins in the location, choose the **Get Bin Content** action.  
6. Choose the **Create Put-away** action. A warehouse put-away instruction is now ready for a warehouse employee to perform. Alternatively you can choose the **Release** action and create warehouse put-aways using the **Put-away worksheet**. For more information see,  [Plan Put-aways in Worksheets](warehouse-how-to-plan-put-aways-in-worksheets.md)

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
