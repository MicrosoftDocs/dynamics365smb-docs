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

The **Item Availability** page is part of the Sales Order Agent extension. The Sales Order Agent uses this page to check item availability if configured. Before adding items requested by customers, it checks availability on the requested date, in the requested quantity, and at the customer's location. It also shows the specific price and discount for the customer. As a reviewer, you can also use the **Item Availability** page. If the Sales Order Agent finds unavailable items, a request for assistance step is added to the flow. Select the **Item Availability** link to open the page and review and adjust items.

## How it works

Before calculating the availability and prices for requested items, the agent searches for the customer making the request, retrieves the customer's specific location, and then sets the **Customer No.** and **Location Filter** fields on the **Item Availability** page.

> [!IMPORTANT]
> **Customer No.** and **Location Filter** values set by the agent aren't shown in the Sales Order Agent timeline. In order to test the agent results, these fields must be calculated and set manually.

After setting these fields, the agent sets the **Date Filter** and **Quantity Filter** for each item in the request. The Date Filter is validated with the requested date, and the Quantity Filter is filled with the requested quantity of the item (currently only in Base Unit of Measure).
For each item from the search result, the following fields are calculated:

|Field|Description|
|-|-|
|Available Quantity (Base UOM)|This is the sum of inventory, inbound and outbound transactions. It shows the projected inventory by adding the inbound transactions (Assembly Orders, Released Production Orders, Transfer Order, and Purchase Order lines), to current inventory, and then subtracting all outbound transactions (Production Order component, Assembly component, Sales Order and Transfer Order shipment lines). Clicking this number will list the totals for each type of Receipt. Clicking on any of those numbers will show the filtered set that was found.|
|Unit Of Measure Code|This is a Sales Unit of Measure code of the item. If Sales Unit Of Measure is empty, Base Unit of measure is used.|
|Unit Of Measure|This is the item's Sales or Base Unit of Measure description.|
|Available Quantity|This is the available quantity in base UOM recalculated to sales unit of measure.|
|Unit Price Including Discount|This is the price including discount calculated for specified customer on a specified date.|
|Availability Level|his is the level of item's availability, which is calculated based on available quantity in base UOM compared to the safety stock specified on the Item or Stockkeeping Unit card.|

There are several hidden fields that can be useful for some user scenarios but are not considered by the agent.

## Related information

[Sales order agent overview](sales-order-agent.md)  
[Set up the Sales Order Agent](sales-order-agent-setup.md)  
[FAQ for Sales Order Agent](faqs-sales-order-taker-agent.md)  
[Configure Copilot and AI capabilities](enable-ai.md)  
