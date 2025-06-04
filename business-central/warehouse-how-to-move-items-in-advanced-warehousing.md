---
title: Move items in warehouses that use directed put-away and pick
description: This article explains how to move items in locations that use directed put-away and pick.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 04/23/2024
ms.custom: bap-template
ms.search.form: 7351,
ms.service: dynamics-365-business-central
---

# Move items in advanced warehouse configurations that use directed put-away and pick

You can move items between bins without a demand from a source document. For example, you might want to do that as part of the following activities:

* Reorganize your warehouse.
* Bring items to an inspection area.
* Take items out of the warehouse pick bins temporarily, perhaps to serve as demonstration models in a sales presentation.
* Move extra items to production area for components configured with some flushing methods.
* Move produced or assembled items from production or assembly area to warehouse.
* Move items from bulk storage area to bins you use for picking.

How you move items depends on how your warehouse is set up as a location. Learn more at [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

In warehouse configurations where the **Directed Pick and Put-away** toggle is turned on for locations, you can register unplanned movements on the following pages:  

* Movement Worksheet
* Warehouse Internal Pick
* Warehouse Internal Put-away
* Warehouse Reclassification Journal

The **Movement Worksheet** , **Warehouse Internal Pick**, and  **Warehouse Internal Put-away** pages work in the same way. Use the pages to prepare warehouse activities for warehouse employees. The difference is in the advanced functionality associated with each page, and the different types of warehouse activities that are probably performed by different employees:

* Movement worksheet lets you fill up high-ranking pick bins with items from other bins
* Put-aways use put-away templates
* Picking uses bin ranking and availability

## Warehouse movement worksheet

### To move items with the warehouse movement worksheet

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Movement Worksheet**, and then choose the related link.  
2. Fill in the fields on the worksheet lines manually, or use one of the following actions to automatically fill in the lines:

    * **Get Bin Content** fills in the worksheet lines with the contents of the bin or bins you specify.
    * **Calculate Bin Replenishment** uses the bin rankings to suggest replenishment for high-ranking bins from low-ranking bins.

    > [!NOTE]  
    > If the item meets the criteria in the list below, the **From Zone** and **From Bin** fields will be blank. [!INCLUDE [prod_short](includes/prod_short.md)] calculates from where to move the items only when you use the **Create Movement** action.  
    >  
    > * The item has an expiration date.  
    > * The **Pick According to FEFO** toggle is turned on for the location.  
    > * You're using the **Calculate Bin Replenishment** feature.  

3. Choose the **Create Movement** action to create the movement. When the move is complete, you can register it.  

### To register the warehouse movement

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Movements**, and then choose the related link.  
2. Open the movement document to register.  
3. On **Place** lines, specify where, which, and by when to move the item by choosing values in the **Zone Code**, **Bin Code**, **Qty. to Handle**, or **Due Date** fields.  
4. On **Take** lines, in the **Qty. to Handle** field, specify the quantity of the bin content that you want to move. You can only edit this field on **Take** lines. 

    > [!NOTE]
    > If you must pick or place the items for one line in more than one bin, for example because the designated bin is full, use the **Split Line** action on the **Lines** FastTab. The action creates a line for the remaining quantity to handle.
 
5. To register all suggested quantities as specified in the **Quantity** field, choose the **Autofill Qty. to Handle** action.  
6. Choose the **Register** action.  

> [!NOTE]  
> For locations that use directed put-away and pick, you can't manually move items in bins of the type **RECEIVE** because they aren't yet considered as available inventory. You must put away the items in these bins before they're available for movements.

## Internal pick  

### To create an internal pick  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Whse. Internal Pick**, and then choose the related link.  
2. Choose the **New** action.
3. Fill in the **No.** field, **Location Code** field, and the **To Bin Code** field on the **General** FastTab. The **To Bin Code** field specifies the bin where you want to place the picked items. For production purposes, this bin would be the inbound production bin or the open shop bin. For other purposes, choose a bin code of a bin type that is not used for picking, most likely a staging, shipping, or special purpose bin.  
4. Select an item in the **Item No.** field, and fill in the quantities you want to pick.  
5. Choose the **Create Pick** action. A warehouse pick instruction is now ready for a warehouse employee to perform. Alternatively, choose the **Release** action and create warehouse picks using the **Pick Worksheet** page. To learn more about pick worksheets, go to [Create pick documents in bulk with the pick worksheet](warehouse-how-to-pick-items-for-warehouse-shipment.md#to-create-pick-documents-in-bulk-with-the-pick-worksheet).
6. When the pick is complete, you can register it.  

### To register the warehouse pick

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Picks**, and then choose the related link.  

    To work on a particular pick, select the pick from the list, or filter the list to find the picks that are assigned to you.  
2. If the **Assigned User ID** field is blank, enter your ID to identify yourself, if needed.  
3. Pick the items.  

    Because the warehouse is set up to use directed put-away and pick, bin ranking determines the bins to pick from. The bins are suggested on the pick lines. The instructions contain at least two separate lines for Take and Place actions.  

4. After you pick and place the items in the shipping area or shipping bin, choose the **Register Pick** action.  

## Internal put-away  

### To create an internal put-away  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Internal Put-aways**, and then choose the related link.  
2. Choose the **New** action.
3. Fill in the **No.** and **Location Code** fields.
4. Fill in a line for each item to move to the warehouse. The **Item No.** and the **Quantity** fields are required.

    > [!NOTE]  
    > When you choose an item in the **Item No.** field, the **Bin Contents** page opens instead of the **Items** page. This page opens because you're putting away an item that is assigned to a particular bin - *bin content* - not just an item, and you already know the bin the item should be taken from. If you filled in the **From Bin Code** field, the bin content will be filtered by that value.

5. To fill the lines with the entire bin content or the filtered content of bins in the location, choose the **Get Bin Content** action.  
6. Choose the **Create Put-away** action. A warehouse put-away instruction is now ready for a warehouse employee. Alternatively, choose the **Release** action to create warehouse put-aways using the **Put-away worksheet** page. To learn more about put-away worksheets, go to [Create put-away documents in bulk with the put-away worksheet](warehouse-how-to-put-items-away-with-warehouse-put-aways.md#to-create-put-away-documents-in-bulk-with-the-put-away-worksheet).
6. When the put-away is complete, you can register it.  

### To register the warehouse put away

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Put-aways**, and then choose the related link.
2. Open the warehouse put-away that's ready to handle.  
3. If required, enter your user ID when you start work on a put-away.  

    To optimize the put-away process, you can sort the put-away lines by various criteria. For example, by item, shelf number, or due date.
   
    * If the Take and Place lines for each receipt line don't immediately follow one another, and you want them to, sort the lines by selecting **Item** in the **Sorting Method** field.  
    * If the bin rankings reflect the physical layout of the warehouse, use the **Bin Ranking** sorting method to organize the work around the bin locations.

  > [!NOTE]  
  > Lines are sorted in ascending order by the selected criteria. If you sort by document, sorting is done first by document type based on the **Warehouse Activity Source Document** enum. If you sort by ship-to, sorting is done by destination type based on the **Warehouse Destination Type** field.

4. Perform the put-away.

    Each internal put-away line has become at least two lines in the warehouse put-away.  

    * The first line, with **Take** in the **Action Type** field, indicates where the items are located in the receiving area. You can't change the zone and bin on this line.  
    * The next line, with **Place** in the **Action Type** field, shows where to place the items in the warehouse. If you receive a large number of items on one receipt line, you might have to put the items away in several bins, so there's a Place line for each bin.  

5. When you have placed all the items in bins as instructed, choose the **Register Put-away** action.  

## To register a movement that has already happened

If you must register the fact that items has been already moved to other bins without a put-away, pick, or movement, you can use the **Whse. Reclassification Journal** page to register the movement.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Whse. Reclassification Journal**, and then choose the related link.  
2. Fill in the **Item No.**, **From Zone Code**, **From Bin Code**, **To Zone Code**, and **To Bin Code** fields.  
3. Choose the **Register** action.  

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
