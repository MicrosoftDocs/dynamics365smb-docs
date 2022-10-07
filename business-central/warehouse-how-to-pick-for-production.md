---
    title: Pick for Production, Assembly, or Jobs in Basic Warehouse
    description: When your warehouse location requires that you process picks but not shipments, use the Inventory Pick page to record that components were picked.
    author: brentholtorf
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/02/2022
    ms.author: bholtorf

---
# Pick for Production, Assembly, or Jobs in Basic Warehouse Configurations

How you put away your pick components for production or assembly orders depends on how your warehouse is set up as a location. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

## Pick for Production in Basic Warehouse Configurations

If a location requires pick processing but not shipment processing, you can use the **Inventory Pick** page. The **Inventory Pick** page lets you organize and record the picking of items that have their flushing method set to **Manual**. When you register an inventory pick, the consumption of the picked components is posted. You can also use an **Inventory Movement** with reference to a source document to assign components with flushing method set to **Manual**, **Pick + Forward**, **Pick + Backward** to production orders.

If production is integrated with warehouse processes through bins or directed put-aways and picks, components are consumed from the bin on the production order line. All required components must be available in that bin. Otherwise, manual or flushed consumption posting is stopped for that component.

> [!NOTE]  
> The following are important differences between inventory picks, inventory movements, and warehouse picks:  
>
> - When you register an inventory pick for an internal operation, such as production, the consumption of the picked components is posted at the same time. When you register an inventory movement or warehouse pick for an internal operation, you only record the physical movement of the required components to a bin in the operation area without posting the consumption.  
> - When you use inventory picks, the **Bin Code** field on a production order component line defines the *take* bin from where components are decreased when posting consumption. When you use inventory movements or warehouse pick, the **Bin Code** field on production order component lines defines the *place* bin in the operation area where the warehouse worker must place the components.  

To pick or move components for source documents, an outbound warehouse request must notify the warehouse area of the need for the component. The outbound warehouse request is created when you do the following:

- Change the status of a production order to Released.
- Create a released production order.  

Flushing methods also affect the flow of components in production. For more information, see [Flush Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md). **Inventory Movement** with references to the source document and **Warehouse pick** can't be used to pick components with *Forward* and *Backward* flushing methods. **Inventory Pick** can't be used to pick components with any flushing method but *Manual*. To handle remaining components, use **Inventory Movement** without reference to a source document. For more information, see [Move Components to an Operation Area in Basic Warehouse Configurations](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

In advanced warehouse configurations where locations require both picks and shipments, you must use the **Warehouse Pick** page to bring components with flushing method set to *Manual*, *Pick + Forward*, *Pick + Backward* to production orders. For more information, see [Pick for Production or Assembly in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).

## To pick components for production and jobs in basic warehouse configurations

In basic warehouse configurations where the location is set up to use picking only, you can pick components for production activities and job planning lines on the **Inventory Pick** page. For more information, see [Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md).

> [!NOTE]
> The ability to pick components for job planning lines was added to [!INCLUDE[d365fin](includes/d365fin_md.md)] in 2022 release wave 2. To start using the capability, an administrator must turn on **Feature Update: Enable inventory and warehouse pick from Jobs** on the **Feature Management** page.
>
>[!INCLUDE[prod_short](includes/prod_short.md)] uses the value in the **Remaining Quantity** field on the job planning line when it creates inventory picks. To use inventory picks for jobs, you must turn on the **Apply Usage Link** toggle on the **Job Card** page for the job. This lets you track usage against your plan. If you don't turn on the toggle, the remaining quantity will stay at **0** and the inventory pick won't be created. For more information, see [To set up job usage tracking](projects-how-setup-jobs.md?tabs=current-experience#to-set-up-job-usage-tracking).

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Picks**, and then choose the related link.  
2. To access the production order components, choose the **Get Source Documents** action, and then select the released production order.  
3. Pick the component, and then record the picking information in the **Qty. to Handle** field.  
4. When the lines are ready for posting, choose the **Post** action. The posting creates the necessary warehouse entries and posts the consumption of the items.  

You can also create an **Inventory Pick** directly from the released production order. Choose the **Create Inventory Put-away/Pick/Movement** action, select the **Create Invt. Pick** check box, and then choose the **OK** button.

As an alternative, use an **Inventory Movement** with reference to the source document to move items between bins. You'll need to register consumption separately. For more information, see [Batch Post Production Consumption](production-how-to-post-consumption.md)

## Pick for Assembly in Basic Warehouse Configurations

Use the following pages to pick for assembly orders:

- The **Inventory Movement** page.
- If the location requires picks but not shipments, use the **Inventory Pick** page to pick, assemble, and ship for sales orders where items must be assembled before they can be shipped. For more information, see [Handling Assemble-to-Order Item with Inventory Picks](warehouse-how-to-pick-for-production.md#handling-assemble-to-order-items-with-inventory-picks).  

In advanced warehouse configurations where locations require both picks and shipments, you must use the **Warehouse Pick** page to bring components to assembly orders. For more information, see [Pick for Production or Assembly in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).

## Handling Assemble-to-Order Items with Inventory Picks

The **Inventory Pick** page is also used to pick and ship for sales where items must be assembled before they can be shipped. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).

Assemble-to-order items to ship aren't considered present in a bin until they're assembled and posted as output to a bin in the assembly area. Therefore, picking these items for shipment follows a special flow. From a bin, warehouse workers take the assembly items to the shipping dock and then post the inventory pick. The posted inventory pick then posts the assembly output, the component consumption, and the sales shipment.

You can set up [!INCLUDE[prod_short](includes/prod_short.md)] to automatically create an inventory movement when the inventory pick for the assembly item is created. To create movements automatically, choose the **Create Movements Automatically** field on the **Assembly Setup** page. For more information, see [Move Components to an Operation Area in Basic Warehousing](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

[!INCLUDE[prod_short](includes/prod_short.md)] creates inventory pick lines for sales items differently, depending on whether none, some, or all of the sales line quantities are assembled to order.

- In sales where you use inventory picks to post inventory shipment, [!INCLUDE[prod_short](includes/prod_short.md)] creates one inventory pick line for each sales order line. If the item is placed in different bins, more than one line will be created. The pick lines are based on the quantity in the **Qty. to Ship** field.
- In sales where the full quantity on the sales order line is assembled-to-order, one inventory pick line is created for the quantity. The value in the Quantity to Assemble field is the same as the value in the **Qty. to Ship** field. The **Assemble to Order** field is selected on the line.

If an assembly output flow is set up for the location, the value in the **Asm.-to-Order Shpt. Bin Code** or **From-Assembly Bin Code** fields, in that order, is inserted in the **Bin Code** field on the inventory pick line.

If no bin code is specified on the sales order line, and no assembly output flow is set up for the location, then the **Bin Code** field on the inventory pick line is empty. The warehouse worker must open the **Bin Contents** page and select the bin where the assembly items are assembled.

When part of the quantity must be assembled first, and another must be picked from inventory, [!INCLUDE[prod_short](includes/prod_short.md)] creates at least two inventory pick lines. One pick line is for the assemble-to-order quantity. The other pick line depends on which bins can fulfill the remaining quantity from inventory. Bin codes on the two lines are filled in different ways as described for the two different sales types respectively. For more information, see the “Combination Scenarios” section in [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).

## Filling the Consumption Bin

This flow chart shows how the **Bin Code** field on production order component lines is filled according to your location setup.

![Bin flow chart.](media/binflow.png "BinFlow")

## See related [Microsoft training](/training/paths/pick-ship-items-business-central/)

## See also

[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
