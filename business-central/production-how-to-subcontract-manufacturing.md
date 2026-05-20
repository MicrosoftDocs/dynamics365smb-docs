---
title: Subcontracting overview
description: Get an overview of subcontracting capabilities for manufacturing, including subcontractor prices, component posting, transfer orders, and location management.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.keywords: subcontracting, manufacturing, production, vendor, prices
ms.search.form: 99000886,
ms.date: 05/18/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Subcontracting overview

Subcontracting selected operations to a vendor is common in many manufacturing companies. Subcontracting can be a rare occurrence or an integral part of all production processes.

<!--[!INCLUDE[prod_short](includes/prod_short.md)] provides basic subcontracting support through subcontract work centers. For extended capabilities — such as the subcontracting worksheet, subcontractor price management, component posting, transfer orders, item charges, and location management — install the **Subcontracting** app from [Microsoft AppSource](https://go.microsoft.com/fwlink/?linkid=2311183). Learn more about installing apps at [Install and uninstall extensions](ui-extensions-install-uninstall.md#install). -->

## Basic subcontracting tools

The following tools are available without the Subcontracting app:

- **Work centers with an assigned vendor**. You can set up a work center that is associated with a vendor (subcontractor). You specify this subcontract work center on routing operations, and the cost of the operation can be designated at the routing or work center level. Learn more in [Set up subcontracting](subcontract-setup.md).
- **Work center cost based on units or time**. You can specify whether costs for the work center are based on production time or a flat charge per unit. Although subcontractors commonly use a flat charge per unit, [!INCLUDE[prod_short](includes/prod_short.md)] can handle both options.

## Extended capabilities in the Subcontracting app

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

The following sections outline the extra capabilities that the Subcontracting app offers.

### Subcontracting worksheet

Use the subcontracting worksheet to find production orders with material ready to send to a subcontractor and automatically create purchase orders for subcontract operations. Learn more in [Use the subcontracting worksheet](subcontract-worksheet.md).

### Order subcontracting from production orders

Create subcontracting purchase orders directly from released production order routings. You don't need to use worksheets or other journals, which reduces the risk of errors when you verify purchase invoices. Learn more in [Order subcontracting from production orders](subcontract-order.md).

### Subcontractor prices

Store subcontractor prices and view all item prices at a glance. You can use filters to search for specific prices. Learn more in [Manage subcontractor prices](subcontract-prices.md).

### Component management

Subcontracting types control how components are handled — whether they're purchased by the subcontractor, already stocked at their location, or transferred from your warehouse. [!INCLUDE [prod_short](includes/prod_short.md)] automatically manages locations and supports transfer orders for moving materials. Learn more in [Manage components in subcontracting](subcontract-components.md).

### Item charges

Assign additional costs such as transport, packaging, or other incidental costs directly to subcontracting operations. Item charges enable precise cost allocation to production orders. Learn more in [Assign item charges to subcontracting receipts](subcontract-item-charges.md).

### Location management

[!INCLUDE [prod_short](includes/prod_short.md)] automatically assigns and manages locations in subcontracting, from component provision to transfer to the subcontractor. Learn more in [Set up locations for subcontracting](subcontract-location-management.md).

<!--### Purchase provisions

Create subcontracting from purchase orders through production orders and complete the subcontracting process. Default settings support automatic posting processes to save time and reduce costs. Learn more in [Set up purchase provisions for subcontracting](subcontract-purchase-provisions.md). -->

## Related information

[Set up subcontracting](subcontract-setup.md)  
[Order subcontracting from production orders](subcontract-order.md)  
[Use the subcontracting worksheet](subcontract-worksheet.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
