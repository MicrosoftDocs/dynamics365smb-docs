---
    title: Walkthrough - Planning Supplies Automatically | Microsoft Docs
    description: Phrases like “run planning” and “run MRP” refer to the calculation of the master production schedule (MPS) and the material requirements plan (MRP) based on actual and forecasted demand.
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
# Walkthrough: Planning Supplies Automatically

**Note**: This walkthrough must be performed on a demonstration company with the **Full Evaluation - Complete Sample Data** option, which is available in the Sandbox environment. For more information, see [Creating a Sandbox Environment](across-how-create-sandbox-environment.md).

Phrases like “run planning” and “run MRP” refer to the calculation of the master production schedule (MPS) and the material requirements plan (MRP) based on actual and forecasted demand.  

-   MPS is the calculation of a master production schedule based on actual demand and the demand forecast. The MPS calculation is used for end items that have a forecast or a sales order line. These items are called "MPS items" and are identified dynamically when the calculation starts.  
-   MRP is the calculation of material requirements based on actual demand for components and the demand forecast on the component level. MRP is calculated only for items that are not MPS items. The overall purpose of MRP is to provide time-phased formal plans, by item, to supply the right item at the right time, in the right place, in the right quantity.  

 The planning algorithms used for both MPS and MRP are identical. The planning algorithms use netting, reuse of existing supply orders, and action messages. The planning system process examines what is needed or will be needed (demand) and what is available or expected (supply). When these quantities are netted against each other, action messages are displayed in the planning worksheet. Action messages are suggestions to create a new supply order, change a supply order (quantity or date), or cancel an existing supply order. Supply orders can be production orders, purchase orders, and transfer orders. For more information, see [Design Details: Supply Planning](design-details-supply-planning.md).  

 The planning result is calculated partly from the demand-supply sets in the database and partly by the setup of stockkeeping unit cards or item cards, production BOMs, and routings.  

## About This Walkthrough  
 This walkthrough demonstrates how to use the supply planning system to automatically plan all the purchase and production orders required to produce 15 touring bicycles demanded on different sales orders. To provide a clear and realistic walkthrough, the number of planning lines is delimited by filtering out all other demand-supply sets in the CRONUS International Ltd. demonstration company except the sales demand at location BLUE.  

 This walkthrough illustrates the following tasks:  

-   Creating the sales order and calculating a complete supply plan.  
-   Viewing planning parameters and order tracking entries behind the planning lines.  
-   Automatically creating the suggested supply orders.  
-   Creating new sales demand and replanning accordingly.  

## Roles  

-   Production Planner  
-   Purchasing Agent  

## Prerequisites  
 To complete this walkthrough, you will need:  

-   The CRONUS International Ltd. demonstration  company.  
-   To change various item setup values by following the steps in the “Preparing Sample Data” section, later in this walkthrough.  

## Story  
 The customer, Cannon Group PLC, orders five touring bikes for shipment on 02-05-2014 (February 5).  

 Eduardo, the production planner, performs the routine supply planning for the first week of February 2014. He filters on his own location, BLUE, and enters a planning interval of the work date (01-23-2014) to 02-07-2014 before he calculates an initial supply plan.  

 The only demand that week is for the Cannon Group sales order. Eduardo sees that none of the planning lines have warnings, and he proceeds to create supply orders without changes for the suggested planning lines.  

 The next day, before any of the initial supply orders are started or posted, Eduardo is notified that another customer has ordered ten touring bikes for shipment on 02-12-2014. He recalculates to adjust the supply plan according to the change of demand. The recalculation gives you a net change plan that suggests changes to both time and quantity of some of the supply orders created in the first run.  

 During the various planning steps, Eduardo looks up the involved orders, and uses the Order Tracking feature to see which demand is covered by which supply.  

## Preparing Sample Data  
 Create stockkeeping units (SKUs) for the touring bike and a selection of its components, item numbers 1001 to 1300. (Some components are excluded to simplify the procedures.) Adjust the planning parameters of the selected components to provide a more transparent planning result.  

### To create stockkeeping units  

1.  Open the item card for item 1001, Touring Bicycle.  
2.  Choose the **Create Stockkeeping Unit** action.  
3.  On the **Create Stockkeeping Unit** page, leave all options and filters unchanged, and then choose the **OK** button.  
4.  Repeat steps 1 through 3 for all items in the number range between 1100 and 1300.  

### To change selected planning parameters  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Stockkeeping Units**, and then choose the related link.  
2.  Open the BLUE stockkeeping unit card for item 1100, Front Wheel.  
3.  On the **Planning** FastTab, fill in the fields as described in the following table.  

    |Reordering Policy|Safety Stock Quantity|Lot Accumulation Period|Rescheduling Period|  
    |-------------------------------------------|-----------------------------------------------|-------------------------------------------------|---------------------------------------------|  
    |Lot-for-Lot|Blank|2W|2W|  

4.  Repeat steps 2 and 3 for all SKUs in the number range between 1100 and 1300.  

 This completes the preparation of sample data for the walkthrough.  

## Creating a Regenerative Supply Plan  
 In reaction to a new sales order for five touring bikes, Ricardo begins the planning process by setting options, filters, and planning interval to exclude all other demand except that of the first week of February at location BLUE. He begins by calculating a master production schedule (MPS), and then proceeds to calculate a complete supply plan for all lower-level demand (MRP).  

### To create the sales order  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2.  Choose the **New** action.  
3.  On the **Sales Order** page, fill in the fields as described in the following table.  

    |Sell-to Customer Name|Shipment Date|Item No.|Location|Quantity|  
    |----------------------------|-------------------|--------------|--------------|--------------|  
    |Cannon Group|02-05-2014|1001|BLUE|5|  

4.  Accept the availability warning and choose the **Yes** button to record the new demand quantity.  

### To create a regenerative plan to fulfill demand at location BLUE  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Planning Worksheet**, and then choose the related link.  
2.  Choose the **Calculate Regenerative Plan** action.  
3.  On the **Calculate Plan - Plan. Wksh.** page, fill in the fields as described in the following table.  

    |Calculate Plan|Starting Date|Ending Date|Show results:|Limit totals to|  
    |--------------------|-------------------|-----------------|-------------------|---------------------|  
    |**MPS** = Yes<br /><br /> **MRP** = No|01-23-2014<br /><br /> (work date)|02-07-2014|1001..1300|Location Filter = BLUE|  

4.  Choose the **OK** button to start the planning run.  

     One planning line is created suggesting that a planned production order be issued to produce the ten touring bikes, item 1001, by 02-05-2014, the shipment date of the sales order.  

     Next, verify that this planning line relates to the Cannon Group sales order by using the **Order Tracking** function, which dynamically links demand with its planned supply.  

5.  Select the new planning line, and then choose the **Order Tracking** action.  
6.  On the **Order Tracking** page, choose the **Show** action.  

     The sales order for five touring bikes shipping to customer number 10000 on 02-05-2014, is shown.  

7.  Close the **Sales Order** and **Order Tracking** pages.  

### To calculate MRP to include underlying component needs  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Planning Worksheet**, and then choose the related link.  
2.  Choose the **Calculate Regenerative Plan** action.  
3.  On the **Calculate Plan - Plan. Wksh.** page, fill in the fields as described in the following table.  

    |Calculate|Starting Date|Ending Date|Show results:|Limit totals to:|  
    |---------------|-------------------|-----------------|-------------------|----------------------|  
    |**MPS** = Yes<br /><br /> **MRP** = Yes|01-23-2014|02-07-2014|1001..1300|Location Filter = BLUE|  

4.  Choose the **OK** button to start the planning run.  

     A total of 14 planning lines are created suggesting supply orders for all the demand that the touring bike sales order at BLUE location represents.  

## Analyzing the Planning Result  
 To analyze the suggested quantities, Eduardo drills down on selected planning lines to view order tracking entries and planning parameters.  

 On the **Planning Worksheet** page, note in the **Due Date** column that the suggested supply orders are scheduled backward from the due date of the sales order, 02-05-2014. The timeline begins on the top planning line with the production order to produce the finished touring bikes. The timeline ends on the bottom planning line with the purchase order for one of the lowest-level items, 1255, Socket Back, due on 01-30-2014. Like the planning line for item 1251, Axle Back Wheel, this line represents a purchase order for components that are due on the starting date of its produced parent, subassembly item 1250, which in turn is due on 02-03-2014. Throughout the worksheet, you can see that all underlying items are due on the starting date of their parents.  

 The planning line for item 1300, Chain Assy, suggests ten pieces. This deviates from the five pieces that we expect to need to fulfill the sales order. Proceed to view the order tracking entries.  

### To view order tracking entries for item 1300  

1.  Select the planning line for item 1300, and then choose the **Order Tracking** action.  

     The two lines on the **Order Tracking** page show that five pieces are tracked from the planning line (first order tracking line) to sales order 1001 (second order tracking line). The last five pieces suggested on the planning line are not related to any document lines, but to a planning parameter, forecast entry, or blanket order entry. Such untracked quantities are summed in the **Untracked Quantity** field in the header of the **Order Tracking** page.  

2.  Choose the **Untracked Quantity** field.  

     The **Untracked Planning Elements** page shows that item 1300 uses a planning parameter, Minimum Order Quantity, of 10.00. Therefore, the planning line is for ten pieces in total, of which only five can be tracked to a demand. The last five pieces are an untracked quantity to satisfy the planning parameter. Proceed to review the planning parameter.  

### To check the planning parameter  

1.  On the **Untracked Planning Elements** page, select the order tracking line for item 1300.  
2.  Choose the **Item No.** field, and then choose the **Advanced** action.  
3.  On the **Item List** page, choose the **Stockkeeping Units** action.  
4.  On the **Stockkeeping Unit List** page, open the BLUE stockkeeping unit card.  
5.  On the **Planning** FastTab, note that the **Minimum Order Quantity** field contains 10.  
6.  Close all pages except the **Planning Worksheet** page.  

### To view more order tracking entries  

1.  Select the planning line for item 1110, Rim, and then choose the **Order Tracking** action.  

     The **Order Tracking** page shows that five rims are needed for each production order for front and back wheels respectively.  

     The same order tracking applies to the planning lines for items 1120, 1160, and 1170. For item 1120, the **Quantity per** field on the production BOM of each wheel item is 50 PCS, which result in a total need of 100.  

     The planning line for item 1150 for six pieces looks irregular. Proceed to analyze.  

2.  Select the planning line for item 1150, and then, on then choose the **Order Tracking** action.  

     The **Order Tracking** page shows that five units are tracked to the front wheel, and one unit is untracked. Proceed to view the untracked quantity.  

3.  Choose the **Untracked Quantity** field.  

     The **Untracked Planning Elements** page shows that item 1150 uses a planning parameter, Order Multiple, of 2.00, which specifies that when the item is ordered, it must be in a quantity that is divisible by 2. The closest number to 5 that is divisible by 2 is 6.  

     The same order tracking applies to the planning lines for the Front Hub components, items 1151 and 1155, except that each need is multiplied by the scrap percentage that is defined for item 1150 in the **Scrap Percentage** field on the item card.  

 This completes the analysis of the initial supply plan. Notice that the **Accept Action Message** check box is selected in all planning lines indicating that they are ready to be converted to supply orders.  

## Carrying Out Action Messages  
 Next, Eduardo converts the suggested planning lines to supply orders by using the **Carry Out Action Msg.** function.  

### To automatically create the suggested supply orders  

1.  Select the **Accept Action Message** check box on all planning lines with a warning of type Exception.  
2.  Choose the **Carry Out Action Message** action.  
3.  On the **Carry Out Action Msg.-Plan.** page, fill in the fields as described in the following table.  

    |Production Order|Purchase Order|Transfer Order|  
    |----------------------|--------------------|--------------------|  
    |Firm Planned|Make Purch. Orders|Make Trans. Orders|  

4.  Choose the **OK** button to automatically create all the suggested supply orders.  
5.  Close the empty **Planning Worksheet** page.  

 This completes the initial calculation, analysis, and creation of a supply plan for demand at location BLUE in the first week of February. In the following section, another customer orders ten touring bikes, and Eduardo must replan.  

## Creating a Net Change Plan  
 The next day, before any supply orders are started or posted, a new sales order arrives from Libros S.A. for ten touring bikes to be shipped on 02-12-2014. Eduardo is notified of the new demand, and he proceeds to replan in order to adjust the current supply plan. Eduardo uses the Net Change Plan function to calculate only the changes that are made to demand or supply since the last planning run. In addition, he expands the planning period to 02-14-2014 to include the new sales demand on 02-12-2014.  

 The planning system calculates the best way to cover the demand for these two identical products, such as to consolidate some purchase and production orders, reschedule other orders, and create new orders where it is required.  

### To create the new sales demand and replan accordingly  

1.  Choose the **New** action.  
2.  On the **Sales Order** page, fill in the fields as described in the following table.  

    |Sell-to Customer Name|Shipment Date|Item No.|Location|Quantity|  
    |----------------------------|-------------------|--------------|--------------|--------------|  
    |Libros S.A.|02-12-2014|1001|BLUE|10|  

3.  Accept the availability warning and choose the **Yes** button to record the demand quantity.  
4.  Proceed to replan to adjust the current supply plan.  
5.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Planning Worksheet**, and then choose the related link.  
6.  Choose the **Calculate Net Change Plan** action.  
7.  On the **Calculate Plan - Plan. Wksh.** page, fill in the fields as described in the following table.  

    |Calculate Plan|Starting Date|Ending Date|Show results:|Limit totals to|  
    |--------------------|-------------------|-----------------|-------------------|---------------------|  
    |**MPS** = Yes<br /><br /> **MRP** = Yes|01-23-2014|02-14-2014|1001..1300|Location Filter = BLUE|  

8.  Choose the **OK** button to start the planning run.  

 A total of 14 planning lines are created. Notice in the first planning line that the **Action Message** field contains **New**, the **Quantity** field 10, and the **Due Date** field 02-12-14. This new line for the top parent item, 1001, Touring Bike, is created because the item uses a reordering policy of **Order**, which means that it must be supplied in a one-to-one relationship to its demand, the sales order of ten pieces.  

 The next two planning lines are the production orders for touring bike wheels. Each existing order of five, in the **Original Quantity** field, is increased to 15, in the **Quantity** field. Both production orders have unchanged due dates, as indicated in the **Action Message** field that contains **Change Qty.** This is also the case for the planning line for item 1300, except its order multiple of 10.00 rounds the tracked demand for 15 pieces up to the 20.  

 All other planning lines have an action message of **Resched. & Chg. Qty.**. This means that apart from being increased in quantity, the due dates are moved in relation to the supply plan to include the extra quantity in the available production time (capacity). Purchased components are rescheduled and increased to supply the production orders. Proceed to analyze the new plan.  

## Analyzing the Changed Planning Result  
 Because all lot-for-lot-planned items within the filter, 1100 to 1300, have a rescheduling period of two weeks, their existing supply orders are all modified to meet the new demand, which occurs within the specified two weeks.  

 Several planning lines are simply multiplied by three to provide 15 touring bikes instead of 5, and the due dates are moved back in time to provide the increased quantities by the shipment date of the sales order to the Cannon Group. For these planning lines, all quantities can be tracked. The remaining planning lines are increased by ten pieces in addition to moving their due dates. For these planning lines, a part of the quantities are untracked due to different planning parameters. Proceed to view some of these order tracking entries.  

### To view order tracking entries for item 1250  

1.  Select the planning line for item 1250, and then choose the **Order Tracking** action.  

     The seven lines on the **Order Tracking** page show that five and ten pieces are tracked through the back wheel to the touring bikes on the two sales orders respectively.  

     The last five pieces are untracked. Proceed to analyze.  

2.  Choose the **Untracked Quantity** field.  

     The **Untracked Planning Elements** page shows that item 1250 uses a planning parameter, Order Multiple, of 10.00. Therefore, the planning line is for 20 pieces in total to round the actual need up to the nearest number divisible by 10. The last five pieces are an untracked quantity to satisfy the planning parameter.  

3.  Close all pages except the **Planning Worksheet** page.  

### To view an existing order  

1.  In the planning line for item 1250, choose the **Ref. Order No.** field.  
2.  On the **Firm Planned Prod. Order** page for the Back Hub. The existing order for ten pieces, which you created in the first planning run, opens.  
3.  Close the firm planned production order.  

 This completes the walkthrough of how the planning system is used to automatically detect demand, calculate the appropriate supply orders according to demand and planning parameters, and then automatically create different types of supply orders with the appropriate dates and quantities.  

## See Also  
 [Business Process Walkthroughs](walkthrough-business-process-walkthroughs.md)   
 [Walkthrough: Planning Supplies Manually](walkthrough-planning-supplies-manually.md)   
 [Design Details: Supply Planning](design-details-supply-planning.md)
