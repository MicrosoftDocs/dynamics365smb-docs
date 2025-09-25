---
title: How to pick items with inventory picks
description: Learn how to use inventory picks to record and post picking and shipping info for source documents.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 05/13/2025
ms.custom: bap-template
ms.search.forms: 931, 7377
---
# Pick items with inventory picks

In [!INCLUDE[prod_short](includes/prod_short.md)], you pick and ship items using one of four methods, as described in the following table.

|Method|Outbound Process|Require Pick|Require Shipment|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------|----------------|-----|---------|-------------------------------------------------------------------------------------|  
|A|Post the pick and shipment from the order line|||No dedicated warehouse activity.|  
|B|Post the pick and shipment from an inventory pick document|Turned on||Basic: Order-by-order.|  
|C|Post the pick and shipment from a warehouse shipment document||Turned on|Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post the pick from a warehouse pick document, and post the shipment from a warehouse shipment document|Turned on|Turned on|Advanced|  

Learn more at [Outbound Warehouse Flow](design-details-outbound-warehouse-flow.md).

This article refers to method B in the table.

When your location is set up to require pick processing but not shipment processing, use the **Inventory Pick** page to record and post picking and shipping information for your source documents. Outbound source documents can be sales orders, purchase return orders, and outbound transfer orders.

> [!NOTE]
> Production and assembly order component needs also represent outbound source documents. To learn more about handling production and assembly orders for internal processes, go to [Design Details: Internal Warehouse Flows](design-details-internal-warehouse-flows.md).
>
> Although service orders are also outbound source documents, they don't support the basic, order-by-order level of complexity.
>
> When picking and shipping sales line quantities that are assembled to the order, there are rules you must follow when you create inventory pick lines. Learn more at [Handling Assemble-to-Order Items with Inventory Picks](#handling-assemble-to-order-items-with-inventory-picks).  

You can create an inventory pick in three ways:

* Create the inventory pick directly from the source document.  
* Create inventory picks for multiple source documents at the same time by using a batch job.
* Request the pick in two steps by first releasing the source document, which acts as a signal to the warehouse that the source document is ready picking.

The inventory pick can then be created from the **Inventory Pick** page based on the source document.  

## To create an inventory pick from the source document

1. In the source document, which can be a sales order, purchase return order, or outbound transfer order, choose the **Create Inventory Put-away/Pick** action.
2. Select the **Create Invt. Pick** checkbox.  
3. Choose the **OK** button.

## To create multiple inventory picks with a batch job

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Create Inventory Put-away/Pick/Movement**, and then choose the related link.  
2. On the **Warehouse Request** FastTab, use the **Source Document** and **Source No.** fields to filter on certain types of documents or ranges of document numbers. For example, you can create picks only for sales orders.  
3. On the **Options** FastTab, select the **Create Invt. Pick** checkbox.
4. Choose the **OK** button.

## To create the pick in two steps

### To request an inventory pick by releasing the source document

For sales orders, purchase return orders, and outbound transfer orders, you create the warehouse request by releasing the order. Releasing the order makes the items available for picking.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then choose the related link.
2. Select the sales order that you want to release, and then choose the **Release** action.

### To create an inventory pick based on the source document

After you release an order, the warehouse employee can create an inventory pick.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Inventory Picks**, and then choose the related link.  
2. Choose the **New** action.  
3. In the **Source Document** field, select the type of document you're picking for.  
4. In the **Source No.** field, select the source document.  
5. Alternatively, choose the **Get Source Document** action to create a list of all outbound source documents that are ready for picking at the location.  
6. Choose the **OK** button to fill the pick lines according to the selected source documents.  

## To record inventory picks

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Inventory Pick**, and then choose the related link.  
2. In the **Bin Code** field on the pick lines, the bin that the items must be picked from is suggesting per the item's default bin. You can change the bin in this page if necessary.  
3. Perform the pick, and then enter the quantity that in the **Qty. to Handle** field.

    If you must pick the items for a line from more than one bin, for example because the full quantity isn't in the bin, use the **Split Line** action on the **Lines** FastTab. The action creates a line for the remaining quantity to handle.

4. Choose the **Post** action.  

    * Post the shipment of the source document lines that were picked.
    * If the location uses bins, posting also creates warehouse entries for the changes to the bin quantity.  

    [!INCLUDE [preview-posting-warehouse](includes/preview-posting-warehouse.md)]

## Handling assemble-to-order items with inventory picks

You can also use the **Inventory Pick** page to pick and ship for sales where items must be assembled before they can be shipped. Learn more at [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).

Assemble-to-order items aren't physically in a bin until they're assembled and posted as output to a bin. Picking assemble-to-order items from a bin for shipments follows a special flow.

1. Warehouse workers take the assembly items from bins to the shipping dock, and then post the inventory picks.
2. Inventory picks post the assembly output, the component consumption, and the sales shipment.

You can set up [!INCLUDE[prod_short](includes/prod_short.md)] to automatically create an inventory movement when the inventory pick for the assembly item is created. Select the **Create Movements Automatically** field on the **Assembly Setup** page. Learn more at [Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md).

Inventory pick lines for sales items are created in different ways, depending on whether you assemble to order none, some, or all of the sales line quantities. In scenarios where some of the quantity is assembled and some is picked from inventory, a minimum of two pick lines are created.

For sales where the full quantity on the sales order line is assembled to order, one inventory pick line is created for the quantity. The value in the **Quantity to Assemble** field is the same as the value in the **Qty. to Ship** field. The **Assemble to Order** field is selected on the line.

If you set up an assembly output flow for the location, the **Bin Code** field on the inventory pick line contains the value from the following fields, in the following order.

* ***Asm.-to-Order Shpt. Bin Code** <!-- not applicable for inv pick-->
* **From-Assembly Bin Code**

If a bin code isn't specified on the sales order line, and no assembly output flow is set up for the location, the **Bin Code** field on the inventory pick line is empty. The warehouse worker must open the **Bin Contents** page and select the bin where the assembly items are assembled.

In scenarios where a part of the quantity is assembled and another must be picked, a minimum of two pick lines are created.

* One pick line for the assemble-to-order quantity. [!INCLUDE [prod_short](includes/prod_short.md)] uses the following fields, in this order, to determine the bin code: **Bin Code**, **Asm.-to-Order Shpt. Bin Code**, and then **From-Assembly Bin Code**. If these fields are blank, the warehouse employee must open the **Bin Contents** page and choose the bin where the items are assembled.  
* The other pick line depends on which bins can fulfill the remaining quantity. If the item is kept in multiple bins, multiple lines are created. The line for the take is based on the quantity in the **Qty. to Ship** field.

> [!NOTE]  
> If items are assembled to order, the inventory pick for the linked sales order creates an inventory movement for all of the assembly components.  

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Walkthrough: Picking and Shipping in Basic Warehouse Configurations](walkthrough-picking-and-shipping-in-basic-warehousing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
