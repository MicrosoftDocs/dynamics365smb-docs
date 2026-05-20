---
title: Set up purchase provisions for subcontracting
description: Learn how to create and post purchase provisions with linked production orders and transfer orders for subcontracting operations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, purchase provisions, production order, BOM
ms.search.form: 99000886,
ms.date: 05/20/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Set up purchase provisions for subcontracting

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

Subcontracting outsources individual production steps or manufacturing work to external vendors. For example, you might outsource milling work, cutting, or surface treatments. Purchase provisions involve processing individual components by an external service provider into a finished product. With the purchase order, you invoice a service from the vendor. The purchase order links to the corresponding production order.

After completion, the product returns to your warehouse. You can set up when transfers, receipts, and issues are posted. You can create, edit, and view the production orders and transfer orders required for posting the provision from the purchase order. You can specify the required components for a specific order or use components from existing production BOMs.

## Create a purchase order with a production order

The following steps describe how to create a purchase provision with a linked production order. Depending on your setup and whether you have existing BOMs, you create the order and assign the necessary BOM components using a production order. When you use the **Transfer** subcontracting type, you create the transfer order. You can post inventory changes in the purchase order card or use warehouse functions.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Create a new purchase order and fill in the relevant fields. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

   > [!NOTE]
   > The **Location Code** for subcontracting is maintained on the vendor card.

3. On the lines, select the item to be procured.
4. In the **Quantity** field, specify how many finished produced items should return.
5. In the **Direct Unit Cost** field, specify the price of the service. A price might already be preset. Learn more in [Set up subcontractor prices](subcontract-prices.md).
6. Choose the **Create Production Order** action.

   Depending on the flushing method you selected in the **Subcontracting Setup**, consumption is posted with shipment posting of the subcontracting service using the production order, and the receipt of the item produced by the supplier in the warehouse. [!INCLUDE [prod_short](includes/prod_short.md)] creates the details in the background through the creation of the production order.

<!-- 7. The provision starts automatically and guides you through the configuration of BOMs and routings. Depending on your configuration in the **Subcontracting Setup**, [!INCLUDE [prod_short](includes/prod_short.md)] displays various steps or automatically processes them. Learn more in [Set up purchase provisions and provision wizard](subcontract-setup-configurator.md). -->

8. To transfer the provision components with the **Transfer** subcontracting type, choose the **Create Transfer Order for Subcontracting** action.

   [!INCLUDE [prod_short](includes/prod_short.md)] transfers the required BOM component lines to a transfer order. The **Transfer-from Code** and **Transfer-to Code** fields are filled based on your setup. If an open transfer order exists for the vendor's location code, [!INCLUDE [prod_short](includes/prod_short.md)] adds the required lines to it.

To view information about the production orders and transfer orders linked to the purchase order, choose the **Production** action on the **Lines** FastTab. Learn more about transfers in [Transfer inventory between locations](inventory-how-transfer-between-locations.md).

## Synchronize changes between purchase and production orders

Because the production order is created from the purchase order, [!INCLUDE [prod_short](includes/prod_short.md)] keeps the two documents in sync when you change key fields on the purchase line. This synchronization applies only to purchase lines that haven't been partially received.

### Date synchronization

When you change the **Expected Receipt Date** on the purchase line, [!INCLUDE [prod_short](includes/prod_short.md)] automatically updates the **Due Date** on the linked production order to match. The production order's ending dates are recalculated accordingly. 

### Quantity synchronization

When you change the **Quantity** or **Unit of Measure Code** on the purchase line, [!INCLUDE [prod_short](includes/prod_short.md)] automatically updates the linked production order header, the production order line, and recalculates the quantities on the production order components. 

> [!NOTE]
> Both date and quantity synchronization work in one direction only, from the purchase order to the production order. If you change the **Due Date** or **Quantity** directly on the production order, the purchase line isn't updated. To keep the documents aligned, make changes on the purchase line.

## Post purchase provisions

The following sections describe how to post purchase provisions.

### Transfer BOM components

The components transferred to a transfer order are posted with the warehouse functionalities of the specified location codes, depending on your setup.

### Consume provided BOM components

The consumption method depends on the flushing method:

- **Forward or Backward** - BOM components assigned with the **Forward** or **Backward** flushing method are automatically posted with the entry type **Consumption** through the created production order from the vendor's location when you post the **Qty. to Receive**.

  > [!NOTE]
  > Items with the **Purchase with Service** subcontracting type must first be posted in the purchase order with **Qty. to Receive**.

- **Manual** - BOM components assigned with the **Manual** flushing method must be posted separately after receipt of the produced item. To post manually:

  1. Open the production order linked to the purchase line.
  2. Choose the **Production Journal** action.
  3. Post the journal.

### Receive the produced item

You post the receipt of the produced item in the purchase order.

1. On the purchase order, in the **Qty. to Receive** field, specify the quantity.
2. Choose the **Post** action, and then choose **Receive**.

[!INCLUDE [prod_short](includes/prod_short.md)] creates an item ledger entry with the entry type **Output** with a reference to the linked production order. If you work with different bins in your location, you can put away the inventory to the target bin code with bin transfers.

### Post the invoice

Post the invoice as you would for other purchase invoices for received goods. The posted line amount is transferred to the production order for valuation of the produced items and supplemented by the value of the consumed items. After you post the invoice, change the status of the production order to **Finished**. Learn more in [Work with production orders](production-about-production-orders.md).

## Related information

<!-- [Set up purchase provisions and provision wizard](subcontract-setup-configurator.md)   -->
[Transfer inventory between locations](inventory-how-transfer-between-locations.md)  
[Work with production orders](production-about-production-orders.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]