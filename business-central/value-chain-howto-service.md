---
title: Sustainability value chain in Service Management
description: Learn how sustainability value chain tracking calculates and posts CO2e for Service Management documents.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: Sustainability, scope 3, emission, carbon, CO2e, value chain, service order, service invoice, service shipment, service credit memo
ms.search.form: Primary_5900, 5902, 5905, 5914, 5933, 5934, 5935, 5936, 5952, 5964, 5966, 5972, 5973, 5975, 5976, 5978, 5979, 6030, 6033, 6034
ms.date: 08/26/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Sustainability value chain in Service Management

Service Management can track the carbon dioxide equivalent (CO2e) for items and resources that you use in service quotes, orders, invoices, and credit memos. The values follow the service line through posting. [!INCLUDE [prod_short](includes/prod_short.md)] also creates sustainability value entries for the posted emissions.

## Prerequisites

Before you add sustainability information to a service document, complete the following setup:

- On the **Sustainability Setup** page, turn on **Enable Value Chain Tracking**. Learn more in [Sustainability value chain setup](value-chain-howto-setup.md).
- Set up a sustainability account with the **Posting** account type. The account must allow direct posting, and it can't be blocked.
- Assign a **Default Sust. Account** to each item or resource that you use on service lines. Ensure that a **CO2e per Unit** value is available. Learn more in [Default data for sustainability](sustainability-howto-default.md).

The sustainability account must track greenhouse gas emissions. You can't use an account that tracks water, waste, or discharges into water on a service line.

## Add CO2e to a service document

1. Open the **Service Quotes**, **Service Orders**, **Service Invoices**, or **Service Credit Memos** page.
2. Create a document, or open the document that you want to change.
3. Open the service lines.
4. In the **Type** field, select **Item** or **Resource**.
5. In the **No.** field, select the item or resource.
6. Review the **Sustainability Account No.** and **Total CO2e** fields.
7. If needed, select a different posting account in the **Sustainability Account No.** field.
8. Enter the quantity for the line.

When you select an item or resource, [!INCLUDE [prod_short](includes/prod_short.md)] copies its default sustainability account and **CO2e per Unit**. Selecting the account also copies its name, category, subcategory, and default dimensions to the line. The **Sustainability Account No.** and **Total CO2e** fields are available only when **Enable Value Chain Tracking** is turned on.

Only lines of the **Item** and **Resource** types can contain sustainability information. Service cost and G/L account lines aren't supported.

## How CO2e is calculated

[!INCLUDE [prod_short](includes/prod_short.md)] uses the following formula for a service line:

**Total CO2e** = **CO2e per Unit** &times; **Qty. per Unit of Measure** &times; **Quantity**

Changing the quantity recalculates **Total CO2e**. You can also change **Total CO2e**. In that case, [!INCLUDE [prod_short](includes/prod_short.md)] recalculates **CO2e per Unit**.

For partial posting, the value entry uses the quantity that you invoice or consume. The **Posted Total CO2e** field on the service order contains the total for invoiced and consumed quantities. Shipping by itself doesn't update this field.

## Post service documents

The posting choice determines whether the CO2e is expected or actual.

| Posting choice | Item line | Resource line |
|----------------|-----------|---------------|
| **Ship** | Creates an expected sustainability value entry. | Doesn't create a sustainability value entry. |
| **Invoice** or **Ship and Invoice** | Creates an actual sustainability value entry. If the item was shipped earlier, invoicing offsets its expected emission. | Creates an actual sustainability value entry. |
| **Ship and Consume** | Creates an actual sustainability value entry. | Creates an actual sustainability value entry. |
| Post a service credit memo | Creates a positive actual sustainability value entry. | Creates a positive actual sustainability value entry. |

A directly posted service invoice follows the **Invoice** behavior. For service orders, invoicing and consumption update **Posted Total CO2e** by the amount that was posted.

Outbound emissions are recorded with a negative sign. Service credit memos use a positive sign. For an item that is marked as a GHG credit, [!INCLUDE [prod_short](includes/prod_short.md)] reverses the normal sign.

If a service line is linked to a project, the sustainability account and CO2e values transfer to the project journal during consumption. This behavior applies to item and resource lines.

Service posting creates **Sustainability Value Entries**, not **Sustainability Ledger Entries**. A line without a sustainability account doesn't create a sustainability value entry.

## Review CO2e and posted information

You can review sustainability information in the following places:

- The **Service Lines** and **Service Quote Lines** pages show **Sustainability Account No.** and **Total CO2e**.
- Service item lines on a service order show the combined **Total CO2e** for their related service lines.
- The **Service Order Statistics** and **Service Statistics** pages show **Total CO2e** and **Posted Total CO2e** on the **Sustainability** FastTab. The FastTab appears when the document has at least one line with a sustainability account.
- Posted service invoice and credit memo lines show **Sustainability Account No.** and **Total CO2e**.
- On a posted service shipment, each service item line shows the combined **Total CO2e** for its related shipment lines.
- The **Service Invoice Statistics** and **Service Credit Memo Statistics** pages show **Total CO2e** on the **Sustainability** FastTab.
- The **Sustainability Value Entries** page shows the expected and actual entries. Filter by the service document number to review a posting.

Standard sustainability reports use sustainability ledger entries. They don't include the Service Management amounts that are stored only in sustainability value entries. This feature also doesn't add CO2e fields to the standard service document report layouts.

## Undo a service shipment or consumption

When you undo service posting, [!INCLUDE [prod_short](includes/prod_short.md)] creates a corrective service shipment line. The line keeps the sustainability account information and uses the opposite **Total CO2e** amount. The combined total on the posted service shipment reflects the correction.

- Undoing consumption creates offsetting sustainability value entries for item and resource lines. It also reduces **Posted Total CO2e** on the service order.
- Undoing an item shipment creates entries that offset the expected emission.
- Undoing a resource shipment doesn't create sustainability value entries because shipping a resource doesn't create an entry.

The standard restrictions for undoing service consumption and shipments still apply. Learn more in [Post service orders and credit memos](service-how-to-post-service-orders.md#undo-posted-consumption).

## Limitations

The following limitations currently apply:

- Service Management value chain tracking supports only CO2e. It doesn't support water or waste.
- Only item and resource service lines are supported.
- A nonrenewable-energy line must have a **Total CO2e** value other than zero before you post it. If a renewable-energy line has a zero value, posting doesn't create a sustainability value entry.
- A resource shipment doesn't create a sustainability value entry until you invoice or consume the resource.
- Standard sustainability reports and standard service document report layouts don't include these service values.

## Related information

- [Sustainability value chain overview](value-chain-howto-overview.md)
- [Sustainability value chain setup](value-chain-howto-setup.md)
- [Default data for sustainability](sustainability-howto-default.md)
- [Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)
- [Service posting](service-service-posting.md)
- [View service statistics](service-service-statistics.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
