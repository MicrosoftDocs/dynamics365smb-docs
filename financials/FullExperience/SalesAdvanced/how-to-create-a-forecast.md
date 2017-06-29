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
# How to: Create a Forecast
You can create sales and production forecasts with the **Production Forecast** window.  
  
### To create a forecast  
  
1.  In the **Search** box, enter **Production Forecast**, and then choose the related link.  
  
2.  On the **General** FastTab, select a forecast in the **Production Forecast Name** field. Multiple forecasts can exist and are differentiated by name and forecast type.  
  
3.  In the **Location Filter** field, select the location to which this forecast will apply.  
  
4.  In the **Forecast Type** field, select **Sales Item**,  **Component**, or **Both**. If you select **Sales Item** or **Component**, then you can edit the quantity by period. If you select **Both**, then you cannot edit the quantity, but you can choose the drop-down arrow button and view the production forecast entries.  
  
5.  Specify a **Date Filter** if you want to limit the amount of data displayed.  
  
6.  On the **Production Forecast Matrix** FastTab, enter the forecasted quantities of **Sales Item** or **Component** forecast for the various periods.  
  
7.  On the **Matrix Options** FastTab, set the time interval in the **View by** field to change the period that is displayed in each column. You can select from the following intervals: **Day**, **Week**, **Month**, **Quarter**, **Year**, or the **Accounting Period**, as set up in Financial Management.  
  
    > [!NOTE]  
    >  You should consider which time interval that you want to use for future forecasts so that the time interval is consistent throughout. When you enter a forecast quantity, it is valid on the first day of the time interval that you select. For example, if you select a month, then you enter the forecast quantity on the first day of the month. If you select a quarter, then you enter the forecast quantity on the first day of the first month in the quarter.  
  
8.  In the **View as** field, select how the forecast quantities are shown for the time interval. If you select **Net Change**, then the net change in balance is displayed for the time interval. If you select **Balance at Date**, then the window displays the balance as of the last day in the time interval.  
  
> [!NOTE]  
>  You can also edit an existing forecast. In the **Production Forecast Matrix** window, On the **Actions** tab, choose **Copy Production Forecast** and populate the **Production Forecast** window with an existing forecast. You can then edit quantities as appropriate.  
  
## See Also  
 [Production Forecast-duplicate](../FullExperience/\($%20N_99000919%20Production%20Forecast%20$\)-duplicate.md)   
 [About Forecasting Functionality](../FullExperience/about-forecasting-functionality.md)