---
    title: Walkthrough - Selling, Assembling, and Shipping Kits | Microsoft Docs
    description: To support just-in-time inventory and the ability to customize products to customer requests, assembly orders can be automatically created and linked as soon as the sales order line is created. The link between the sales demand and the assembly supply enables sales order processors to customize the assembly item and promise delivery dates according to component availability. In addition, assembly consumption and output are posted automatically with the shipment of the linked sales order.
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
# Walkthrough: Selling, Assembling, and Shipping Kits

**Note**: This walkthrough must be performed on a demonstration company with the **Full Evaluation - Complete Sample Data** option, which is available in the Sandbox environment. For more information, see [Creating a Sandbox Environment](across-how-create-sandbox-environment.md).

To support just-in-time inventory and the ability to customize products to customer requests, assembly orders can be automatically created and linked as soon as the sales order line is created. The link between the sales demand and the assembly supply enables sales order processors to customize the assembly item and promise delivery dates according to component availability. In addition, assembly consumption and output are posted automatically with the shipment of the linked sales order.  

Special functionality exists to govern the shipping of assemble-to-order quantities, both in basic and in advanced warehouse configurations. When workers in charge of assembly finish assembling parts or all of the assemble-to-order quantity, they record it in the **Qty. to Ship** field on the warehouse shipment line, in advanced configurations, and then choose **Post Shipment**. The result is that the corresponding assembly output is posted, including the related component consumption, and a sales shipment for the quantity is posted for the linked sales order. This walkthrough illustrates the advanced warehouse process.  

In basic warehouse configurations, when an assemble-to-order quantity is ready to be shipped, the warehouse worker in charge posts an inventory pick for the sales order lines. This creates an inventory movement for the components, posts the assembly output, and the sales order shipment. For more information, see [Handling Assemble-to-Order Items in Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).  

## About This Walkthrough  
This walkthrough demonstrates the following tasks:  

### Setting up Assembly Items  
Assembly items are characterized by their replenishment system and the assembly BOM. The item’s assembly policy can be either assemble-to-order (ATO) or assemble-to-stock (ATS). This section covers the following tasks:  

-   Setting the appropriate replenishment system and assembly policy on a new assembly item card.  
-   Creating an assembly BOM that lists the assembly components and the resource that go into the assembly item.  

### Selling Customized Assembly Items  
[!INCLUDE[d365fin](includes/d365fin_md.md)] provides the flexibility to enter both an inventory quantity and an assemble-to-order quantity on one sales order line. This section covers the following tasks:  

-   Creating a pure ATO sales order line where the full quantity is unavailable and must be assembled before shipment.  
-   Customizing ATO items.  
-   Recalculating the unit price of a customized assembly item.  
-   Creating a mixed sales order line where parts of the sales quantity is provided from inventory and the remaining part must be assembled before shipment.  
-   Understanding ATO availability warnings.  

### Planning for Assembly Items  
Assembly demand and supply are handled by the planning system, just like for purchase, transfer, and production. This section covers the following tasks:  

-   Running a regenerative plan for items with sales demand for assembled supply.  
-   Generating an assembly order to fulfill a sales line quantity by the demanded shipment date.  

### Assembling Items  
Assembly orders function in a similar way as production orders, expect the consumption and output is recorded and posted directly from the order. When the items are assembled to inventory, the assembly worker has full access to all header and line fields. When the items are assembled to an order where the quantity and date are promised to the customer, then certain fields on the assembly order are not editable. In that case, the assembly posting is performed from the warehouse shipment for the linked sales order. This section covers the following tasks.  

-   Recording and posting assembly consumption and output to inventory.  
-   Accessing a warehouse shipment line from an ATO assembly order to record assembly work.  
-   Accessing an ATO assembly order from a warehouse shipment line to review the automatically entered data.  

### Shipping Assembly Items, from Stock and Assembled to Order  
Special functionality exists to govern the shipping of assemble-to-order quantities. This section covers the following tasks:  

-   Creating a warehouse pick for inventory assembly items and for assembly components to be assembled before shipment.  
-   Registering warehouse picks for assembly components and then for assembly items.  
-   Accessing an assembly order from a warehouse shipment to review picked or consumed components.  
-   Shipping assemble-to-order quantities.  
-   Shipping inventory assembly items.  

## Roles  
This walkthrough demonstrates tasks that are performed by the following user roles:  

-   Sales Order Processor  
-   Planner  
-   Assembly Worker  
-   Picker  
-   Shipping Responsible  

## Prerequisites  
Before you can perform the tasks in the walkthrough, you must do the following:  

-   Install [!INCLUDE[d365fin](includes/d365fin_md.md)].  
-   Make yourself a warehouse employee at WHITE location by following these steps:  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.  
2.  Choose the **User ID** field, and select your own user account on the **Users** page.  
3.  In the **Location Code** field, enter WHITE.  
4.  Select the **Default** field.  

Prepare WHITE location for assembly processing by following these steps:  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
2.  Open the location card for WHITE location.  
3.  On the **Bins** FastTab, enter **W-10-0001** in the **To-Assembly Bin Code** field.  

    By entering this non-pick bin code, all assembly order lines are ready to receive their components in the bin.  

4.  In the **From-Assembly Bin Code** field, enter **W-01-0001**.  

    By entering this pick bin code, finished assembly items will be output to the bin.  

Remove the default lead time for internal processes by following these steps:  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manufacturing Setup**, and then choose the related link.  
2.  On the **Manufacturing Setup** page, on the **Planning** FastTab, remove the value in the **Default Safety Lead Time** field.  

Create inventory for assembly components by following [Prepare Sample Data](walkthrough-selling-assembling-and-shipping-kits.md#prepare-sample-data).  

## Story  
On January 23, Susan, the sales order processor takes an order from The Device Shop for three units of Kit B, which is an ATO item. All three units are customized and must contain the strong graphics card and an extra RAM block. The disc drives are upgraded to DWD because the CD drives are unavailable. Susan knows that the units can be assembled immediately, so she leaves the suggested shipment date of January 23.  

At the same time, the customer orders fifteen units of Kit A with a special request that five units be customized to contain the strong graphics card. Although Kit A is typically an assemble-to-stock item, the order processor combines the sales line quantities to sell ten units from stock and assemble five customized units to the order. The ten units of Kit A are unavailable and must first be supplied to inventory by an assembly order according to the item’s assembly policy. Susan learns from the assembly department that Kit A units cannot be completed in the current week. She sets the shipment date of the second sales order line, for the mixed ATO and inventory quantity, to January 27 and informs the customer that the 15 units of Kit A will be shipped four days later than the three units of Kit B. To signal to the shipping department that this sales order requires assembly processing, Susan creates the warehouse shipment document from the sales order.  

Eduardo, the planner, runs the planning worksheet and generates an assembly order for ten standard units of Kit A with an internal due date of January 27.  

Sammy, who is responsible for shipping, gets three warehouse shipment lines for the sales order: One line for the three pure ATO units, one line for the five ATO units on the mixed sales order line, and one line for the ten ATS units on the mixed sale order line. He creates a warehouse pick document for all the assembly components that are needed to assemble the total of eight ATO units on the warehouse shipment document.  

John, the picker, retrieves components for all the ATO quantities on the warehouse shipment document and brings them to the assembly area. He enters the quantity to handle and registers the warehouse pick.  

Linda assembles the three ATO units of Kit B. The components are already picked, and she does not record output and consumption quantities or post the order, because both of these actions are performed automatically through the related warehouse shipment lines.  

Sammy records the assembled quantity on the warehouse shipment line and posts the shipment of the three units of Kit B. The first line on the sales order is updated as shipped. The linked assembly order remains open until the sales order is fully invoiced. The two warehouse shipment lines, one ATO and one ATS, for Kit A with due dates on January 27 remain open.  

On January 27, Linda processes two assembly orders for Kit A. The first order is the ATO order for five units, which she processes differently than the ATO order for Kit B that she processed on January 23. On this order, she is authorized to access the warehouse shipment line herself to record the completed assembly work. The needed components are ready in the assembly department, as they were picked together with components for Kit B.  

The second assembly order is the ATS order for ten units that were created by the planning system. On this ATS order, Linda performs all involved actions from the assembly order. She creates a warehouse pick document for the assembly components that are needed to assemble the ten units. When the PCs are assembled, Linda posts the assembly order and thereby signals that the items are available in inventory and can be picked for shipment.  

Sammy creates a warehouse pick document for any quantities that remain before the warehouse shipment can be posted. A pick document is created for the ten units of Kit A that have just finished. The components needed to assemble the five units of Kit A to order where picked on January 23.  

John brings the ten units of Kit A from the warehouse to the specified shipping area, records the quantity to handle, and then registers the pick.  

Sammy packs the ten ATS units with the five ATO units that Linda assembled earlier in the day. He fills in the quantity to ship on both lines and then posts the last shipment for The Device Shop. The related assembly order for five units of Kit A is automatically posted. The second line on the sales order is updated as shipped. Two linked assembly order remains open until the sales order is invoiced and closed.  

When the sales order is later posted as fully invoiced, the sales order and the linked assembly orders are removed.  

## Prepare Sample Data  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Whse. Item Journals**, and then choose the related link.  
2.  Choose the **Batch Name** field, and then select the default journal.  
3.  Create positive inventory adjustments at WHITE location on the work date, January 23, by entering the following information.  

    |**Item No.**|**Zone Code**|**Bin Code**|**Quantity**|  
    |-----------------------------------|---------------------------------------|--------------------------------------|------------------------------------|  
    |80001|PICK|W-01-0001|20|  
    |80005|PICK|W-01-0001|20|  
    |80011|PICK|W-01-0001|20|  
    |80014|PICK|W-01-0001|20|  
    |80203|PICK|W-01-0001|20|  
    |80209|PICK|W-01-0001|20|  

4.  Choose the **Register** action, and then choose the **Yes** button.  

    Next, synchronize the new warehouse entries with inventory.  

5.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Journals**, and then choose the related link. The **Item Journal** page opens.  
6.  Choose the **Calculate Whse. Adjustment** action.  
7.  On the **Calculate Whse. Adjustment** page, choose the **OK** button.  
8.  On the **Item Journal** page, choose the **Post** action, and then choose the **Yes** button.  

### Creating the Assembly Items  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.  
2.  Choose the **New** action.  
3.  Create the first assembly item based on the following information.  

    |Field|Value|  
    |---------------------------------|-----------|  
    |**Description**|Kit A – Basic PC|  
    |**Base Unit of Measure**|PCS|  
    |**Item Category Code**|Misc.|  
    |**Replenishment System**|Assembly|  
    |**Assembly Policy**|Assemble-to-Stock|  
    |**Reordering Policy**|Lot-for-Lot|  

    > [!NOTE]  
    >  Kit A is typically supplied by assembly to stock and therefore has a reordering policy to make it part of general supply planning.  

4.  Choose the **Assembly** action, and then choose **Assembly BOM**.  
5.  Define an assembly BOM for Kit A with the following information.  

    |**Type**|**No.**|**Quantity per**|  
    |-------------------------------|------------------------------|---------------------------------------|  
    |Item|80001|1|  
    |Item|80011|1|  
    |Item|80209|1|  
    |Resource|Linda|1|  

6.  Create the second assembly item based on the following information.  

    |Field|Value|  
    |---------------------------------|-----------|  
    |**Description**|Kit B – Pro PC|  
    |**Base Unit of Measure**|PCS|  
    |**Item Category Code**|Misc.|  
    |**Replenishment System**|Assembly|  
    |**Assembly Policy**|Assemble-to-Order|  

    > [!NOTE]  
    >  Kit B is usually supplied by assembly to order and therefore does not have a reordering policy, because it should not be part of general supply planning.  

7.  Choose the **Assembly** action, and then choose **Assembly BOM**.  
8.  Define an assembly BOM for Kit B with the following information.  

    |**Type**|**No.**|**Quantity per**|  
    |-------------------------------|------------------------------|---------------------------------------|  
    |Item|80005|1|  
    |Item|80014|1|  
    |Item|80210|1|  
    |Resource|Linda|1|  

### Selling the Assembly Items  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2.  Choose the **New** action.  
3.  Create two sales order lines for customer 62000, The Device Shop, on the work date with the following information.  

    |**Type**|**Description**|**Quantity**|Qty. to Assemble to Order|Shipment Date|  
    |--------------|---------------------|------------------|-------------------------------|-------------------|  
    |Item|Kit B – Pro PC|3|3|January 23|  
    |Item|Kit A – Basic PC|15|5|January 27|  

    > [!NOTE]  
    >  The following availability issue exists for the sales order line for Kit B:  
    >   
    >  -   Assembly component 80210 is not available. This means that the three specified units of Kit B cannot be assembled, indicated by **0** in the **Able to Assemble** field on the **Assembly Availability** page.  
    >   
    >  The following availability issue exists for the sales order line for Kit A:  
    >   
    >  -   The ten units of Kit A are not available. This indicates to the planning system that the quantity must be assembled to inventory.  

    Next, customize the sales order.  

4.  Select the sales order line for three units of Kit B.  
5.  On the **Lines** FastTab, choose **Line**, choose **Assemble to Order**, and then choose **Assemble-to-Order Lines**.  
6.  On the **Assemble-to-Order Lines** page, on the assembly order line for item 80014, enter **2** in the **Quantity per** field.  
7.  On the assembly order line for item 80210, choose the **No.** field, and then select item 80209 instead.  
8.  Create a new assembly order line with the following information.  

    |Type|No.|Quantity per|  
    |----------|---------|------------------|  
    |Item|80203|1|  

9. Close the **Assemble-to-Order Lines** page.  

    Next, update the unit price of Kit B according to the customization that you just performed. Notice the current value in the **Unit Price Excl. VAT** field.  

10. On the **Lines** FastTab, choose **Line**, choose **Assemble to Order**, and then choose **Roll Up Price**.  
11. Choose the **Yes** button. Notice the increased value in the **Unit Price Excl. VAT** field.  
12. Select the sales order line for 15 units of Kit A.  
13. On the **Lines** FastTab, choose **Line**, choose **Assemble to Order**, and then choose **Assemble-to-Order Lines**.  
14. On the **Assemble-to-Order Lines** page, create a new assembly order line with the following information.  

    |Type|No.|Quantity per|  
    |----------|---------|------------------|  
    |Item|80203|1|  

     Next, change the shipment date of the second sales order line according to the assembly schedule.  

15. On the sales order line for 15 units of Kit A, enter **01-27-2014** in the **Shipment Date** field.  
16. Choose the **Release** action.  
17. Choose the **Create Whse. Shipment** action.  
18. Close the sales order.  

### Planning for the Unavailable ATS Items  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Planning Worksheet**, and then choose the related link.  
2.  Choose the **Calculate Regenerative Plan** action.  
3.  On the **Calculate Plan** page, set the following filters.  

    |Starting Date|Ending Date|No.|  
    |-------------------|-----------------|---------|  
    |01-23-2014|01-27-2014|Kit A – Basic PC|  

4.  Choose the **OK** button.  

    A new planning line is created for the needed assembly order of ten units, due on January 27. It needs no changes, so now you can create the order.  

5.  Choose the **Carry Out Action Message** action.  
6.  On the **Carry Out Action Msg.** page, choose the **Assembly Order** field, and then select **Make Assembly Orders**.  
7.  Choose the **OK** button.  

### Assembling and Shipping the First ATO Quantity  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipment**, and then choose the related link.  

    > [!NOTE]  
    >  In this section, the person who is responsible for shipping is in charge of recording the completed ATO assembly work on the warehouse shipment line. This workflow may occur in environments where the assembly work is performed by the person who is responsible for shipping or by assembly workers in the shipping area.  
    >   
    >  In this section, actions on the assembly order are performed indirectly from the warehouse shipment line. For more information about how to process an assembly order directly, see the “Assemble Items to Inventory” section in this walkthrough.  

2.  Open the most recent warehouse shipment that is created at WHITE location.  

    Notice the three warehouse shipment lines: One line for the ATO quantity of Kit B, due on January 23. One line for the ATO quantity of Kit A, due on January 27. One line for the inventory quantity of Kit A, due on January 27.  

    The **Assemble to Order** field specifies the assembly method.

    Next, create a pick document for all the ATO assembly components that are needed on the warehouse shipment.  

3.  Choose the **Create Pick** action, and then choose the **OK** button.  

    Next, perform the picker’s task.  

4.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Picks**, and then choose the related link.  
5.  Open the warehouse pick document that you created in step 3 in this section.  

    Notice the value in the **Source Document** field and that all the pick lines are for assembly components.  

    Next.register the pick without changing the default information.  

6.  Choose the **Autofill Qty. to Handle** action.  
7.  Choose the **Register Pick** action.  

    Return to performing the shipping tasks.  

8.  Reopen the **Warehouse Shipment** page.  

    Notice that the **Qty. Picked** field is still empty on all lines. This is because you still have not picked the items to be shipped, but only the components needed to assemble the ATO quantities.  

    Proceed to review the related assembly order.  

9. Select the shipment line for three units of Kit B.  
10. On the **Lines** FastTab, choose **Line**, and then choose **Assemble to Order**. The **Assembly Order** page opens.  

    Notice that several fields on the assembly order are unavailable because the order is linked to a sales order.  

    Notice on the assembly order lines that the **Qty. Picked** field is filled. This is due to the pick that you registered in step 7 in this section.  

11. In the **Quantity to Assemble** field, try to enter any value lower than **3**.  

    Read the error message explaining why this field can only be filled through the **Qty. to Ship** field on the related shipment.  

    The **Quantity to Assemble** field is editable is to support situations where you want to partially ship an inventory quantity instead of assembling more units to the order. For more information, see the “Combination Scenarios” section in [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).  

12. Close the **Assembly Order** page to return to the **Warehouse Shipment** page.  
13. On the shipment line for three units of Kit B, in the **Qty. to Ship** field, enter **3**.  
14. Choose the **Post Shipment** action, and then select the **Ship** button.  

    Along with this warehouse shipment posting, the full consumption and output quantities of the related assembly order are posted, and the **Remaining Quantity** field is empty. The sales order line for Kit B is updated to show that the three units are shipped.  

    Warehouse activities to fulfill the first sales order line by January 23 are completed. Next, fulfill the sales order lines that are shipping on January 27  

### Assembling and Recording the Second ATO Quantity  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assembly Orders**, and then choose the related link.  

    Notice that the ATO order for shipped units of Kit B is still in the list, although the **Remaining Quantity** is empty. This is because the linked sales order is still not fully invoiced.  

    > [!NOTE]  
    >  In this section, the assembly worker is responsible for recording the completed ATO assembly work on the warehouse shipment line. This workflow may occur in environments where the assembly work is performed in a separate assembly department and assembly workers are authorized to change the warehouse shipment line.  

2.  Open the ATO assembly order for five units of Kit A.  

    Notice that the **Quantity to Assemble** and the **Quantity to Consume** fields are empty because no work is recorded yet.  

    Notice on the assembly order lines that the **Qty. Picked** field is filled. This is due to the pick that was registered on January 23.  

    Next, record that the assembly order is completed.  

3.  Choose the **Asm.-to-Order Whse. Shpt. Line** action.  
4.  On the **Asm.-to-Order Whse. Shpt. Line** page, in the **Qty. to Ship** field, enter **5**, and then close the page.  

    Notice on the **Assembly Order** page that the **Quantity to Assemble** and the **Quantity to Consume** fields are now filled with the output and consumption quantities that will be posted with the shipment.  

5.  Close the **Assembly Order** page.  

### Assembling the ATS Quantity  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assembly Orders**, and then choose the related link.  
2.  Open the assembly order for ten units of Kit A.  

    Notice that the **Quantity to Assemble** field is filled with the expected quantity.  

    Next, create a pick document to retrieve the needed components.  

3.  Choose the **Release** action.  
4.  Choose the **Create Whse. Pick** action, and choose the **OK** button.  

    Next, perform the picker’s task.  

5.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Picks**, and then choose the related link.  
6.  Open the warehouse pick document that you created in step 4 in this section.  

     Proceed to register the pick without changing the default information.  

7.  Choose the **Autofill Qty. to Handle** action.  
8.  Choose the **Register Pick** action.  

    Return to the assembly order to perform the last assembly task.  

9. In the **Assembly Order**, choose the **Post** action, and then choose the **Yes** button.  

    Notice that the assembly order is removed from the list of open orders.  

### Shipping the Remaining Items, Partly from Stock and Partly Assembled to the Order  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Shipment**, and then choose the related link.  
2.  Open the most recent warehouse shipment that is created at WHITE location.  

    Notice on the line for ten units of Kit A that the **Qty. to Ship** and **Qty. Picked** field are empty.  

    Next, pick any remaining items.  

3.  Choose the **Create Pick** action, and then choose the **OK** button.  

    Next, perform the picker’s last task for this warehouse shipment.  

4.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Picks**, and then choose the related link.  
5.  Open the warehouse pick document that you created in step 3 in this section.  

    Notice that this pick document is for assembly item, not for assembly components.  

    Next, register the pick without changing the default information.  

6.  Choose the **Autofill Qty. to Handle** action.  
7.  Choose the **Register Pick** action, and then choose the **Yes** button.  

    Return to the warehouse shipment to perform the last task.  

8.  Reopen the **Warehouse Shipment** page.  

    On the **Warehouse Shipment** page, on the line for ten units of Kit A, notice that the **Qty. to Ship** and **Qty. Picked** fields now contain **10**.  

9. Choose the **Post Shipment** action, and the choose **Ship**.  

    The warehouse shipment document is removed, which indicates that the involved warehouse activities are completed. Next, verify that the sales order has been processed.  

10. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link  
11. Open the sales order for The Device Shop.  

    Notice that the **Quantity Shipped** field contains the full quantity on both lines.  

    When the Device Shop pays for their receipt of the 18 PCs from CRONUS, the sales order and its linked assembly orders are removed.  

## See Also  
 [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md)   
 [Assemble Items](assembly-how-to-assemble-items.md)   
 [Pick Items for Warehouse Shipment](warehouse-how-to-pick-items-for-warehouse-shipment.md)   
 [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md)   
 [Assemble Items](assembly-how-to-assemble-items.md)   
 [Design Details: Assembly Order Posting](design-details-assembly-order-posting.md)   
 [Design Details: Internal Warehouse Flows](design-details-internal-warehouse-flows.md)   
 [Design Details: Outbound Warehouse Flow](design-details-outbound-warehouse-flow.md)   
 [Walkthrough: Planning Supplies Automatically](walkthrough-planning-supplies-automatically.md)
