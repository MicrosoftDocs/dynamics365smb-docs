---
    title: Pick Items | Microsoft Docs
    description: The warehouse activity of picking items before they are shipped or consumed is performed in different ways, depending on how warehouse management features are configured. The [setup](../configure-warehouse-processes.md) complexity can rank from no warehouse features, through basic warehouse configurations for order-by-order handling in one or more activities only, to advanced configurations where all warehouse activities must be performed in a directed workflow.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Pick Items
The warehouse activity of picking items before they are shipped or consumed is performed in different ways, depending on how warehouse management features are configured. The complexity can rank from no warehouse features, through basic warehouse configurations for order-by-order handling in one or more activities only, to advanced configurations where all warehouse activities must be performed in a directed workflow. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

If you decide to organize and record your picking activity with warehouse documents, you place a check mark in the **Require Pick** field on the location card. This indicates that when you have items that need to be picked for an outbound source document you want the picking of those items to be controlled by the system. An outbound source document can be a sales order, a purchase return order, an outbound transfer order, a service order, or a production order whose components should be picked.

> [!NOTE]
> Even though the setting is called **Require Pick**, you can still post shipments directly from the source business document at location where you select this check box.

If your location is set up to require pick processing but not shipment processing, you use the **Inventory Pick** page to organize the picking information, print the picking information, enter the result of the pick, and post the picking information, which in turn posts the shipment of the items. In the case of picking components for a production order, the posting of the pick also posts the consumption.

If your location is set up to require both pick and shipment processing, so that you have placed check marks in both the **Require Pick** and **Require Shipment** field on the location card, you use the **Warehouse Pick** page to handle the pick. The warehouse pick functions similarly to the inventory pick, except that instead of posting the picking information, you register the pick. This registering process does not post the shipment, but merely makes the items available for shipment. As a warehouse manager, you can use a pick worksheets to organize pick information before creating the individual warehouse pick instructions.

The following table describes a sequence of tasks, with links to the topics that describe them.   

|**To**|**See**|
|------------|-------------|  
|Post the shipment of items directly in the outbound order document because no warehouse features exist. (Works the same for sales orders, outbound transfer orders, and return shipments.)|[Ship Items](warehouse-how-ship-items.md)|  
|Pick items order by order and post the shipment in the same activity, in a basic warehouse configuration.|[Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md)|
|Pick items for multiple orders in an advanced warehouse configuration.|[Pick Items with Warehouse Picks](warehouse-how-to-pick-items-for-warehouse-shipment.md)|  
|Pick components for production or assembly in a basic warehouse configuration.|[Pick for Production or Assembly in Basic Warehouse Configurations](warehouse-how-to-pick-for-production.md)|
|Pick components for production or assembly in an advanced warehouse configuration.|[Pick for Production or Assembly in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md)|  
|Plan optimized pick instructions for a number of shipments rather than have warehouse workers act directly on posted shipments.|[Plan Picks in Worksheets](warehouse-how-to-plan-picks-in-worksheets.md)|  
|Pick items technically for a special purpose, such as a production unit in need of extra components, in such a way that the items do not technically leave the warehouse.|[Pick and Put Away Without a Source Document](warehouse-how-to-create-put-aways-from-internal-put-aways.md)|
|Understand how to automatically pick items according to their expiration date, for example perishable goods.|[Picking By FEFO](warehouse-picking-by-fefo.md)|
|Split a pick line into multiple lines, for example because there are not enough items to take from in the designated bin.|[Split Warehouse Activity Lines](warehouse-how-to-split-warehouse-activity-lines.md)|
|Get immediate access to picks that are assigned to you as a warehouse worker.|[Find Your Warehouse Assignments](warehouse-how-to-find-your-warehouse-assignments.md)|  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
