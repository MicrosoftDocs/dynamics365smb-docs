---
title: Outbound warehouse process overview
description: This article describes the outbound warehouse workflow.
author: brentholtorf
ms.author: bholtorf 
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: concept-article
ms.date: 06/17/2025
ms.custom: bap-template    
---
# Outbound warehouse processes

Outbound processes in warehouses start when you release a source document to take items out of a warehouse location. For example, either to ship the items somewhere or to move them to another company location. You can ship physical and noninventory items. To learn more about receiving noninventory items, go to [Post noninventory items](#post-non-inventory-items).

In principle, the process of shipping outbound orders consists of two activities:

* Picking items from the shelves.
* Shipping items out of the warehouse.

The source documents for outbound warehouse flow are:  

* Sales order  
* Outbound transfer order  
* Purchase return order  
* Service order  

> [!NOTE]
> Production and assembly orders with component needs also represent outbound source documents. Production and assembly orders are a little different because they're typically internal processes that don't involve shipping. Instead, they're used to put-away produced items or move the components needed to assemble an item to an assembly area. Learn more about these processes at [Design Details: Internal Warehouse Flows](design-details-internal-warehouse-flows.md).  

In [!INCLUDE[prod_short](includes/prod_short.md)], you pick and ship items using one of four methods, as described in the following table.

|Method|Outbound Process|Require Pick|Require Shipment|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------|----------------|-----|---------|-------------------------------------------------------------------------------------|  
|A|Post the pick and shipment from the order line|||No dedicated warehouse activity.|  
|B|Post the pick and shipment from an inventory pick document|Turned on||Basic: Order-by-order.|  
|C|Post the pick and shipment from a warehouse shipment document||Turned on|Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post the pick from a warehouse pick document, and post the shipment from a warehouse shipment document|Turned on|Turned on|Advanced|  

The approach to choose depends on your warehouse practices and level of organizational complexity. The following are some examples that might help you decide.

* In an order-by-order environment with straightforward processes and a simple bin structure, method A, picking and shipping from the order line is appropriate.
* If items for an order line come from more than one bin, or if warehouse workers can't work with order documents, the use of separate pick documents is appropriate, method B.
* If picking and shipping involves multiple orders and requires greater control and overview, you might choose methods C and D to separate the picking and shipping tasks.  

In methods A, B, and C, picking and shipping activities are combined in one step when posting the document as shipped. In method D, you first register the pick, and then post the shipment later from a different document.

> [!NOTE]
> Although warehouse picks and inventory picks sound similar, they're different documents, and they're used in different processes.
>
> * The inventory pick used in method B, together with registering picking information, also posts the shipment of the source document.
> * The warehouse pick used in method D can't be posted and only registers the pick. The registration makes the items available for the warehouse shipment but doesn't post the shipment. In the outbound flow, the warehouse pick requires a warehouse shipment.

## No dedicated warehouse activity

The following articles provide information about how to process receipts for source documents if you don't use dedicated warehouse activities.

* [Sell Product](sales-how-sell-products.md)
* [Transfer Orders](inventory-how-transfer-between-locations.md)
* [Process Purchase Returns or Cancellations](purchasing-how-process-purchase-returns-cancellations.md)
* [Create Service Orders](service-how-to-create-service-orders.md)

## Basic warehouse configurations

The following diagram illustrates the outbound warehouse processes for different types of documents in basic warehouse configurations. The numbers in the diagram correspond with the steps in the sections following the diagram.  

:::image type="content" source="media/design-details-warehouse-management-outbound-basic-flow.png" alt-text="Shows the steps in a basic outbound flow in a warehouse.":::

### 1: Release a source document in a basic configuration

When you use the **Release** action on a source document, such as a sales or transfer order, the items on the document are ready to be handled in the warehouse. For example, picked and put in the bin specified on the document. Alternatively, you can create inventory pick documents for individual lines on orders, in a push fashion, based on specified bins and quantities to handle.  

### 2: Create an inventory pick

On the **Inventory Pick** page, the warehouse worker retrieves, in a pull fashion, the source document lines. Alternatively, the inventory pick lines are already created, in a push fashion, by the user who is responsible for the source document.  

### 3: Post an inventory pick

On each line for items that were picked or moved, partially or fully, fill in the **Quantity** field, and then post the inventory pick. Source documents related to the inventory pick are posted as shipped or consumed.  

For inventory picks, negative item ledger entries are created, warehouse entries are created, and the pick request is deleted, if fully handled. For example, the **Quantity Shipped** field on the outbound source document line is updated. A posted shipment document is created  that reflects the sales order, for example, and the shipped items.  

## Advanced warehouse configurations

The following diagram illustrates the outbound warehouse processes for different types of documents in advanced warehouse configurations. The numbers in the diagram correspond with the steps in the sections following the diagram.  

:::image type="content" source="media/design_details_warehouse_management_outbound_advanced_flow.png" alt-text="Shows the steps in an advanced outbound warehouse flow.":::

### 1: Release a source document in an advanced configuration

Releasing a source document in advanced configurations does the same thing as for basic configurations. The items become available for handling in the warehouse. For example, they can be included in a shipment.  

### 2: Create a warehouse shipment

On the **Warehouse Shipment** page, get the lines from the released source document. You can combine lines from several source documents in one warehouse shipment.  

### 3: Create a warehouse pick

On the **Warehouse Shipment** page, create warehouse pick activities for warehouse shipments in one of two ways:

* In a push fashion, where you use the **Create Pick** action. Select the lines to pick and prepare the picks by specifying, for example, which bins to take from and place in, and how many units to handle. The bins can be predefined for the warehouse location or resource.
* In a pull fashion, where you use the **Release** action. On the **Pick Worksheet** page, warehouse workers can use the **Get Warehouse Documents** action to get their assigned picks. When the warehouse picks are fully registered, the lines in the **Pick Worksheet** are deleted.

### 4: Register a warehouse pick

On the **Warehouse Pick** page, a warehouse worker fills in the **Quantity** field for each line that they fully or partially picked, and then registers the pick.

Warehouse entries are created, and the warehouse pick lines are deleted if the full quantity was picked. The warehouse pick document remains open until the full quantity of the warehouse shipment is registered. The **Qty. Picked** field on the warehouse shipment lines is updated accordingly.  

### 5: Post the warehouse shipment

When all items on the warehouse shipment document are registered as picked, the warehouse worker posts the shipment. Posting updates the item ledger entries to reflect the reduction in inventory. For example, the **Quantity Shipped** field on the outbound source document line is updated.  

## Post noninventory items

[!INCLUDE [post-non-inventory-items](includes/post-non-inventory-items.md)]

## Related information

[Warehouse Management](design-details-warehouse-management.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
