---
title: Using the Sales and Inventory Forecast Extension to Manage Inventory | Microsoft Docs
description: This extension helps you predict sales, get a clear overview of expected stock-outs, and even helps you create replenishment requests to vendors.
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: app, add-in, manifest, customize, budget
ms.date: 04/01/2020
ms.author: edupont

---
# The Sales and Inventory Forecast Extension
Inventory management is a trade-off between customer service and managing your cost. On one hand, a low inventory requires less working capital, but, on the other hand, stock-outs potentially lead to missed sales. The Sales and Inventory Forecast extension predicts potential sales using historical data and gives a clear overview of expected stock-outs. Based on the forecast, the extension helps create replenishment requests to your vendors and saves you time.  

## Setting up Forecasting
In [!INCLUDE[d365fin](includes/d365fin_md.md)], the connection to [Azure AI](https://azure.microsoft.com/overview/ai-platform/) is already set up for you. But you can configure the forecast to use a different type of period to report by, such as changing from forecasting by month to forecasting by quarter. You can also choose the number of periods to calculate the forecast by, depending on how granular you want the forecast to be. We suggest that you forecast by month and with a 12 month horizon for the forecast. 

> [!TIP]  
>   Consider the length of the periods that the service will use in its calculations. The more data you provide, the more accurate the predictions will be. Also, watch out for large variances in periods. They will also impact predictions. If Azure AI does not find enough data, or the data varies a lot, the service will not make a prediction.

## Using the Forecasts
The extension uses Azure AI to predict future sales based on your sales history to help you avoid inventory shortage. For example, when you choose an item on the **Items** page, the chart in the **Item Forecast** pane shows the estimated sales of this item in the coming period. This way you can see if you are likely to run out of stock of the item soon.  

You can also use the extension to suggest when to stock up on inventory. For example, if you create a purchase order for Fabrikam because you want to buy their new desk chair, the Sales and Inventory Forecast extension will suggest that you also restock on the LONDON swivel chair that you usually buy from this vendor. This is because the extension forecasts that you will run out of stock of the LONDON swivel chair in the coming two months, so you might want to order more chairs already now.  

## Design details
Subscriptions for [!INCLUDE[d365fin](includes/d365fin_md.md)] come with access to several predictive web services in all regions where [!INCLUDE[d365fin](includes/d365fin_md.md)] is available. For more information, see the Microsoft Dynamics 365 Business Central Licensing Guide. The guide is available for download on the [Business Central](https://dynamics.microsoft.com/en-us/business-central/overview/) website. 

These web services are stateless, meaning they use data only to calculate predictions on demand. They do not store data.

> [!NOTE]  
>   You can also use your own predictive web service instead of ours. For more information, see [Create and use your own predictive web service for sales and inventory forecasts](#AnchorText). 

### Data required for forecast
To make predictions about future sales, the web service requires quantitative data about past sales. That data comes from the **Posting Date**, **Item No**, and **Quantity** fields on the **Item Ledger Entries** page, where:
-    The entry type is "Sale."
- The posting date is between the date that is calculated based on the values in the **Historical Periods** and **Period Type** fields on the **Sales and Inventory Forecast Setup** page and the work date.

Before using the web service [!INCLUDE[d365fin](includes/d365fin_md.md)] compresses transactions by **Item No.** and **Posting Date** based on the value in the **Period Type** field in the **Sales and Inventory Forecast Setup** page.

## <a name="AnchorText"> </a>Create and use your own predictive web service for sales and inventory forecasts
You can also create your own predictive web service based on a public model named **Forecasting model for Microsoft Business Central**. This predictive model is available online in the Azure AI Gallery. To use the model, follow these steps:  

1. Open a browser and go to the [Azure AI Gallery](https://go.microsoft.com/fwlink/?linkid=828352).  
2. Search for **Forecasting Model for Microsoft Business Central**, and then open the model in Azure Machine Learning Studio.  
3. Use your Microsoft account to sign up for a workspace, and then copy the model.  
4. Run the model, and publish it as a web service.  
5. Make a note of the API URL and API key. You will use these credentials for a cash flow setup.  
6. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales and Inventory Forecast Setup**, and then choose the related link.  
7. Expand the **General** FastTab, and then fill in the API URL and API key fields.  


## See Also
[Sales](sales-manage-sales.md)  
[Inventory](inventory-manage-inventory.md)  
[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)  
