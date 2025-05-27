---
title: Design Details - Inbound Warehouse Flow
description: Learn how to receive items at your warehouse, and register and match them to inbound source documents.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: warehouse
ms.date: 09/18/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Design details: Inbound warehouse flow

The inbound flow in a warehouse begins when items arrive in the warehouse of the company location, either received from external sources or from another company location. You can receive physical and non-inventory items. To learn more about receiving non-inventory items, go to [Post non-inventory items](#post-non-inventory-items).

In principle, the process of receiving inbound orders consists of two activities:

* Receive items at the dock, identify them, match them to a source document, and record the received quantity.
* Put away items in stock, and record the place you put them.

The source documents for inbound warehouse flow are:

* Purchase orders  
* Inbound transfer orders  
* Sales return orders  

> [!NOTE]
> Production and assembly output also represent inbound source documents. Learn more about handling production and assembly output for internal processes at [Design Details: Internal Warehouse Flows](design-details-internal-warehouse-flows.md).  

In [!INCLUDE[prod_short](includes/prod_short.md)], you receive items and put them away using one of four methods, as described in the following table.

|Method|Inbound Process|Require Receipts|Require Put-aways|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------------|---------------------|--------------|----------------|------------|  
|A|Post receipt and put-away from the order line|||No dedicated warehouse activity.|  
|B|Post receipt and put-away from an inventory put-away document||Turned on|Basic: Order-by-order.|  
|C|Post receipt and put-away from a warehouse receipt document|Turned on||Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document|Turned on|Turned on|Advanced|  

Selecting an approach depends on your company's practices and level of organizational complexity. The following are some examples that might help you decide.

* In an order-by-order warehouse environment, where most of the warehouse staff works directly with order documents, you might decide to use method A. 
* An order-by-order warehouse that has a more complex put-away process, or where warehouse staff separates their put-away activities from the order document, might use method B.
* Companies that need to plan the handling of multiple orders may find it helpful to use warehouse receipt documents, methods C and D.  

In methods A, B, and C, receiving and putting away are combined in one step when posting documents as received. In method D, the receipt is posted first to record the increase of inventory and that items are available for sale. The warehouse worker then registers the put-away to make the items available to pick for outbound orders. 

> [!NOTE]
> While warehouse put-aways and inventory put-aways sound similar, they're different documents and are used in different processes.
> * The inventory put-away used in method B, together with registering put-away information, also posts the receipt of the source document.
> * The warehouse put-away used in method D can't be posted and only registers the put-away. The registration makes the items available for the further processing but doesn't post the receipt. In the inbound flow, the warehouse put-away requires a warehouse receipt.

## No dedicated warehouse activity

The following articles provide information about how to process receipts for source documents if you don't have dedicated warehouse activities.

* [Record Purchases](purchasing-how-record-purchases.md)
* [Transfer Orders](inventory-how-transfer-between-locations.md)
* [Process Sales Return Orders](sales-how-process-sales-returns-orders.md)

## Basic warehouse configurations  

In a basic warehouse configuration, the **Require Put-away** toggle is turned on, but the **Require Receipt** toggle is turned off on the **Location Card** page for the location.

The following diagram illustrates the inbound warehouse flows by document type in basic warehouse configurations. The numbers in the diagram correspond with the steps in the sections following the diagram.  

:::image type="content" source="media/design_details_warehouse_management_inbound_basic_flow.png" alt-text="The basic inbound flow in a warehouse.":::

### 1: Release a source document to create a request for an inventory put-away  

When you receive items, release the source document, such as a purchase order or an inbound transfer order. Releasing the document makes the items available to be put away. You can also create inventory put-away documents for individual order lines, in a push fashion, based on bins and quantities to handle.  

### 2: Create an inventory put-away  

On the **Inventory Put-away** page, in a pull fashion, you can get the pending source document lines based on inbound warehouse requests. In a push fashion, you can also create inventory put-away lines when you create the source document.  

### 3: Post an inventory put-away  

On each line for items that have been put away, partially or fully, fill in the **Quantity** field and then post the inventory put-away. Source documents that are related to the inventory put-away are posted as received.  

* Positive item ledger entries are created.
* Warehouse entries are created for locations that require a bin code on all item transactions.
* The put-away request is deleted, if it's fully handled. For example, the **Quantity Received** field on the inbound source document line is updated.
* A posted receipt document is created that reflects the purchase order, for example, and the received items.  

## Advanced warehouse configurations  

To use an advanced warehouse configuration, turn on the **Require Receipt** toggle on the Location Card page for the location. The **Require Put-away** toggle is optional.

The following diagram illustrates the inbound warehouse flow by document type. The numbers in the diagram correspond with the steps in the sections following the diagram.  

:::image type="content" source="media/design_details_warehouse_management_inbound_advanced_flow.png" alt-text="The advanced inbound flow in a warehouse.":::

### 1: Release the source document  

When you receive items, release the source document, such as the purchase order or an inbound transfer order. Releasing the document makes the items available to be put away. The put away will contain references to the source document type and number.

### 2: Create a warehouse receipt  

On the **Warehouse Receipt** page, get the inbound source document lines. You can combine several source document lines in one warehouse receipt document. Fill in the **Qty. to Handle** field and select the receiving zone and bin, if necessary.  

### 3: Post the warehouse receipt  

Post the warehouse receipt to create positive item ledger entries. The **Quantity Received** field on the inbound source document line is updated.  

If the **Require Put-away** toggle is not turned on on the location card, this is where the process stops. Otherwise, posting the inbound source document makes the items available to be put away. The put away contains references the source document type and number.  

### 4: (Optional) Generate put-away worksheet lines

Get warehouse put-away lines in the **Put-away Worksheet** based on posted warehouse receipts or operations that produce output. On the lines you'll put-away, specify the following information:

* The bins to take items from.
* The bins to put items in.
* How many units to handle.

The bins can be predefined by the setup of the warehouse location or the resource that performed the operation.  

When all put-aways are planned and assigned to warehouse workers, generate the warehouse put-away documents. Fully assigned put-away lines are deleted from the **Put-away Worksheet**.  

> [!NOTE]  
> If the **Use Put-away Worksheet** toggle is not turned on on the location card, warehouse put-away documents are created directly based on posted warehouse receipts. In that case, this step isn't needed.  

### 5: Create a warehouse put-away document

Create a warehouse put-away document in a pull fashion, based on the posted warehouse receipt. Alternatively, create the warehouse put-away document and assign it to a warehouse worker in a push fashion.  

### 6: Register a warehouse put-away

On each line for items that have been put away, partially or fully, fill in the **Quantity** field on the **Warehouse Put-away** page, and then register the warehouse put-away.  

* Warehouse entries are created for locations that require a bin code on all item transactions.
* The warehouse put-away lines are deleted, if they're fully handled.
* The warehouse put-away document remains open until you register the full quantity of the related posted warehouse receipt.
* The **Qty. Put Away** field on posted warehouse receipt order lines is updated.

## Related tasks

The following table describes a sequence of tasks, with links to the articles that describe them.

|**To**|**See**|  
|------------|-------------|  
|Receive items at warehouse locations with a warehouse receipt for fully or partially automated warehouse processing.|[Receive Items](warehouse-how-receive-items.md)|
|Put away items on an order-by-order basis and post the receipt in one activity in basic warehouse configurations.|[Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md)|  
|Put away items received from multiple purchases, sales returns, transfers orders in an advanced warehouse configuration.|[Put Items Away with Warehouse Put-aways](warehouse-how-to-put-items-away-with-warehouse-put-aways.md)|  

## Post non-inventory items

[!INCLUDE [post-non-inventory-items](includes/post-non-inventory-items.md)]

## Related information

[!INCLUDE[footer-include](includes/footer-banner.md)]
