---
title: Receive items
description: This article is an overview of the different ways to receive items at a warehouse with a warehouse receipt.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 01/27/2025
ms.search.form: 5768, 7330, 7332, 7333, 7342, 7363, 8510, 9008
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai.usage: ai-assisted

---
# Receive items with warehouse receipts

In [!INCLUDE[prod_short](includes/prod_short.md)], you receive items and put them away using one of four methods, as described in the following table.

|Method|Inbound Process|Require Receipts|Require Put-aways|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------------|---------------------|--------------|----------------|------------|  
|A|Post receipt and put-away from the order line|||No dedicated warehouse activity.|  
|B|Post receipt and put-away from an inventory put-away document||Turned on|Basic: Order-by-order.|  
|C|Post receipt and put-away from a warehouse receipt document|Turned on||Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document|Turned on|Turned on|Advanced|  

To learn more about how to handle inbound items, go to [Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md).

The following article refers to methods C and D in the previous table.

## Receive items with a warehouse receipt

When items arrive at a warehouse that processes warehouse receipts, get the lines of the document that triggered the receipt. If you use bins, you can either accept the default bin or specify the bin to put the items in. The latter might be required when you receive an item for the first time. Then, enter the quantities of the items you received and post the receipt.  

You can create warehouse receipt in one of two ways:

* In a push fashion, when work is done on an order-by-order basis. Choose the **Create Warehouse Receipt** action in the source document, such as a purchase order, sales return order, or transfer order to create a warehouse receipt for a source document.
* In a pull fashion, where you use the **Release** action in the source document, such as a purchase order, sales return order, or transfer order to release the document to the warehouse. A warehouse employee can create a **Warehouse Receipt** for one or more released source documents.

The following procedure describes how to create a warehouse receipt in a pull fashion.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts**, then choose the related link.  
2. Choose the **New** action.  

    Fill in the **Location Code** field on the **General** FastTab. When you retrieve source document lines, some of the information is copied to each line.

    For a location that requires bins, fill in the **Bin Code** field. Depending on your setup, [!INCLUDE[prod_short](includes/prod_short.md)] can add the bin code for you. Learn more at [Zone and bin codes](warehouse-how-receive-items.md#zone-and-bin-codes).  

3. You can get source document in two ways:

    1. Choose the **Get Source Documents** action. The **Source Documents - Inbound** page opens. Here you can select one or more source documents released to warehouse that requires receipt.
    2. Choose the **Use Filters to Get Src. Docs.** action. The **Filters to Get Source Docs. - Inbound** page opens. Here you can select Source Document Filter and run it. All released source document lines that meet the filter criteria are added on the **Warehouse Receipt** page. Learn more at [How to Use Filters to Get Source Documents](warehouse-how-receive-items.md#how-to-use-filters-to-get-source-documents).

4. Set the quantity to receive.

    The **Qty. to Receive** field contains the quantity outstanding for each line, but you can change the quantity as needed. 

    To set the value in the **Qty. to Receive** field on all lines to zero, choose the **Delete Qty. to Receive** action. For example, setting the quantities to zero is useful if you're using a barcode scanner to update the received quantities. To add the outstanding quantities from the source document again, choose the **Autofill Qty. to Receive** action.  

    On a warehouse receipt document where the received quantity is higher than ordered, enter the quantity received in the **Qty. to Receive** field. If the increase is within the tolerance specified by an assigned over-receipt code, the **Over-Receipt Quantity** field updates to show the quantity by which the value in the **Quantity** field is exceeded. If the increase is over the tolerance, the over-receipt isn't allowed.

5. Post the warehouse receipt. The quantity fields are updated on the source documents, and the items are added to inventory.  

    [!INCLUDE [preview-posting-shipment](includes/preview-posting-shipment.md)]

    > [!TIP]
    > If you use warehouse put-aways (method D in the table in the beginning of this article), the items are received. However, you can't pick them until they're put away. To learn more about putting away items, go to [Put Items Away with Warehouse Put-aways](warehouse-how-to-put-items-away-with-warehouse-put-aways.md).
    >
    > Otherwise, consider using the **Post and Print** action. The action posts the receipt and prints it as a put-away instruction that shows where to put the item.

    > [!NOTE]  
    > If your warehouse uses cross-docking, you can check whether you can cross-dock items without putting them away. To learn more about cross-docking, go to [Cross-Dock Items](warehouse-how-to-cross-dock-items.md).

## How to use filters to get source documents

From a warehouse receipt, you can use the **Filters to Get Source Docs.** page to retrieve the released source document lines that specify the items to receive.

1. In the warehouse receipt, choose the **Use Filters to Get Src. Docs.** action.
2. To set up a new filter, enter a descriptive code in the **Code** field, then choose the **Modify** action.

    The **Source Document Filter Card - Inbound** page appears.

3. Use the filters to define the type of source document lines to retrieve. For example, you can select types of source documents, such as purchase or transfer orders.
4. Choose **Run**.  

All released source document lines that meet the filter criteria are added on the **Warehouse Receipt** page on which you activated the filters.

You can make an unlimited number of filter combinations. Filters are saved on the **Filters to Get Source Docs.** page, and they're available the next time you need them. You can change the criteria at any time by choosing the **Modify** action.

## Zone and bin codes

To receive items with warehouse class codes other than the class code of the bin in the **Bin Code** field on the document header, clear the **Bin Code** field on the header before you retrieve source document lines for the items.  
<!-- TBD, table with comparison of various options-->

If bins are mandatory for a location, zone and bin codes are added to warehouse receipt documents as follows:

* For advanced configurations that use directed put-away and pick, [!INCLUDE [prod_short](includes/prod_short.md)] uses the receipt bin code from the **Location Card** page for the location. If a receipt bin code isn't specified, no bin is specified. If the item and receipt bins don't match, the receipt bin code is blank.
* In other configurations, if a receipt bin code isn't specified, [!INCLUDE [prod_short](includes/prod_short.md)] uses the bin code from the source document.

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
