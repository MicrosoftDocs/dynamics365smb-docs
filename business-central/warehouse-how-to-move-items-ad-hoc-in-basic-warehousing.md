---
title: Move Items Unplanned in Basic Warehouse Configurations
description: This article explains unplanned internal movements between bins without a demand from a source document. 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 12/16/2022
ms.custom: bap-template
ms.search.form: 393, 7382
---
# Move Items Internally in Basic Warehouse Configurations

You might want to move items between bins without a demand from a source document. For example, as part of the following activities:

* Reorganize your warehouse.
* Bring items to an inspection area.
* Move extra items to and from a production area. 

How you move items depends on how your warehouse is set up as a location. Learn more at [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

In warehouse configurations where the **Bin Mandatory** setup toggle is turned on, but not **Directed Pick and Put-away** you can register unplanned movements on the following pages:  

* On the **Internal Movement** page.
* On the **Item Reclassification Journal** page.  

## Internal movements

The **Internal Movements** page lets you specify Take and Place lines when there isn't a demand from a source document. The Internal Movement page is like a worksheet for organizing things. You can't process the actual movement directly from it. When a line is filled in, use the **Create Inventory Movement** action to send the line to the **Inventory Movement** page, which is where you process and register the movement.

### To move items as an internal movement

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Internal Movements**, and then choose the related link.  
2. Choose **New** action. Make sure that the **No.** field on the **General** FastTab is filled in.
3. In the **Location Code** field, enter the location where the movement takes place.  

    If the location is your default location as a warehouse employee, the location code is added automatically.  
4. In the **To Bin Code** field, enter the code for the bin that you want to move the items to.

    For example, in production, the bin could be the open shop floor bin defined on the location card or work center.  
5. In the **Due Date** field, enter the date by which to complete the movement.  
6. On each line, fill in the fields as necessary. Internal movement documents have one line per movement. The line contains both the take and the place actions.
7. Choose the **Item No.** field to open the **Bin Contents List** page. Select the item to move based on its availability in bins. You can also choose the **Get Bin Contents** action to fill the internal movement lines based on your filters.  

    After you select the item, the **From Bin Code** field is automatically filled in according to the selected bin content. You can choose any bin where the item is available. The **Item No.** and **From Bin Code** fields are related. Changing the value in one field might change the value in the other.  

    The **To Bin Code** field is filled in with the value you entered on the header. You can change it on the line to any other bin code that isn’t blocked or dedicated for special purposes. Learn more at [The Dedicated field](warehouse-how-to-create-individual-bins.md#the-dedicated-field).  

8. After you define which bins you want to move the items from and to, enter the quantity to move in the **Quantity** field.  

    > [!NOTE]  
    > The quantity must be available in the bin specified in the **From Bin Code** field.  

9. When you're ready to process the movement, choose the **Create Inventory Movement** action.  

    > [!NOTE]  
    >  After you create the movement, the internal movement lines are deleted.  

Perform the rest of the unplanned movement on the **Inventory Movement** page in the same way as you would for a movement based on source documents.

### To record the inventory movement

1. On the **Inventory Movement** page, open the document to record the movement for.  
2. In the **Bin Code** field on the movement lines, the bin where the items must be picked from is where the item is available. You can change the bin if needed.
3. Perform the move and enter the information for the moved quantity in the **Qty. to Handle** field. The value on the Take and the Place lines must be the same. Otherwise, you can't register the movement.

    If you must take the items for a line from more than one bin, for example because the full quantity isn't in the bin, use the **Split Line** action on the **Lines** FastTab. The action creates a line for the remaining quantity to handle.  
4. Choose the **Register Invt. Movement** action.  

The following happens during the posting process:

* Warehouse entries indicate that the quantity is transferred from the take bins to the place bins.

## To move items with the item reclassification journal

Instead of using movement documents, you can record movements by reclassifying bin codes on items. Learn more at [Count, Adjust, and Reclassify Inventory Using Journals](inventory-how-count-adjust-reclassify.md).

> [!NOTE]  
> Movements posted with reclassification journals don't make the movement documents ready to move.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Item Reclass. Journal**, and then choose the related link.  
2. On each journal line, define the bins to move the items from and to by filling in the **Bin Code** and the **New Bin Code** fields.  

    1. To move a bin's entire contents to another bin, choose the **Get Bin Contents** action.  
    2. Use the filters to find the bin that contains the items you'd like to move, and then choose **OK**. The journal lines are filled with the contents of the bin.  
3. Fill in the remaining fields on each journal line.
4. Post the reclassification journal.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
