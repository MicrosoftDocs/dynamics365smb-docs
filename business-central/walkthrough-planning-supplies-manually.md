---
    title: Walkthrough - Planning Supplies Manually | Microsoft Docs
    description: This walkthrough demonstrates the process of planning supply orders to fulfill new demand. You can initiate supply planning at fixed intervals, for example, every morning or every Monday, or when you are notified by sales or production, depending on the type of demand.
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
# Walkthrough: Planning Supplies Manually

**Note**: This walkthrough must be performed on a demonstration company with the **Full Evaluation - Complete Sample Data** option, which is available in the Sandbox environment. For more information, see [Creating a Sandbox Environment](across-how-create-sandbox-environment.md).

This walkthrough demonstrates the process of planning supply orders to fulfill new demand. You can initiate supply planning at fixed intervals, for example, every morning or every Monday, or when you are notified by sales or production, depending on the type of demand. In this walkthrough you will use the **Order Planning** page, a simple supply planning tool that is based on manual decision-making instead of parameter-based automatic planning.  

## About This Walkthrough  
 This walkthrough illustrates the following tasks:  

-   Planning a purchase order for manufacturing components.  
-   Planning a transfer order to fulfill sales demand.  
-   Planning a production order for a multilevel item.  

## Roles  
 This walkthrough demonstrates tasks performed by the following user roles:  

-   Production Planner  
-   Purchasing Agent  
-   Sales Order Processor  

## Prerequisites  
 Before you begin this walkthrough, you must install the [!INCLUDE[d365fin](includes/d365fin_md.md)]. The following modifications must be made to the database:  

-   Delete all existing sales orders for bicycles.  
-   Create one sales order for 10 bicycles at BLUE location.  
-   Delete all planned and firm planned production orders. Do not delete started orders with entries that are already posted.  

 As a rule, use the suggested data in this walkthrough because this data has the necessary records.  

## Story  
 Eduardo, the Production Planner of a small manufacturing company, is about to plan production and purchase orders to fulfill new sales demand.  

 Because the products have few BOM levels and the flow of orders is relatively low, Eduardo uses the **Order Planning** page to manually create supply orders, one product level at a time.  

 In a more complex manufacturing environment, the planning worksheet is used to plan supply based on item parameters such as rescheduling period, safety lead time, reorder point, and batch calculations of consolidated demand from all product levels.  

## Setting Up the Sample Data  
 The standard CRONUS demonstration company currently has lots of unplanned demand. During the different planning tasks in this walkthrough, you will have to deviate from the realistic business flow by ignoring demand with close due dates and instead use demand with later due dates.  

## Using the Order Planning Page  

The **Order Planning** page can be accessed from several different locations:  

-   Manufacturing, Planning  
-   Sales & Marketing, Order Processing  
-   Purchase, Planning  
-   In addition, you can open this page for a specific production order by choosing the **Planning** action.

### To use the Order Planning page  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Order Planning**, and then choose the related link.  

     When the **Order Planning** page first opens, a plan must be calculated to show the new demand since it was last calculated.  

2.  Choose the **Calculate Plan** action.  

     The planning system analyzes any new demand that has been introduced, such as new sales, changed sales, or production orders.  

     Based on total availability, the quantity needed for each demand line is calculated. This calculation is performed order-by-order. This means that the order which includes the demand line with the earliest due date or shipment date will be calculated first. After that, additional demand lines will be calculated in the same order, regardless of the due date or shipment date.  

3.  Be sure that the **Order Planning** page is maximized and that column fields are resized to show all the default field names.  

     When the calculation is completed, the page displays all unfulfilled demand as collapsed order header lines sorted by earliest demand date.  

     Notice that CRONUS has several orders with unfulfilled demand. Each bold planning line represents an order, sales order, or production order, including at least one order line with insufficient availability.  

4.  In the **Show Demand As** field, select the **All Demand** filter.  

     With the **Demand Type** field, you can choose which order types that you want to display.  

     Orders that do not have availability problems are not shown. If no orders exist when a plan is calculated, a message will display and no planning lines will appear.  

## Planning a Purchase Order to Fulfill Component Demand  
 In this procedure, you create a purchase order for needed manufacturing components.  

### To plan a purchase order to fulfill component need in production  

1.  Expand the first line (choose the + symbol).  
2.  Choose the first demand line, with item **LSU-15**, and then choose the **Show Document** action.  
3.  Close the opened production order to return to the **Order Planning** page.  
4.  In the **Replenishment System** field, select **Purchase**.  

     The default value is from the item card, or SKU card, but you can change it to one of the following options:  

    -   **Purchase** – To create a purchase order.  
    -   **Transfer** – To create a transfer order.  
    -   **Prod. Order** – To create a production order.  

5.  In the **Supply From** field, select one of the following options according to the selected replenishment system:  

    -   **Vendor** – For purchases  
    -   **Location** – For transfers  

     If the field is not filled in, an error message will display when you try to create the supply orders.  

    > [!NOTE]  
    >  If the components have a default vendor number set up on the item cards, the lines will be preset.  

6.  Choose the **Supply From**  field.  
7.  On the **Item Vendor Catalogue** page, choose the **New** action, and then select vendor **30000**.  
8.  Choose the **OK** button to return to the **Order Planning** page.  
9. Copy vendor **30000** to the other lines for loudspeaker components on this production order.  

     You are now ready to create a purchase order.  

10. Choose the **Make Orders** action. The **Make Supply Orders** page opens.  
11. On the **Order Planning** FastTab, in the **Make Orders for** field, choose the **Active Order** option.  
12. On the **Options** FastTab, in the **Create Purchase Order** field, choose the **Make Purch. Order** option.  
13. Choose the **OK** button to create purchase orders for all the components of the order.  

     The purchase orders are now created and saved as the last orders in the list of purchase orders.  

## Planning a Transfer Order to Fulfill Sales Demand  
 In this procedure, you will plan for demand from a sales order. Demand lines represent sales lines and not component lines, as in production demand.  

### To plan a transfer order to fulfill sales demand  

1.  Move the pointer to the planning line for order **2008**.  
2.  Expand the line and move the pointer to the demand line.  

     Sales order **2008** is for ten loudspeakers, item **LS-120**, ordered by John Haddock Insurance Co.  

     The item’s defined replenishment system and default vendor will display.  

    > [!NOTE]  
    >  At the bottom of the page, there are four information fields. In the **Earliest Date Available** field, the ten pieces that are needed will be available, on an inbound supply order, nine days later than the current due date. If this is too late for the customer, the **Available for Transfer** field shows 13 pieces of the item at another location. You will want to plan for this stock.  

3.  Choose the **Available for Transfer** field to open the **Get Alternative Supply** page.  
4.  Choose the **OK** button to book the ten items that are available.  

    > [!NOTE]  
    >  In the demand line, the suggested purchase has been exchanged with a transfer from GREEN location. The **Make Orders** function creates a transfer order from GREEN to the demanded location. The **Substitutes Exists** field works in the same way.  

5.  Choose the **Make Orders** action. The **Make Supply Orders** page opens.  
6.  On the **Order Planning** FastTab, in the **Make Orders for** field, choose the **The Active Order** option.  
7.  On the **Options** FastTab, in the **Create Transfer Order** field, select the **Make Trans. Orders** option.  
8.  Choose the **OK** button to create the transfer order to supply the sales order.  

     The transfer order is now created and saved in the list as the last order in the list of open transfer orders.  

## Planning a Multilevel Production Order to Fulfill Sales Demand  
 In this procedure, you will plan to fulfill sales demand for a produced item with multiple product levels, each creating dependent production demand.  

### To plan multilevel production to fulfill sales demand  

1.  Select the planning line with sales demand for order **1001**, created earlier as prerequisite data.  

     This demand is a sales line, but the item has a defined replenishment system of **Prod. Order**. Proceed to add an extra bell to the component need of each bicycle.  

2.  Choose the **Components** action to open the **Planning Components** page.  
3.  On the line with the Bell item, change the **Quantity per** field from **1** to **2**.  
4.  On the **Order Planning** page, consider your planning alternatives. In this case, you have no alternative means of supply, no transfer, substitute, or later delivery. You must create the suggested supply order, a production order.  
5.  Choose the **Make Orders** action to create the production order.  

     On the **Order Planning** page, notice that the planning line for sales order **1001** no longer exists and that the initial sales demand has been covered.  

6.  Close the **Order Planning** page.  

     Now, you could choose to stay in this view and complete all the planning tasks. Instead, you will now take on the Production Planner role by going to the production order that you just created and access the **Order Planning** page.  

 As a production planner you now must plan a specific production order.  

### To plan a specific production order  

1.  Open the production order **101001**, for ten bicycles, that you just created by using the **Make Orders** function.  
2.  Open the **Prod. Order Components** page to check that the extra bell is reflected on the production order.  
3.  Choose the **Planning** action.  

     The **Order Planning** page opens in a view that is always filtered on the specific production demand. Sales demand is not displayed. You must calculate a plan before you can see any additional demand.  

4.  Choose the **Calculate Plan** action.  

     Notice that four new production orders appear as unplanned production demand derived from order **101001**. The new lines represent new production demand from the subassemblies that must be created to produce the order.  

5.  Choose the **Expand All** action to get an overview of all the production demand for the production orders.  

     To provide additional information about the demand lines, you may want to add the **Demand Quantity** and **Demand Qty. Available** fields to your view.  

     Now you must supply ten of each component.  

     Note that four of the demand lines have replenishment system Prod. Order. These four subassemblies represent the second product level of the bicycle.  

     The default replenishment settings are already filled in and you can proceed to make orders.  

6.  Choose the **Make Orders** action.  

     Before you choose the **OK** button, notice the text on the **Order Planning** FastTab. This text is important because you know that the bicycle has several produced components, subassemblies, in its product structure that might be in demand when you create this production order.  

7.  On the **Make Supply Order** page, in the **Make Orders for** field, choose the **All Lines** option, and then choose the **OK** button to create production orders for the second product level of the order.  

     Note that the top-level production demand for production order 101001 no longer exists. This means that the initial production demand for subassemblies has been planned for.  

     On the **Order Planning** page, you calculate a plan again in order to plan the bicycle structure.  

8.  Choose the **Calculate Plan** action to recalculate the plan as instructed by the embedded Help text.  

     The two new lines represent additional production demand derived from the subassemblies planned in the previous steps. It is suggested that you make two production orders to supply the wheel hubs, one for 10 front hubs and one for 10 back hubs.  

9. Choose the **Expand All** action to get an overview of all the demand for the two production orders.  

     The suggested supply plan indicates that a total of four purchase orders will be created for the components. You decide to make the proposed orders.  

10. Choose the **Make Orders** action.  
11. In the **Make Orders for** field, select the **All Lines** option, and then choose the **OK** button. Check if additional demand exists for the production of the parent item, the bicycle, which is being sold on sales order 1001.  
12. Choose the **Calculate Plan** action.  

     The message indicates that all required items are now supplied. Verify the firm planned production orders that are created.  

13. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Firm Planned Prod. Orders**, and then choose the related link.  

     On the **Firm Planned Prod. Orders** page review how start times and end times of individual orders are scheduled according to the product structure. The lowest-level components are produced first. Therefore, you must plan multilevel orders as demonstrated in this planning workflow.  

## See Also  
 [Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)   
 [Walkthrough: Planning Supplies Automatically](walkthrough-planning-supplies-automatically.md)
