---
title: About Production Orders
description: Learn about production orders, and how they're used to manage the conversion of purchased materials into manufactured items. 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.form: 99000813, 99000814, 99000815, 99000816, 99000829, 99000830, 99000831, 99000832, 99000833, 99000838, 99000839, 99000867, 99000868, 99000882, 99000897, 99000898, 99000900, 99000912, 99000913, 99000914, 99000917 
ms.date: 02/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# About production orders

Production orders are used to manage the conversion of purchased materials into manufactured items. Production orders route work through various work or machine centers on the shop floor.  

Before they proceed with production, most companies perform supply planning, typically once a week, to calculate how many production orders and purchase orders to execute to fulfill that week’s sales demand. Purchase orders supply the components that are required according to the production BOM to produce the end items.

Production orders are the central components of manufacturing functionality and they contain the following information:  

- Products planned for manufacturing  
- Materials required for the planned production orders  
- Products that have been manufactured  
- Materials that are already selected  
- Products that were manufactured in the past  
- Materials that were used in previous manufacturing operations  

Production orders are the starting points for:  

- Planning future manufacturing  
- Controlling current manufacturing  
- Tracking of finished manufacturing  

## Production order creation  

You can create production orders on an order-by-order basis manually on the **Production Order** page, or generate them from the **Sales Order Planning** or **Order Planning** pages. You can also create multiple orders are created from the **Planning Worksheet** page.  

You create production orders using information from:  

- Items  
- Production BOMs
- Routings  
- Machine centers  
- Work centers  

## Limitations on creating production orders  

Production orders are automatically reserved and tracked to their source when:  

- Created from the [Planning Worksheet](production-how-to-run-mps-and-mrp.md)  
- Created from the [Sales Order Planning](production-how-to-create-production-orders-from-sales-orders.md) page  
- Created from the [Order Planning](production-how-to-plan-for-new-demand.md) page  
- Using the [Replan](production-how-to-replan-refresh-production-orders.md) function on production orders  

For more information, see [Track Relations Between Demand and Supply](production-how-track-demand-supply.md).

Production orders created through other means aren't automatically reserved and tracked.

## Production order status  

The production order status controls how the production order behaves within application. The order's status dictates the form and content of the production. The production orders are displayed in different pages according to their status. You can't change the status of a production order manually. You must use the **Change Status** function in the individual production order or in the **Change Production Order Status** page.  

### Simulated production order  

A simulated production order is unique, based on the following characteristics:  

- As the name implies, it's a simulation you can use for quotes and costing. For example, when the Research and Development department wants to get a cost estimate on a proposed item. A simulated production order serves as an example of a production order.  
- They don't influence the planning of orders. Planning (MPS and MRP) doesn't considers and isn't affected by simulated production orders. Also, a simulated production order can't be used as a template because it disappears when you change its status.  

### Planned production order  

A planned production order is unique because of the following characteristics:  

- You can automatically create a planned production order from a sales order.  
- Planned production orders are like released production orders and provide input to capacity requirements planning by showing the total capacity requirements by work center or machine center.  
- A planned production order represents the best estimate of the future load for the work center or machine center load based on available information. Typically, they're generated from planning, but can also be created manually. Because they're erased during subsequent planning generations, manual creation isn't practical.  
- Their generation in planning results in a suggested "planned order release" that includes quantity, release date, and due date. The planning system logic is based on the replenishment system, reorder policies, and order modifiers that it encounters in the net requirements planning process.  
- To view their effect, look at the load for each work center or machine center on the planned production order's routing.  

### Firm planned production order  

A firm planned production order is unique because of the following characteristics:  

- You can automatically create a firm planned production order from a sales order.  
- A firm planned production order acts as a placeholder in the planning schedule for some future project released to the floor.  
- A firm planned production order can be generated from planning or created manually or from sales orders. They aren't erased during subsequent planning.  
- Their generation in planning results in a suggested "planned order release" that includes: quantity, release date, and due date. The planning system logic is based on the replenishment system, reorder policies, and order modifiers that it encounters in the net requirements planning process.  
- To view their effect, look at the load for each work center or machine center on the firm planned production order's routing.  

### Released production order  

The released production order is unique, based on the following characteristics:  

- You can automatically create a released production order from a sales order.  
- When a production order is released, it doesn't necessarily mean that materials are picked or the project has physically moved to its first operation.  
- In a make-to-order (MTO) environment, it isn't unusual to create a released production order immediately after the entry of the sales order.  
- Actual material consumption and product output can be recorded manually with a released production order. In addition, automatic flushing of consumption and product output only occurs for released production orders.  

### Finished production order  

A finished production order is unique, based on the following characteristics:  

- A finished production order is typically one that is manufactured.  
- Finishing the production order is an important task in completing the costing lifecycle of the item that is being produced. After you finish a production order, you can adjust and reconcile costing.  
- Finished production orders are used for statistical reporting and to support the ability to track back to other orders (sales, production, and purchase, for example). The ability to track back to a finished production order allows you to review the detailed history.  
- Finished production orders can never be changed.  

## Production order execution  

After you create and schedule a production order, it has to be released to the shop floor to be executed. During execution of the order, you record:  

- The materials that were picked or consumed  
- How much time was spent working on the order  
- The quantity of the parent item produced  

You can record this information manually or through automatic reporting. The method dependson the setup in the Flushing Method field on the item and work center.  

### Material consumption  

[!INCLUDE [prod_short](includes/prod_short.md)] offers various options for how to record material consumption. For example, material consumption can be recorded manually, which might be desirable if there are frequent component substitutions or greater than expected scrap.  

Consumption of materials can be processed through the [consumption journal](production-how-to-post-consumption.md), but can also be recorded automatically by [!INCLUDE [prod_short](includes/prod_short.md)], known as automatic reporting (flushing). The Manual, Forward, and Backward reporting methods are available.

Manual consumption reporting uses the consumption journal to specify material picking.  

Forward consumption reporting assumes the expected quantity of all materials for the entire order is consumed at the release of a production order, unless using routing link codes. When you use routing link codes, the material consumed after the start of the operational step is recorded in the output journal. To forward flush the entire production order, you need to do two things:  

- All items in the top-level production BOM need to have forward flushing selected on their respective item card.  
- All routing link codes on the production BOM must be removed.  

Backward consumption reporting records the actual quantity of all material picked or consumed when the status of a production order is changed to *Finished,* unless using routing link codes. When you use routing link codes, the material is consumed after a quantity of the parent item is recorded for the operational step in the output journal.  

When the Production Order is refreshed, the flushing method is copied from the item card. Because the flushing method for each production order component controls how and when the consumption is recorded, it's important to note that you can change flushing method for specific items directly on the production order. For more information, see [Flush Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).

### Production output  

[!INCLUDE [prod_short](includes/prod_short.md)] provides the ability to track how much time is spent working on a production order, in addition to recording the quantity produced. This information can help you more accurately determine the costs of production. Also, manufacturers using a standard costing system might want to record actual information in order to help them develop better standards.  

Output can be processed through the [output journal](production-how-to-post-output-quantity.md), but can also be recorded automatically. [!INCLUDE [prod_short](includes/prod_short.md)] copies the flushing method from the machine center or work center card to the production order routing when refreshing. As with material consumption, there are the Manual, Forward, and Backward reporting methods for output.

The Manual method uses the output journal to specify time consumed and quantity produced.  

The Forward method records the expected output (and time), which is automatically recorded at the release of a production order. Routing link codes aren't a factor in the forward flushing of the output.  

Backward method records the expected output (and time), which is automatically recorded at the finish of a production order. Routing link codes aren't a factor in the back flushing of the output.  

### Posting consumption and output  

You can use any combination of automatic flushing and manually recorded information for both consumption and output. For example, you might want to automatically forward flush components, but still use a consumption journal to record scrap. Similarly, you might want to automatically record output, but use an output journal to record scrap of the parent item or extra time spent on the order.  

Finally, if you enter consumption and output manually, you need to determine the sequence in which you're going to record this information. You can record consumption first and use a shortcut method to enter the information, which is based on expected quantity of output. Or, you can enter output first, using the **Explode Routing** function. You would then record consumption based on actual quantity of output.  

### Production journal  

The [Production Journal](production-how-to-register-consumption-and-output.md) combines the functions of a consumption journal and output journals into one journal, which is accessed directly from the released production order.  

The purpose of a production journal is to provide a single interface for you to register consumption and output from a production order.  

Production journals have a simple view and provide you with the ability to:  

- Easily record output and consumption related to a production order  
- Relate the components to operations  
- Relate actual operation data with the standard estimates on a production order routing and component lines  
- Post and print an overview of registered operation data for a production order  

Production journal do many of the same functions as the consumption and output journals. Dimensions, item tracking, and bin contents are handled in the same way.  

However, production journals differ from the consumption and output journals in the following ways:  

- It's called directly from a released production order line and preset with the relevant data.  
- It allows you to define which types of components to handle based on a flushing method filter on the journal.  
- Quantities and times already posted for the order are displayed at the bottom of the journal as actual entries.  
- Fields where data entry is irrelevant are blank and noneditable.  
- The user can set up the way output quantities are preset in the journal - for example, that the last operation must have zero as Output Quantity.  
- If you happen to exit the journal without posting your changes, a request message is displayed allowing you to stay in the journal.  
- It displays operations and components together in a logical structure that provides an overview of the production process.  

In the production journal, consumption quantities are posted as negative item ledger entries, output quantities are posted as positive ledger entries, and times spent are posted as capacity ledger entries.  

## See also

[Manufacturing](production-manage-manufacturing.md)
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
