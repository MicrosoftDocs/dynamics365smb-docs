---
title: How to Put Items Away with Inventory Put-aways
description: Learn how to use inventory put-away documents to record and post put-away and receipt information.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 09/19/2023
ms.custom: bap-template
ms.search.forms: 7375, 
---
# Put Items Away with Inventory Put-aways

In [!INCLUDE[prod_short](includes/prod_short.md)], you receive items and put them away using one of four methods, as described in the following table.

|Method|Inbound Process|Require Receipts|Require Put-aways|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------------|---------------------|--------------|----------------|------------|  
|A|Post receipt and put-away from the order line|||No dedicated warehouse activity.|  
|B|Post receipt and put-away from an inventory put-away document||Turned on|Basic: Order-by-order.|  
|C|Post receipt and put-away from a warehouse receipt document|Turned on||Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document|Turned on|Turned on|Advanced|  

Learn more at [Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md).

This article refers to method B in the table.

When your location is set up to require put-away processing but not receive processing, use an **Inventory Put-away** document to record and post put-away and receipt information for your source documents. Inbound source documents can be purchase orders, sales return orders, and inbound transfer orders.

> [!NOTE]
> Production and assembly output also represent inbound source documents. Learn more about handling production and assembly output for internal processes at [Design Details: Internal Warehouse Flows](design-details-internal-warehouse-flows.md).

You can create an inventory put-away in three ways:  

* Create the inventory put-away directly from the source document itself.  
* Create inventory put-aways for several source documents at the same time by using a batch job.  
* Create the put-away in two steps by first by releasing the source document to make the items available to be put away. You can create the inventory put-away based on the source document by using the **Inventory Put-away** page.  

## To create an inventory put-away from the source document

1. In the source document, which can be a purchase order, sales return order, or inbound transfer order, choose the **Create Inventory Put-away/Pick** action.  
2. Select the **Create Invt. Put-away** checkbox.
3. Choose the **OK** button. A new inventory put-away is created.

## To create multiple inventory put-aways with a batch job

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Create Inventory Put-away/Pick/Movement**, and then choose the related link. 
2. On the **Warehouse Request** FastTab, use the **Source Document** and **Source No.** fields to filter on certain types of documents or ranges of document numbers. For example, you can create put-aways for purchase orders only.
3. On the **Options** FastTab, select the **Create Invt. Put-away** checkbox.
4. Choose the **OK** button. The specified inventory put-aways are created.

## To create the put-away in two steps

### To request an inventory put-away by releasing the source document

When you release purchase orders, sales return orders, and inbound transfer orders, the items on the orders become available to be put away. The following steps describe how to make the items on a purchase order ready to be put away.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Select the purchase order that you want to release, and then choose the **Release** action.  

### To create an inventory put-away based on the source document

A warehouse employee can create a new inventory put-away based on the released source document.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Put-away**, and then select the related link.  
2. Choose the **New** action.  
3. In the **Source Document** field, select the type of source document you are putting away for.  
4. In the **Source No.** field, select the source document.  
5. Alternatively, choose the **Get Source Document** action to select the document from a list of inbound source documents that are ready for put-away at the location.  
6. Choose the **OK** button to fill the put-away lines according to the selected source document.  

## To record the inventory put-away

1. On the **Inventory Put-aways** page, open a previously created put-away document.  
2. In the **Bin Code** field on the put-away lines, the bins where the items must be put away are suggested based on the items' default bin. You can change the bin if needed.  
3. Perform the put-away, and then enter the actual quantity that was put away in the **Qty. to Handle** field.

    If you must place the items for one line in more than one bin, for example because the designated bin is full, use the **Split Line** action on the **Lines** FastTab. The action creates a line for the remaining quantity to handle.  
4. After you put the items away, choose the **Post** action.  

    * Post the receipt of the source document lines that have been put away
    * If the location uses bins, posting will also create warehouse entries to post the bin quantity changes.

    [!INCLUDE [preview-posting-warehouse](includes/preview-posting-warehouse.md)]

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
