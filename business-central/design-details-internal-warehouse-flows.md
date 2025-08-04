---
title: Design details - flows for production, assembly, and projects
description: Learn about the flow between bins for picking components and putting away end items for assembly, production, or project orders.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.date: 08/12/2024
ms.custom: bap-template
---
# Flows for production, assembly, and projects

Internal flows, such as picking components and putting away end items for assembly, projects, and production orders are similar to inbound or outbound flows. Many of the processes might seem familiar. This article provides information about how to work with internal warehouse flows with various levels of complexity.

## Overview of different configuration options

You can configure warehouse features in various ways. It's important that the options you choose improve your processes without causing overhead. The following tables describe typical configurations for dealing with physical goods for production, projects, and assembly orders.

### Inbound flow (put-away)

|Complexity Level|Description|Settings|Bin Code|Inbound Flow of Production Order|Inbound Flow of Assembly Order|Inbound Flow of Projects|  
|---|----------------|----------|---------|------------------|------------------|------------------|
|No dedicated warehouse activity.|Posting from orders and journals.||Optional. Controlled by the **Bin Code is Mandatory** toggle.|Production Journal -> Output Journal</br><br/> **NOTE**: You can post output using **Production Journal**.|Assembly Order|Put-away isn't applicable for projects|  
|Basic|Order-by-order.|Production Output Whse Handling: Inventory Put-away. </br><br/> **NOTE**: You can still post output directly from the source documents at locations where you activated these settings. |Optional. Controlled by the **Bin Code is Mandatory** toggle.|Production Order -> Inventory Put-away|Assembly Order|Put-away isn't applicable for projects|
|Advanced|Consolidated put-away activities for multiple source documents.|No dedicated settings|Optional. Controlled by the **Bin Code is Mandatory** toggle.|Production Order(s) -> Output Journal|Assembly order(s) ->  internal movements | Put-away isn't applicable for projects|
|Advanced|Same as above plus directed pick/put-away activities|Directed Pick and Put-away (dependent toggles are enabled automatically)|Mandatory|Same as above|Same as above| Put-away isn't applicable for projects|

Some configurations don't let you use dedicated warehouse documents to register put-aways. However, if your location uses bins you can use generic movement documents to move produced or assembled items to warehouse. Learn more at [Moving Items](warehouse-move-items.md).

### Outbound flow (pick)

|Complexity Level|Description|Settings|Bin Code|Outbound Flow of Production Order|Outbound Flow of Assembly Order|Outbound Flow of Projects|  
|---|----------------|----------|---------|------------------|------------------|------------------|
|No dedicated warehouse activity.|Posting from orders and journals.||Optional. Controlled by the **Bin Code is Mandatory** toggle.|Production Journal -> Consumption Journal </br><br/> **NOTE**: You can post consumption using a **Production Journal**.|Assembly Order|Project -> Project Journal|  
|Basic|Order-by-order.|Production, Assembly, Projects: Inventory Pick, Inventory Movement </br><br/> **NOTE**: You can still post consumption directly from the source documents at locations where you activated these settings.|Optional. Controlled by the **Bin Code is Mandatory** toggle.|Production Order -> Inventory Pick|Assembly Order -> Inventory movement</br><br/>The **Inventory Movement** can be used only with bins.|Project -> Inventory Pick|
|Advanced|Consolidated pick activities for multiple source documents.|Production, Assembly, Projects: Warehouse Pick|Optional. Controlled by the Bin Code is Mandatory toggle|Production Order(s) -> Warehouse Pick -> Consumption Journal |Assembly order(s) -> Warehouse Pick| Project(s) -> Warehouse Pick -> Project Journal |
|Advanced|Same as above + Directed pick/put-away activities|Directed Pick and Put-away (dependent toggles are enabled automatically)|Mandatory|Same as above|Same as above| Same as above|

## Warehouses without dedicated warehouse activity

Even if you don't use dedicated warehouse activities, you might want to track things like consumption and production output. The following articles provide information about how to process receipts for source documents.

* [Register Consumption and Output for One Released Production order line](production-how-to-register-consumption-and-output.md)
* [Assemble Items](assembly-how-to-assemble-items.md)
* [Record Consumption or Usage for Projects](projects-how-record-job-usage.md)

## Basic warehouse configuration

### Flows to and from production in a basic warehouse configuration  

The inbound and outbound flows in a basic warehouse configuration involve the following settings on the **Location Card** page for the location:

* For the inbound flow (put-away), in the **Prod. Output Whse. Handling** field, select **Inventory Put-away**.
* For the outbound flow (pick), in the **Prod. Consumption Whse. Handling** field, select **Inventory Pick/Movement**.

Use **Inventory Pick** documents to pick production components in the flow to production. To put away the products you produce, use **Inventory Put-away** documents.

For locations that use bins, inventory movement documents are especially useful for component flushing. To learn more about how component consumption is flushed from To-Production or Open Shop Floor bins, go to [Flushing production components in the warehouse](warehouse-how-to-pick-for-production.md#flushing-production-components-in-a-basic-warehouse-configuration).

   > [!NOTE]
   > Inventory movements are important documents if you're using **Pick + Forward** or **Pick + Backward** flushing methods. Learn more at [Flushing methods](production-how-to-flush-components-according-to-operation-output.md#flushing-methods).

* The **To-Production Bin Code**, **From-Production Bin Code**, and **Open Shop Floor Bin Code** fields on the location or the machine/work center define the default flows to and from production areas.
* Manage the movement of produced items on the **Internal Movement** page without a relation to a production order.

### Flows to and from assembly in a basic warehouse configuration  

The outbound flow in a basic warehouse configuration involves the following settings on the **Location Card** page for the location:

* For the outbound flow (pick), in the **Asm. Consumption Whse. Handling** field, select **Inventory Movement**.

Use **Inventory Movement** documents to pick assembly components in the flow to assembly. Post assembly output and consumption directly from an assembly order.

> [!NOTE]
> **Inventory Pick** and **Inventory Put-away** documents aren't supported for assembly orders.

For locations that use bins:

* Use **Inventory Movement** documents to move assembly components to the assembly area.
* The **To-Assembly Bin Code**, **From-Assembly Bin Code** fields on the location card define default flows to and from assembly areas.
* Manage the movement of assembled items on the **Internal Movement** page, without a relation to an assembly order.

[!INCLUDE [prod_short](includes/prod_short.md)] supports assemble-to-stock and assemble-to-order assembly flows. Learn more at [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md#understanding-assemble-to-order-and-assemble-to-stock). In relation to warehouse management, assemble-to-stock is part of the internal warehouse flow, and assemble-to-order is in the outbound warehouse flow. Learn more at [Handling Assemble-to-Order Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).

### Flows for project management in a basic warehouse configuration

The outbound flow in a basic warehouse configuration involves the following settings on the **Location Card** page for the location:

* For the outbound flow (pick), in the **Project Consumption Whse. Handling** field, select **Inventory Pick**.

Use **Inventory Pick** documents to pick project components in the flow to project management.

For a location that uses bins, the **To-Project Bin Code** field on the location defines the default flows to project management.

## Advanced warehouse configurations  

### Flows to and from production in advanced warehouse configurations

The outbound flow in an advanced warehouse configuration involves the following settings on the **Location Card** page for the location:

* For the outbound flow (pick), in the **Prod. Consumption Whse. Handling** field, select **Warehouse Pick (optional)** or **Warehouse Pick (mandatory)**.

Use the **Warehouse Pick** documents and the **Pick Worksheet** page to pick components for production.

> [!NOTE]
> **Warehouse Put-away** documents aren't supported for production output.

For locations that use bins:

* **Warehouse Movement** documents and the **Movement Worksheet** page are especially useful for component flushing. Learn more at [Flushing production components in the warehouse](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md#flushing-production-components-in-an-advanced-warehouse-configuration).
* The **To-Production Bin Code**, **From-Production Bin Code**, and **Open Shop Floor Bin Code** fields on the location or machine/work center define the default flows to and from production areas. 
* Manage the movement of produced items on the **Movement Worksheet** or **Whse. Internal Put-away** pages, without a relation to a production order.

### Flows to and from assembly in advanced warehouse configurations

The outbound flow in an advanced warehouse configuration involves the following settings on the **Location Card** page for the location:

* For the outbound flow (pick), in the **Asm. Consumption Whse. Handling** field, select **Warehouse Pick (optional)** or **Warehouse Pick (mandatory)**. 

Use **Warehouse Pick** documents and the **Pick Worksheet** page to pick components for assembly.

> [!NOTE]
> **Warehouse Put-away** document isn't supported for assembly orders.

For locations that use bins:

* The **To-Assembly Bin Code** and **From-Assembly Bin Code** fields on the location define the default flows to and from assembly areas.
* Manage the movement of assembly items on the **Movement Worksheet** or **Whse. Internal Put-away** pages, without a relation to an assembly order.

[!INCLUDE [prod_short](includes/prod_short.md)] supports assemble-to-stock and assemble-to-order assembly flows. Learn more at [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md#understanding-assemble-to-order-and-assemble-to-stock). 

Assemble-to-stock is part of the internal warehouse flow, and assemble-to-order is in the outbound warehouse flow. Learn more at [Handling Assemble-to-Order Items in Warehouse Shipments](warehouse-how-ship-items.md#handling-assemble-to-order-items-in-warehouse-shipments).

### Flows to project management in advanced warehouse configurations

The outbound flow in an advanced warehouse configuration involves the following settings on the **Location Card** page for the location:

* For the outbound flow (pick), in the **Project Consumption Whse. Handling** field, select **Warehouse Pick (optional)** or **Warehouse Pick (mandatory)**.

Use **Warehouse Pick** documents and the **Pick Worksheet** page to pick components in the flow to project management.

For locations that use bins, the **To-Projects Bin Code** field on the location defines the default flows to the project area.

## Related information  

[Warehouse Management Overview](design-details-warehouse-management.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
