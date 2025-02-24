---
title: Item availabity (preview)
description: Learn about the item availability used by the Sales Order agent.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: conceptual
ms.collection:
  - bap-ai-copilot
ms.date: 02/21/2025
ms.custom: bap-template
---
# Item availability (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

The **Item Availability** page is part of the Sales Order Agent extension. The Sales Order Agent uses this page to check item availability if configured. Before adding items requested by customers, it checks availability on the requested date, in the requested quantity, and at the customer's location. It also shows the specific price and discount for the customer.

As a reviewer, you can also use the **Item Availability** page. If the Sales Order Agent finds unavailable items, a request for assistance step is added to the flow. Select the **Item Availability** link to open the page and review and adjust items.

Learn how to configure the agent in [Set up Sales Order Agent (preview)](sales-order-agent-setup.md).

## How it works

Before calculating the availability and prices for requested items, the agent searches for the customer making the request, retrieves the customer's specific location, and then sets the **Customer No.** and **Location Filter** fields on the **Item Availability** page.

> [!IMPORTANT]
> **Customer No.** and **Location Filter** values set by the agent aren't shown in the Sales Order Agent timeline or on the **Item Availability** page when you open it from the timeline. To test the agent results, set these fields manually.

After setting these fields, the agent starts to check the availability of each item in the request one at a time. The agent sets the **Date Filter** with the customer's requested delivery data. If no data was requested, the default is used. It sets the **Quantity Filter** to the requested quantity, currently only in base unit of measure. For each item from the search result, the following fields are calculated:

|Field|Description|
|-|-|
Available quantity (base UOM)|The sum of inventory, inbound, and outbound transactions. It shows the projected inventory by adding the inbound transactions (assembly orders, released production orders, transfer order, and purchase order lines) to current inventory, and then subtracting all outbound transactions (production order component, assembly component, sales order, and transfer order shipment lines). Selecting this number will list the totals for each type of receipt. Selecting any of those numbers will show the filtered set that was found.|
|Unit of measure code|The item's sales unit of measure code. If the sales unit of measure is empty, the base unit of measure is used.|
|Unit of measure|The item's sales or base unit of measure description.|
|Available quantity|The available quantity in base UOM recalculated to the sales unit of measure.|
|Unit price including discount|The price including discount calculated for a specified customer on a specified date.|
|Availability level|The level of the item's availability, which is calculated based on available quantity in base UOM compared to the safety stock specified on the item or stockkeeping unit card.|

There are several hidden fields that can be useful for some user scenarios but are not considered by the agent.

## Related information

[Sales order agent overview](sales-order-agent.md)  
[Set up the Sales Order Agent](sales-order-agent-setup.md)  
[FAQ for Sales Order Agent](faqs-sales-order-taker-agent.md)  
[Configure Copilot and AI capabilities](enable-ai.md)  
