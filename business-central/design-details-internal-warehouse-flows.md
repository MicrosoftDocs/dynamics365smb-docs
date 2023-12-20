---
title: Design Details - Flows for Production, Assembly, and Jobs
description: Learn about the flow between bins for picking components and putting away end items for assembly, production, or job orders.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 12/16/2022
ms.custom: bap-template
---
# Flows for Production, Assembly, and Jobs

Internal flows, such as picking components and putting away end items for assembly, jobs, and production orders are similar to inbound or outbound flows. So, many of the processes might seen familiar. This article provides information about how to work with internal warehouse flows with various levels of complexity.

## Overview of different configuration options

You can configure warehouse features in various ways. It's important that the options you choose improve your processes without causing overhead. The following tables describe typical configurations for dealing with physical goods for production, jobs, and assembly orders.

### Inbound flow (put-away)

|Complexity Level|Description|Settings|Bin Code|Inbound Flow of Production Order|Inbound Flow of Assembly Order|Inbound Flow of Jobs|  
|---|----------------|----------|---------|------------------|------------------|------------------|
|No dedicated warehouse activity.|Posting from orders and journals.||Optional. Controlled by the **Bin Code is Mandatory** toggle.|Production Journal -> Output Journal</br><br/> **NOTE**: You can post output using **Production Journal**.|Assembly Order|Put-away is not applicable for Jobs|  
|Basic|Order-by-order.|Require Put-away. </br><br/> **NOTE**: Although the setting is called **Require Put-away**, you can still post output from the source documents at locations where you select this checkbox. |Optional. Controlled by the **Bin Code is Mandatory** toggle.|Production Order -> Inventory Put-away|Assembly Order|Put-away is not applicable for Jobs|
|Advanced|Consolidated put-away activities for multiple source documents.|Require Receipt + Require Put-away|Optional. Controlled by the **Bin Code is Mandatory** toggle.|Production Order(s) -> Output Journal|Assembly order(s) ->  internal movements | Put-away is not applicable for Jobs|
|Advanced|Same as above + Directed pick/put-away activities|Directed Pick and Put-away (dependent toggles will be enabled automatically)|Mandatory|Same as above.|Same as above.| Put-away is not applicable for Jobs|

Some configurations don't allow you use dedicated warehouse documents to register put-aways. However, if your location uses bins you can use generic movement documents to move produced or assembled items to warehouse. Learn more at [Move Items Internally in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md).

### Outbound flow (pick)

|Complexity Level|Description|Settings|Bin Code|Outbound Flow of Production Order|Outbound Flow of Assembly Order|Outbound Flow of Jobs|  
|---|----------------|----------|---------|------------------|------------------|------------------|
|No dedicated warehouse activity.|Posting from orders and journals.||Optional. Controlled by the **Bin Code is Mandatory** toggle.|Production Journal -> Consumption Journal </br><br/> **NOTE**: You can post consumption using a **Production Journal**.|Assembly Order|Job -> Job Journal|  
|Basic|Order-by-order.|Require Pick. </br><br/> **NOTE**: Although the setting is called **Require Pick**, you can still post output from the source documents at locations where you select this checkbox. <!-- ToDo Test prod output-->|Optional. Controlled by the **Bin Code is Mandatory** toggle.|Production Order -> Inventory Pick|Assembly Order -> Inventory movement</br><br/>The **Inventory Movement** can be used only with bins.|Job -> Inventory Pick|
|Advanced|Consolidated pick activities for multiple source documents.|Require Shipment + Require Pick|Optional. Controlled by the Bin Code is Mandatory toggle|Production Order(s) -> Warehouse Pick -> Consumption Journal |Assembly order(s) -> Warehouse Pick| Job(s) -> Warehouse Pick -> Job  Journal |
|Advanced|Same as above + Directed pick/put-away activities|Directed Pick and Put-away (dependent toggles will be enabled automatically)|Mandatory|Same as above.|Same as above.| Directed pick and Put-away is not supported for Jobs|

Similar to the inbound flow, some configurations don't allow you use dedicated warehouse documents to register put-aways. If your location uses bins, you can use generic movement documents to move produced or assembled items. Learn more at [Moving Items](warehouse-move-items.md).

## Warehouses without dedicated warehouse activity

Even if you don't have dedicated warehouse activities, you'll probably still want to keep track of things like consumption and production output. The following articles provide information about how to process receipts for source documents.

* [Register Consumption and Output for One Released Production order line](production-how-to-register-consumption-and-output.md)
* [Assemble Items](assembly-how-to-assemble-items.md)
* [Record Consumption or Usage for Jobs](projects-how-record-job-usage.md)

## Basic warehouse configuration

The inbound and outbound flows in a basic warehouse configuration involve the following settings on the **Location Card** page for the location:

* For the inbound flow (put-away), turn on the **Require Put-away** toggle, but turn off the **Require Receipt** toggle.
* For the outbound flow (pick), turn on the **Require Pick** toggle, but turn off the **Require Shipment** toggle.

### Flows to and from production in a basic warehouse configuration  

Use **Inventory Pick** documents to pick production components in the flow to production. To put away the products you produce, use **Inventory Put-away** documents.

For locations that use bins, inventory movement documents are especially useful for component flushing. To learn more about how component consumption is flushed from To-Production or Open Shop Floor bins, go to [Flushing production components in the warehouse](warehouse-how-to-pick-for-production.md#flushing-production-components-in-a-basic-warehouse-configuration).

   > [!NOTE]
   > Inventory movements are important documents if you're using **Pick + Forward** or **Pick + Backward** flushing methods. Learn more at [Flushing methods](production-how-to-flush-components-according-to-operation-output.md#flushing-methods).

* The **To-Production Bin Code**, **From-Production Bin Code**, and **Open Shop Floor Bin Code** fields on the location or the machine/work center define the default flows to and from production areas.
* Manage the movement of produced items on the **Internal Movement** page without a relation to a production order.

### Flows to and from assembly in a basic warehouse configuration  

Post assembly output and consumption directly from an assembly order.

> [!NOTE]
> **Inventory Pick** and **Inventory Put-away** documents aren't supported for assembly orders.

For locations that use bins:

* Use **Inventory Movement** documents to move assembly components to the assembly area.
* The **To-Assembly Bin Code**, **From-Assembly Bin Code** fields on the location card define default flows to and from assembly areas.
* Manage the movement of assembled items on the **Internal Movement** page, without a relation to an assembly order.

[!INCLUDE [prod_short](includes/prod_short.md)] supports assemble-to-stock and assemble-to-order assembly flows. Learn more at [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md#understanding-assemble-to-order-and-assemble-to-stock). In relation to warehouse management, assemble-to-stock is part of the internal warehouse flow, and assemble-to-order is in the outbound warehouse flow. Learn more at [Handling Assemble-to-Order Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).

### Flows for project management in a basic warehouse configuration

Use **Inventory Pick** documents to pick job components in the flow to project management.

For a location that uses bins, the **To-Job Bin Code** field on the location defines the default flows to project management.

## Advanced warehouse configurations  

The inbound and outbound flows in an advanced warehouse configuration involve the following settings on the **Location Card** page for the location:

* For the inbound flow (put-away), turn on the **Require Receipt** and **Require Put-away** toggles.
* For the outbound flow (pick), turn on the **Require Ship** and **Require Receipt** toggles.

### Flows to and from production in advanced warehouse configurations

Use the **Warehouse Pick** documents and the **Pick Worksheet** page to pick components for production.

For locations that use bins:

* **Warehouse Movement** documents and the **Movement Worksheet** page are especially useful for component flushing. Learn more at [Flushing production components in the warehouse](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md#flushing-production-components-in-an-advanced-warehouse-configuration).
* The **To-Production Bin Code**, **From-Production Bin Code**, and **Open Shop Floor Bin Code** fields on the location or machine/work center define the default flows to and from production areas. 
* Manage the movement of produced items on the **Movement Worksheet** or **Whse. Internal Put-away** pages, without a relation to a production order.

### Flows to and from assembly in advanced warehouse configurations

Use **Warehouse Pick** documents and the **Pick Worksheet** page to pick components for assembly.

For locations that use bins:

* The **To-Assembly Bin Code** and **From-Assembly Bin Code** fields on the location define the default flows to and from assembly areas.
* Manage the movement of assembly items on the **Movement Worksheet** or **Whse. Internal Put-away** pages, without a relation to an assembly order.

[!INCLUDE [prod_short](includes/prod_short.md)] supports assemble-to-stock and assemble-to-order assembly flows. Learn more at [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md#understanding-assemble-to-order-and-assemble-to-stock). 

Assemble-to-stock is part of the internal warehouse flow, and assemble-to-order is in the outbound warehouse flow. Learn more at [Handling Assemble-to-Order Items in Warehouse Shipments](warehouse-how-ship-items.md#handling-assemble-to-order-items-in-warehouse-shipments).

### Flows to project management in advanced warehouse configurations

Use **Warehouse Pick** documents and the **Pick Worksheet** page to pick components in the flow to project management.

For locations that use bins, the **To-Jobs Bin Code** field on the location defines the default flows to the project area.

## See Also  

[Warehouse Management Overview](design-details-warehouse-management.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
