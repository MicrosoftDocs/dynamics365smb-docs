---
    title: Insert topic title| Microsoft Docs
    description: Insert description
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
# About Forecasting Functionality
Forecasting functionality is used to create anticipated demand; actual demand is created from sales and production orders. During creation of the Master Production Schedule \(MPS\), the forecast is netted against the sales and production orders. The *Component* option on the forecast determines which type of requirements to take into consideration in the netting process. If the forecast is for a sales item, only sales orders net the forecast. If it is for components, only dependent demand from production order components net the forecast.  
  
 Forecasting allows your company to create "what if" scenarios and efficiently and cost\-effectively plan for and meet demand. Accurate forecasting can make a critical difference in customer satisfaction levels with regard to order promising dates and on\-time delivery.  
  
## Sales Forecasts and Production Forecasts  
 The forecasting functionality in the program can be used to create sales or production forecasts, in combination or independently. For example, most make\-to\-order companies don't carry finished goods inventory, because each item is produced when it is ordered. Anticipating orders \(sales forecasting\) is critical for a reasonable turnaround time on the finished goods \(production forecasting\). As an example, component parts with lengthy delivery times, if not on order or on inventory, can delay production.  
  
-   The sales forecast is the sales department's best guess at what will be sold in the future, and is specified by item and by period. However, the sales forecast is not always adequate for production.  
  
-   The production forecast is the production planner's projection of how many end items and derived subassemblies to produce in specific periods to meet the forecasted sales.  
  
 In most cases, then, the production planner modifies the sales forecast to fit the conditions of production, yet still satisfies the sales forecast.  
  
## Creating Forecasts  
 [Forecasts are created](../OperationsPlanning/how-to-create-a-forecast.md) manually using the **Production Forecast.** Multiple forecasts can exist in the system, and are differentiated by name and type. Forecasts can be copied and edited as necessary. Note that only one forecast is valid for planning purposes at a time.  
  
 The forecast consists of a number of records each stating item number, forecast date, and forecasted quantity. The forecast of an item covers a period, which is defined by the forecast date and the forecast date of the next \(later\) forecast record. From a planning point of view, the forecasted quantity should be available at the start of the demand period.  
  
 You must designate a forecast as *Sales Item*, *Component*, or *Both*. The forecast type *Sales Item* is used for sales forecasting. The production forecast is created using the *Component* type. The forecast type *Both* is only used to give the planner an overview of both the sales forecast and the production forecast. With this option, the forecast entries are not editable. By designating these forecast types here, you can use the same worksheet to enter a sales forecast as you do a production forecast, and use the same sheet to view both forecasts simultaneously. Note that the system treats the different inputs \(sales and production\) differently when calculating planning, based on item, manufacturing, and production setup.  
  
### Component Forecast  
 The component forecast can be seen as an option forecast in relation to a parent item. This can, for example, be useful if the planner can estimate the demand for the component.  
  
 As the component forecast is designed to define options for a parent item, the component forecast should be equal or less than the sales item forecast quantity. If the component forecast is higher than the sales item forecast, the system treats the difference between these two types of forecast as independent demand.  
  
### Forecasting Periods  
 The forecast period is valid from its starting date until the date the next forecast starts. The time interval window gives you multiple choices to insert the demand at a specific date in a period. It is therefore recommended not to change the forecast period scope unless you want to move all forecast entries to the starting date of this period.  
  
### Forecast by Locations  
 It can be stated in the manufacturing setup if [forecasts on locations are to be limited to each location](../Topic/\($%20T_99000765_37%20Use%20Forecast%20on%20Locations%20$\).md). Note, though, that if location\-based forecasts are viewed in isolation, the overall forecast may not be representative.  
  
## See Also  
 [How to: Run MPS and MRP](../OperationsPlanning/how-to-run-mps-and-mrp.md)   
 [How to: Create Production Orders from Sales Orders](../OperationsPlanning/how-to-create-production-orders-from-sales-orders.md)   
 Order Planning   
 [How to: Plan for New Demand](../OperationsPlanning/how-to-plan-for-new-demand.md)   
 [How to: Plan Project Orders](../OperationsPlanning/how-to-plan-project-orders.md)   
 [Production Forecast\-duplicate](../Topic/\($%20N_99000919%20Production%20Forecast%20$\)-duplicate.md)