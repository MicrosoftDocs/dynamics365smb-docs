---
    title: How to Pick Items with Inventory Picks | Microsoft Docs
    description: If a location is set up to require pick processing but not shipment processing, you use the inventory pick documents to record and post picking and shipping information for your source documents.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Handle Assemble-to-Order Items in Inventory Picks
Handling Assemble-to-Order Items in Inventory Picks
The Inventory Pick window is also used to pick and ship for sales where items must be assembled before they can be shipped. For more information, see How to: Sell Items Assembled to Order.

Items to be shipped are not physically present in a bin until they are assembled and posted as output to a bin in the assembly area. This means that picking assemble-to-order items for shipment follows a special flow. From a bin, warehouse workers take the assembly items to the shipping dock and then post the inventory pick. The posted inventory pick then posts the assembly output, the component consumption, and the sales shipment.

You can set up Microsoft Dynamics NAV to automatically create an inventory movement when the inventory pick for the assembly item is created. To enable this, you must select the Create Movements Automatically field in the Assembly Setup window. For more information, see How to: Move Components to an Operation Area in Basic Warehouse Configurations.

Inventory pick lines for sales items are created in different ways depending on whether none, some, or all of the sales line quantities are assembled to order.

In regular sales where you use inventory picks to post shipment of inventory quantities, one inventory pick line, or several if the item is placed in different bins, is created for each sales order line. This pick line is based on the quantity in the Qty. to Ship field.

In assemble-to-order sales where the full quantity on the sales order line is assembled to order, one inventory pick line is created for that quantity. This means that the value in the Quantity to Assemble field is the same as the value in the Qty. to Ship field. The Assemble to Order field is selected on the line.

If an assembly output flow is set up for the location, then the value in the Asm.-to-Order Shpt. Bin Code field or the value in the From-Assembly Bin Code field, in that order, is inserted in the Bin Code field on the inventory pick line.

If no bin code is specified on the sales order line, and no assembly output flow is set up for the location, then the Bin Code field on the inventory pick line is empty. The warehouse worker must open the Bin Contents window and select the bin where the assembly items are assembled.

In combination scenarios, where a part of the quantity must first be assembled and another must be picked from inventory, a minimum of two inventory pick lines are created. One pick line is for the assemble-to-order quantity. The other pick line depends on which bins can fulfill the remaining quantity from inventory. Bin codes on the two lines are filled in different ways as described for the two different sales types respectively. For more information, see the “Combination Scenarios” section in Understanding Assemble to Order and Assemble to Stock.
