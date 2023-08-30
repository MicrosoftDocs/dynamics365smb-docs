---
title: About Production Orders
description: Learn about production orders, and how they are used to manage the conversion of purchased materials into manufactured items. 
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 99000813, 99000814, 99000815, 99000816, 99000829, 99000830, 99000831, 99000832, 99000833, 99000838, 99000839, 99000867, 99000868, 99000882, 99000897, 99000898, 99000900, 99000912, 99000913, 99000914, 99000917 
ms.date: 06/22/2021
ms.author: bholtorf

---
# About Production Orders

Production orders are used to manage the conversion of purchased materials into manufactured items. Production orders route work through various work or machine centers on the shop floor.  

Before proceeding with production, most companies perform supply planning, typically once a week, to calculate how many production orders and purchase orders to execute to fulfill that week’s sales demand. Purchase orders supply the components that are required according to the production BOM to produce the end items.

Production orders are the central components of application's manufacturing functionality and they contain the following information:  

- Products planned for manufacturing  
- Materials required for the planned production orders  
- Products that have just been manufactured  
- Materials that have already been selected  
- Products that have been manufactured in the past  
- Materials that were used in previous manufacturing operations  

Production orders are the starting points for:  

- Planning future manufacturing  
- Controlling current manufacturing  
- Tracking of finished manufacturing  

## Production Order Creation  
Production orders can be created on an order-by-order basis manually from the **Production Order** page, or generated from the **Sales Order Planning** or **Order Planning** pages. Multiple orders are created from the **Planning Worksheet** page.  

Production orders are created using information from:  

- Items  
- Production BOMs
- Routings  
- Machine centers  
- Work centers  

## Limitations on Production Order Creation  
Production orders are automatically reserved and tracked to their source when:  

- Created from the **[Planning Worksheet](production-how-to-run-mps-and-mrp.md)**.  
- Created from the **[Sales Order Planning](production-how-to-create-production-orders-from-sales-orders.md)** page  
- Created from the **[Order Planning](production-how-to-plan-for-new-demand.md)** page  
- Using the **[Replan](production-how-to-replan-refresh-production-orders.md)** function on production orders  

For more information, see [Track Relations Between Demand and Supply](production-how-track-demand-supply.md).

Production orders created through other means are not automatically reserved and tracked.   

## Production Order Status  
The production order status controls how the production order behaves within application. The form and content of the production are dictated by the order's status. The production orders are displayed in different pages according to their status. You cannot change the status of a production order manually; you must use the **Change Status** function in the individual production order or in the **Change Production Order Status** window.  

### Simulated Production Order  
The Simulated Production Order is unique based on the following characteristics:  

- As its name implies, it is a simulation and its main purpose is for quoting and costing - such as when the Research and Development department wants to get a cost estimate on a proposed item. A simulated production order serves as an example of a production order.  
- It does not influence the planning of orders. Planning (MPS and MRP) neither considers nor is affected by simulated production orders. Also, a simulated production order cannot be used as a template because it disappears when you change its status.  

### Planned Production Order  
The Planned Production Order is unique because of the following characteristics:  

- You can automatically create a planned production order from a sales order.  
- Planned production orders are like released production orders and provide input to capacity requirements planning by showing the total capacity requirements by work center or machine center.  
- A planned production order represents the best estimate of the future load for the work center or machine center load based on available information. Typically, they are generated from planning, but can also be created manually. Because they are erased during subsequent planning generations, manual creation is not practical.  
- Their generation in planning results in a suggested "planned order release" that includes quantity, release date, and due date. The planning system logic is based on the replenishment system, reorder policies, and order modifiers that it encounters in the net requirements planning process.  
- To view their impact, look at the load for each work center or machine center on the planned production order's routing.  

### Firm Planned Production Order  
The Firm Planned Production Order is unique because of the following characteristics:  

- You can automatically create a firm planned production order from a sales order.  
- A firm planned production order acts as a placeholder in the planning schedule for some future job released to the floor.  
- A firm planned production order can be generated from planning or created manually or from sales orders. They are not erased during subsequent planning.  
- Their generation in planning results in a suggested "planned order release" that includes: quantity, release date, and due date. The planning system logic is based on the replenishment system, reorder policies, and order modifiers that it encounters in the net requirements planning process.  
- To view their impact, look at the load for each work center or machine center on the firm planned production order's routing.  

### Released Production Order  
The Released Production Order is unique based on the following characteristics:  

- You can automatically create a released production order from a sales order.  
- When a production order has been released, it does not necessarily mean that materials have been picked or the job has physically moved to its first operation.  
- In a MTO (Make-to-Order) environment, it is not unusual to create a released production order immediately after the entry of the sales order.  
- Actual material consumption and product output can be recorded manually with a released production order. In addition, automatic flushing of consumption and product output only occurs for released production orders.  

### Finished Production Order  
The Finished Production Order is unique based on the following characteristics:  

- A finished production order is typically one that has been manufactured.  
- Finishing the production order is an important task in completing the costing lifecycle of the item that is being produced. By finishing a production order, costing can be adjusted and reconciled.  
- Finished production orders are used for statistical reporting and to support the ability to track back to other orders (sales, production, and purchase, for example). The ability to track back to a finished production order allows you to review the detailed history.  
- Finished production orders can never be changed.  

## Production Order Execution  
Once a production order has been created and scheduled, it has to be released to the shop floor to be executed. During execution of the order, you record:  

- Materials picked or consumed  
- How much time was spent working on the order  
- Quantity of the parent item produced  

This information can be recorded manually or through automatic reporting, according to the setup in the Flushing Method field of item and work center.  

### Material Consumption  
The application offers a variety of options for how a manufacturing company might want to record material consumption. For example, material consumption may be recorded manually, which might be desirable if there are frequent component substitutions or greater than expected scrap.  

Consumption of materials may be processed through the [consumption journal](production-how-to-post-consumption.md), but also may be recorded automatically by application, known as automatic reporting (flushing). The reporting methods are:  

- Manual  
- Forward  
- Backward  

Manual consumption reporting uses the consumption journal to specify material picking.  

Forward consumption reporting assumes the expected quantity of all materials for the entire order is consumed at the release of a production order, unless using routing link codes. When using routing link codes, the material consumed after the start of the operational step is recorded in the Output Journal. To forward flush the entire production order, you need to do two things:  

- All items in the top-level production BOM need to have forward flushing selected on their respective item card.  
- All routing link codes on the production BOM must be removed.  

Backward consumption reporting records the actual quantity of all material picked or consumed when the status of a production order is changed to *Finished,* unless using routing link codes. When using routing link codes, the material is consumed after a quantity of the parent item is recorded for the operational step in the Output Journal.  

When the Production Order is refreshed, the flushing method is copied from the item card. Because the flushing method for each production order component controls how and when the consumption is recorded, it is important to note that you can change flushing method for specific items directly on the Production Order. 

For more information, see [Flush Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md)

### Production Output  
The application provides you with the capability to track how much time is spent working on a production order, in addition to recording the quantity produced. This information can help you more accurately determine the costs of production. Also, manufacturers using a standard costing system may want to record actual information in order to help them develop better standards.  

Output may be processed through the [output journal](production-how-to-post-output-quantity.md), but also may be recorded automatically by application. The application copies the flushing method from the machine center or work center card to the production order routing when refreshing. As with material consumption, there are three reporting methods for output:  

- Manual  
- Forward  
- Backward  

Manual method uses the Output Journal to specify time consumed and quantity produced.  

Forward method records the expected output (and time), which is automatically recorded at the release of a Production Order. Routing link codes are not a factor in the forward flushing of the output.  

Backward method records the expected output (and time), which is automatically recorded at the finish of a Production Order. Routing link codes are not a factor in the back flushing of the output.  

### Posting Consumption and Output  
You can use any combination of automatic flushing and manually recorded information for both consumption and output. For example, you may want to automatically forward flush components, but still use the Consumption Journal to record scrap. Similarly, you may want to automatically record output, but use the Output Journal to record scrap of the parent item or additional time spent on the order.  

Finally, if you enter consumption and output manually, you need to determine the sequence in which you are going to record this information. You can record consumption first and use a shortcut method to enter the information, which is based on expected quantity of output. Or, you can enter output first, using the **Explode Routing** function. You would then record consumption based on actual quantity of output.  

### Production Journal  
The [Production Journal](production-how-to-register-consumption-and-output.md) combines the functions of the Consumption Journal and Output Journals into one journal, which is accessed directly from the Released Production Order.  

The purpose of the Production Journal is to provide a single interface for you to register consumption and output from a Production Order.  

The Production Journal has a simple view and provides you with the ability to:  

- Easily record output and consumption related to a Production Order  
- Relate the components to operations  
- Relate actual operation data with the standard estimates on the Production Order routing and component lines  
- Post and print an overview of registered operation data for the Production Order  

The Production Journal performs many of the same functions as the Consumption and Output journals. Dimensions, Item Tracking, and Bin Contents are handled in the same way as on the Consumption and Output journals.  

However, the Production Journal differs from the Consumption and Output journals in the following ways:  

- It is called directly from a released production order line and preset with the relevant data.  
- It allows you to define which types of components to handle based on a flushing method filter on the journal.  
- Quantities and times already posted for the order are displayed at the bottom of the journal as actual entries.  
- Fields where data entry is irrelevant are blank and non-editable.  
- The user can set up the way output quantities are preset in the journal - for example, that the last operation must have zero as Output Quantity.  
- If you happen to exit the journal without posting your changes, a request message is displayed allowing you to stay in the journal.  
- It displays operations and components together in a logical structure that provides an overview of the production process.  

In the production journal, consumption quantities are posted as negative item ledger entries, output quantities are posted as positive ledger entries, and times spent are posted as capacity ledger entries.  

## See Also
[Manufacturing](production-manage-manufacturing.md)
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
