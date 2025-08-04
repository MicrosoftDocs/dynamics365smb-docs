---
title: Item availability in Sales Order Agent (preview)
description: Learn about the item availability used by Sales Order Agent and how you can test results on your own.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: article
ms.collection:
  - bap-ai-copilot
ms.date: 04/01/2025
ms.update-cycle: 180-days
ms.custom: bap-template
ms.search.form: 4400, 4410_Primary
---
# Item availability in Sales Order Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

The **Item Availability** page is part of Sales Order Agent for checking item availability during the sales order-taking process. This article provides a detailed overview of how the **Item Availability** page functions, including configuration and field descriptions.

![Screenshot of Item Availability page](media/soa-item-availability-page-clip.svg "Screenshot of Item Availability page")

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]
<!--[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]-->

## Overview

Admins can set up Sales Order Agent to select only available items for sales quotes or orders. Learn more in [Set up Sales Order Agent (preview)](sales-order-agent-setup.md).

When this capability is turned on, Sales Order Agent uses the **Item Availability** page to check an item's availability before adding it to the quote or order. If an item isn't available, reviewers are notified by a **Request Assistance** step in the timeline for the task in the **Task** tab.

![Screenshot of the Sales Order Agent task tab that shows a request-for-assistance step about item availability](media/soa-item-availability.png "Screenshot of the Sales Order Agent task tab that shows a request-for-assistance step about item availability")

As a reviewer, use the **Item Availability** page to verify that items are unavailable. Decide whether to stop the task or let the agent proceed. You can't change items and quantity at this point. If you confirm the step, the agent creates an email to the customer about the unavailable items for your review.

<!--
Here's the general flow:

1. Select **Review** or the **Item Availability** link to open the **Item Availability** page.
1. Verify that the items in question are unavailable. Refer to the next section for details about how the page works.
1. When you're finished reviewing availability, return to the confirmation step in the **Tasks** tab and select **Confirm**.

The agent creates an email about the unavailable items for your review.
-->

## How to check item availability page

Before the agent calculates the availability and prices for requested items, it searches for the customer making the request, retrieves the customer's specific location, and then sets the **Customer No.** and **Location Filter** fields on the **Item Availability** page.

After setting these fields, the agent calculates the availability of each item in the request one at a time. The agent sets the **Date filter** with the customer's requested delivery date, if any, and the **Quantity Filter** to the requested quantity, currently only in the base unit of measure.

As a reviewer, these fields aren't automatically set to the values the agent used. To check availability, set the fields manually based on the customer's request.

For each item, the following fields are calculated:

|Field|Description|
|-|-|
|Requested Quantity Available|Indicates whether the quantity of items requested by the customer, specified by the **Quantity Filter** field, is available. If the **Quantity Filter** is less than or equal to the **Available Quantity (Base UOM)**, the item is available, and the checkbox is selected. If the **Quantity Filter** field is greater than, the item isn't available, and the checkbox is cleared. |
|Available Quantity (Base UOM)|Shows the projected available balance of item quantity on the date specified by the **Date Filter**. Calculated by adding the current item inventory in ledger entries to the items in scheduled receipts (inbound transactions like purchase and transfer orders). Then, subtract the items in gross requirements (outbound transactions like sales, service, and production orders). You can select the value to display the totals for item ledger entries and each receipt type. Then, you can drill down to view the source of these totals.|
|Unit of Measure Code|Shows the item's sales unit of measure code. If the field is empty, the base unit of measure is used.|
|Unit of Measure|The item's sales or base unit of measure description. Learn more in [Set Up Units of Measure](inventory-how-setup-units-of-measure.md).|
|Available Quantity|Shows the available quantity in base unit of measure (UOM) recalculated to the sales unit of measure.|
|Unit Price Including Discount|Shows the items' price including discount calculated for a specified customer on a specified date. Learn more in [Record special sales prices and discounts](sales-how-record-sales-price-discount-payment-agreements.md).|
|Availability Level|Shows the level of the item's availability, such as ***Available** or **Out of Stock**. The value is calculated based on the **Available Quantity (Base UOM)** compared to the **Safety Stock Quantity** specified on the item or storekeeping unit card. Learn more about safety stock in [Design Details: Balancing supply and demand](design-details-balancing-demand-and-supply.md).|

## Related information

[Sales Order Agent overview](sales-order-agent.md)  
[Set up Sales Order Agent](sales-order-agent-setup.md)  
[Process sales quotes and orders with Sales Order Agent](sales-order-agent-process.md)  
[FAQ for Sales Order Agent](faqs-sales-order-taker-agent.md)  
[Configure Copilot and agent capabilities](enable-ai.md)  
