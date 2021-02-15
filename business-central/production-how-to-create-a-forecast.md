---
    title: How to Create a Demand Forecast
    description: You can create sales and production forecasts with the **Demand Forecast** page.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 01/12/2021
    ms.author: edupont

---
# Create a Demand Forecast
You can create sales and production forecasts with the **Demand Forecast** page.  

Forecasting functionality is used to create anticipated demand; actual demand is created from sales and production orders. During creation of the Master Production Schedule (MPS), the forecast is netted against the sales and production orders. The *Component* option on the forecast determines which type of requirements to take into consideration in the netting process. If the forecast is for a sales item, only sales orders net the forecast. If it is for components, only dependent demand from production order components net the forecast.  

Forecasting allows your company to create "what if" scenarios and efficiently and cost-effectively plan for and meet demand. Accurate forecasting can make a critical difference in customer satisfaction levels with regard to order promising dates and on-time delivery.  

## Sales Forecasts and Production Forecasts  
The forecasting functionality in application can be used to create sales or production forecasts, in combination or independently. For example, most make-to-order companies do not carry finished goods inventory, because each item is produced when it is ordered. Anticipating orders (sales forecasting) is critical for a reasonable turnaround time on the finished goods (production forecasting). As an example, component parts with lengthy delivery times, if not on order or on inventory, can delay production.  

-   The sales forecast is the sales department's best guess at what will be sold in the future, and is specified by item and by period. However, the sales forecast is not always adequate for production.  
-   The production forecast is the production planner's projection of how many end items and derived subassemblies to produce in specific periods to meet the forecasted sales.  

In most cases, then, the production planner modifies the sales forecast to fit the conditions of production, yet still satisfies the sales forecast.  

You create forecasts manually on the **Demand Forecast** page. Multiple forecasts can exist in the system, and are differentiated by name and type. Forecasts can be copied and edited as necessary. Note that only one forecast is valid for planning purposes at a time.  

The forecast consists of a number of records each stating item number, forecast date, and forecasted quantity. The forecast of an item covers a period, which is defined by the forecast date and the forecast date of the next (later) forecast record. From a planning point of view, the forecasted quantity should be available at the start of the demand period.  

You must designate a forecast as *Sales Item*, *Component*, or *Both*. The forecast type *Sales Item* is used for sales forecasting. The production forecast is created using the *Component* type. The forecast type *Both* is only used to give the planner an overview of both the sales forecast and the production forecast. With this option, the forecast entries are not editable. By designating these forecast types here, you can use the same worksheet to enter a sales forecast as you do a production forecast, and use the same sheet to view both forecasts simultaneously. Note that the system treats the different inputs (sales and production) differently when calculating planning, based on item, manufacturing, and production setup.  

## Component Forecast  
The component forecast can be seen as an option forecast in relation to a parent item. This can, for example, be useful if the planner can estimate the demand for the component.  

As the component forecast is designed to define options for a parent item, the component forecast should be equal or less than the sales item forecast quantity. If the component forecast is higher than the sales item forecast, the system treats the difference between these two types of forecast as independent demand.  

## Forecasting Periods  
 The forecast period is valid from its starting date until the date the next forecast starts. The time interval page gives you multiple choices to insert the demand at a specific date in a period. It is therefore recommended not to change the forecast period scope unless you want to move all forecast entries to the starting date of this period.  

## Forecast by Locations  

It can be stated in the **Manufacturing Setup** page how you want to deal with locations that are defined on forecasts when you calculate a plan. 

### Use forecast by locations

If you choose the **Use Forecast by Location** field, then [!INCLUDE[prod_short](includes/prod_short.md)] will respect any location codes that are specified for each Demand Forecast entry and calculate the remaining forecast for each location.  

Consider this example: Your company purchases and sells items on two locations: EAST and WEST. For both locations, you have configured a lot-to-lot reordering policy. You create a forecast for the two locations:

- 10 pieces for location EAST
- 4 pieces for location WEST

Then, you create a sales order with a quantity of 12 on location WEST. The planning system will suggest that you do the following:

- Replenish 10 pieces for location EAST, based on data from the forecast.  
- Replenish 12 pieces for location WEST, based on sales order. The 4 pieces that were specified in the forecast are fully consumed by the actual demand pf the sales order. For more information, see [Forecast Demand is Reduced by Sales Orders](design-details-balancing-demand-and-supply.md#forecast-demand-is-reduced-by-sales-orders). 

> [!NOTE]  
>  If location-based forecasts are viewed in isolation, the overall forecast might not be representative.

### Do not use forecast by locations
If you disable **Use Forecast by Location**, then [!INCLUDE[prod_short](includes/prod_short.md)] will ignore location codes that are specified for each Demand Forecast entry and agregate the forecasts into a forecast for empty locations.  

Consider this example: Your company purchases and sells items on two locations: EAST and WEST. For both locations, you have configured a lot-to-lot reordering policy. You create a forecast for the two locations:

- 10 pieces for location EAST
- 4 pieces for location WEST

Then, you create a sales order with a quantity of 12 on location WEST. The planning system will suggest that you do the following:

- Replenish 12 pieces for location WEST, based on the sales order. 
- Replenish 2 pieces for the empty location. The 10 and 4 pieces that were specified in the forecast are partially consumed by the actual demand of the sales order. [!INCLUDE[prod_short](includes/prod_short.md)] ignored the location codes that were specified by the user and uses a blank location instead.

> [!NOTE]  
>  You can set a filter by locations, but location-based results might not match planning results without filters.

## To create a demand forecast

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Demand Forecast**, and then choose the related link.  
2. On the **General** FastTab, select a forecast in the **Demand Forecast Name** field. Multiple forecasts can exist and are differentiated by name and forecast type.  
3. In the **Location Filter** field, select the location to which this forecast will apply.
4. In the **View by** field to change the period that is displayed in each column. You can select from the following intervals: **Day**, **Week**, **Month**, **Quarter**, **Year**, or the **Accounting Period** as set up in your finance area.    

> [!NOTE]  
>  You should consider which time interval that you want to use for future forecasts so that the time interval is consistent throughout. When you enter a forecast quantity, it is valid on the first day of the time interval that you select. For example, if you select a month, then you enter the forecast quantity on the first day of the month. If you select a quarter, then you enter the forecast quantity on the first day of the first month in the quarter.

5. In the **View as** field, select how the forecast quantities are shown for the time interval. If you select **Net Change**, then the net change in balance is displayed for the time interval. If you select **Balance at Date**, then the page displays the balance as of the last day in the time interval.  
6. In the **Forecast Type** field, select **Sales Item**,  **Component**, or **Both**. If you select **Sales Item** or **Component**, then you can edit the quantity by period. If you select **Both**, then you cannot edit the quantity, but you can choose the drop-down arrow button and view the demand forecast entries.  
7. Specify a **Date Filter** if you want to limit the amount of data displayed.  
8. On the **Demand Forecast Matrix** FastTab, enter the forecasted quantities by typing a quantity in the cell representing an item on a particular date or period. Note that in empty cells, the lookup button opens an empty page indicating that you must enter a value manually.   

> [!NOTE]  
>  You can also edit an existing forecast. On the **Demand Forecast Matrix** page, choose the **Copy Demand Forecast** action and populate the **Demand Forecast** page with an existing forecast. You can then edit quantities as appropriate.  

## See Also  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)   
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]