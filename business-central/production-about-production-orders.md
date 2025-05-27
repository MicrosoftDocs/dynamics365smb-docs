---
title: About production orders
description: Learn about production orders, and how to use them to manage the conversion of purchased materials into manufactured items. 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 99000813, 99000814, 99000815, 99000816, 99000829, 99000830, 99000831, 99000832, 99000833, 99000838, 99000839, 99000867, 99000868, 99000882, 99000897, 99000898, 99000900, 99000912, 99000913, 99000914, 99000917 
ms.date: 03/21/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# About production orders

Use production orders to manage the conversion of purchased materials into manufactured items. Production orders route work through various work or machine centers on the shop floor.  

Before they start production, most companies do supply planning, typically once a week, to calculate how many production orders and purchase orders they need fulfill sales demand. Purchase orders supply the required components according to the end item's bill of materials (BOM).

Production orders are central components in manufacturing, and contain the following information:  

- Products planned for manufacturing  
- Materials required for the planned production orders  
- Materials that are already selected  
- Products that were manufactured in the past  
- Materials that were used in previous manufacturing operations  

Production orders are the starting points for:  

- Planning future manufacturing  
- Controlling current manufacturing  
- Tracking of finished manufacturing  

## Production order creation  

You can create production orders on an order-by-order basis manually on the **Production Order** page, or generate them from the **Sales Order Planning** or **Order Planning** pages. You can also create multiple orders from the **Planning Worksheet** page.  

You create production orders using information from:  

- Items  
- Production BOMs
- Routings  
- Machine centers  
- Work centers  

## Reserving and tracking production orders to their source

Production orders are automatically reserved and tracked to their source when you create them from:  

- The [Planning Worksheet](production-how-to-run-mps-and-mrp.md) page.
- The [Sales Order Planning](production-how-to-create-production-orders-from-sales-orders.md) page.
- The [Order Planning](production-how-to-plan-for-new-demand.md) page.  
- The [Replan](production-how-to-replan-refresh-production-orders.md) action on production orders.  

To learn more, go to [Track Relations Between Demand and Supply](production-how-track-demand-supply.md).

If you create production orders by other means, they aren't automatically reserved and tracked.

## Production order status  

A production order can have one of the following statuses:

- Simulated
- Planned
- Firm Planned
- Released
- Finished

The status of a production order controls what you can do with it, and the form and content of the production. Production orders display on different pages according to their status. You can't change the status of a production order manually. To change the status of an order, use the **Change Status** action on the production order or use the **Change Production Order Status** page to change the status of one or orders in one go.

The **Change Status** action is available for the following types of orders:

- Simulated production orders
- Planned production orders
- Firm planned production orders
- Released production orders

> [!TIP]
> A confirmation dialog with additional questions displays for each order individually. If there are multiple orders with partial output or consumption, confirm each one separately.

If the status of orders can't change, they're skipped. The **Error Message** page shows the orders that were skipped and the reasons.  

### Simulated production order  

A simulated production order is unique because of the following characteristics:  

- It's a simulation you can use for quotes and costing. For example, when the Research and Development department wants a cost estimate for a proposed item. A simulated production order serves as an example of a production order.  
- They don't influence the planning of orders. MPS and MRP don't consider and aren't affected by simulated production orders. Also, you can't use a simulated production order as a template because it disappears when you change its status.  

### Planned production order  

A planned production order is unique because of the following characteristics:  

- You can automatically create a planned production order from a sales order.  
- Planned production orders are like released production orders and provide input to planning by showing the total capacity requirements by work center or machine center.  
- A planned production order represents the best estimate of the future load for the work center or machine center load based on available information. Typically, they're generated from planning, but you can also manually create them. However, they're erased the next time you run planning so it isn't practical to create them manually.  
- Their generation in planning results in a suggested "planned order release" that includes the quantity, release date, and due date. The planning system logic is based on the replenishment system, reorder policies, and order modifiers that it encounters in the net requirement planning process.  
- The load for each work center or machine center on the planned production order's routing shows their effect.  

### Firm planned production order  

A firm planned production order is unique because of the following characteristics:  

- You can automatically create a firm planned production order from a sales order.  
- A firm planned production order acts as a placeholder in the planning schedule for a future project released to the floor.  
- You can generate them during planning, create them manually, or create them from sales orders. They aren't erased during subsequent planning.  
- Their generation in planning results in a suggested "planned order release" that includes the quantity, release date, and due date. The planning system logic is based on the replenishment system, reorder policies, and order modifiers that it encounters in the net requirement planning process.  
- The load for each work center or machine center on the firm planned production order's routing show their effect.  

### Released production order  

The released production order is unique, based on the following characteristics:  

- You can automatically create a released production order from a sales order.  
- A released production order doesn't necessarily mean that materials are picked or the project moves to its first operation.  
- People typically create a released production order immediately after they enter the sales order in make-to-order (MTO) environments.  
- You can use a released production order to record the actual material consumption and product output. In addition, automatic flushing of consumption and product output only occur for released production orders.  

### Finished production order  

A finished production order is unique, based on the following characteristics:  

- A finished production order is typically one that is manufactured.  
- Finishing the production order is an important task in completing the costing lifecycle of the produced item. After you finish a production order, you can adjust and reconcile costing.  
- Finished production orders are used for reporting and to support the ability to track back to other orders (for example, sales, production, and purchases). The ability to track back to a finished production order allows you to review the detailed history.  
- You can't change finished production orders.  

#### Reopen a finished production order to make corrections

After you complete a production order and set its status to **Finished**, you might discover a mistake. For example, you might find that consumption is missing or the item tracking information is incorrect. To make sure that your inventory and cost transactions are correct, use the **Reopen** action on the **Finished Production Orders** page to make adjustments. However, to protect your data there are a few restrictions:

- You can only reopen an order one time.
- You can't reopen an order that has no output and cost was written off to an adjustment account.

## Production order execution  

After you create and schedule a production order, you must release it to the shop floor so that work can start. While you work on an order, you record:  

- The materials that were picked or consumed.  
- The time spent working on the order.
- The quantity of the item produced.

You can record this information manually or through automatic reporting. The method depends on the selection in the **Flushing Method** field on the item and work center.  

### Material consumption  

[!INCLUDE [prod_short](includes/prod_short.md)] offers options for how to record material consumption. For example, you can record material consumption manually, which can be useful if you often substitute components or generate more scrap than you expected.  

Consumption of materials can be processed through the [consumption journal](production-how-to-post-consumption.md), or [!INCLUDE [prod_short](includes/prod_short.md)] can record it automatically, which is known as automatic reporting (flushing). The **Manual**, **Forward**, and **Backward** reporting methods are available.

Manual consumption reporting uses consumption journals to specify material picking.  

Forward consumption reporting assumes the expected quantity of all materials for the entire order is consumed at the release of a production order, unless you use routing link codes. When you use routing link codes, the material consumed after the start of the operational step is recorded in the output journal. To forward flush the entire production order, you need to do two things:  

- All items in the top-level production BOM need to have forward flushing selected on their respective item card.  
- All routing link codes on the production BOM must be removed.  

Backward consumption reporting records the actual quantity of all material picked or consumed when the status of a production order is changed to *Finished,* unless using routing link codes. When you use routing link codes, the material is consumed after a quantity of the parent item is recorded for the operational step in the output journal.  

When you refresh the production order, the flushing method is copied from the item card. The flushing method for each production order component controls how and when you record consumption. Therefore, it's important to note that you can change flushing method for specific items directly on the production order. To learn more, go to [Flush Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).

### Production output  

You can track the time spent working on a production order and the quantity produced. This information can help you determine the costs of production. Also, manufacturers who use a standard costing system might want to record actual information in order to help them develop better standards.  

Output can be processed through [output journals](production-how-to-post-output-quantity.md), but can also be recorded automatically. [!INCLUDE [prod_short](includes/prod_short.md)] copies the flushing method from the machine center or work center card to the production order routing when refreshing. As with material consumption, there are **Manual**, **Forward**, and **Backward** reporting methods for output.

The Manual method uses the output journal to specify time consumed and quantity produced.  

The Forward method records the expected output (and time), which is automatically recorded at the release of a production order. Routing link codes aren't a factor in the forward flushing of the output.  

Backward method records the expected output (and time), which is automatically recorded at the finish of a production order. Routing link codes aren't a factor in the back flushing of the output.  

### Posting consumption and output  

You can use any combination of automatic flushing and manually recorded information for both consumption and output. For example, you might want to automatically forward flush components, but still use a consumption journal to record scrap. Similarly, you might want to automatically record output, but use an output journal to record scrap of the parent item or extra time spent on the order.  

Finally, if you enter consumption and output manually, you need to determine the sequence in which you're going to record this information. You can record consumption first and use a shortcut method to enter the information, which is based on expected quantity of output. Or, you can enter output first, using the **Explode Routing** action. You would then record consumption based on actual quantity of output.  

### Production journals  

The [Production Journal](production-how-to-register-consumption-and-output.md) combines the functions of a consumption journal and output journals into one journal, which is accessed directly from the released production order.  

The purpose of a production journal is to provide a single interface for you to register consumption and output from a production order.  

Production journals have a simple view and provide you with the ability to:  

- Easily record output and consumption related to a production order  
- Relate the components to operations  
- Relate actual operation data with the standard estimates on a production order routing and component lines  
- Post and print an overview of registered operation data for a production order  

Production journals do many of the same things as consumption and output journals. Dimensions, item tracking, and bin contents are handled in the same way.  

However, production journals differ from the consumption and output journals in the following ways:  

- You open them directly from a released production order line and they're preset with the relevant data.
- They let you define which types of components to handle based on a flushing method filter on the journal.  
- Quantities and times already posted for the order display at the bottom of the journal as actual entries.  
- Fields where data entry is irrelevant are blank and noneditable.  
- You can specify how output quantities are preset in the journal. For example, that the last operation must have zero as the output quantity.  
- A confirmation message displays if you exit a journal without posting your changes.  
- They display operations and components together in a structure that provides an overview of the production process.  

In the production journal, consumption quantities are posted as negative item ledger entries, output quantities are posted as positive ledger entries, and times spent are posted as capacity ledger entries.  

## Related information

[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
