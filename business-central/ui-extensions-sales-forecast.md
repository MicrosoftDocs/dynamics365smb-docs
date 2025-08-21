---
title: Using the Sales and Inventory Forecast extension to manage inventory
description: This extension helps you predict sales, get a clear overview of expected stock-outs, and even helps you create replenishment requests to vendors.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: app, add-in, manifest, customize, budget
ms.search.form: 1850, 1851, 1853, 
ms.date: 08/28/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# The Sales and Inventory Forecast extension

Inventory management is a trade-off between customer service and managing your cost. On one hand, a low inventory requires less working capital, but, on the other hand, stock-outs potentially lead to missed sales. The Sales and Inventory Forecast extension predicts potential sales using historical data and gives a clear overview of expected stock-outs. Based on the forecast, the extension helps create replenishment requests to your vendors and saves you time.  

## Setting up forecasting

In [!INCLUDE[prod_short](includes/prod_short.md)], the connection to [Azure AI](https://azure.microsoft.com/overview/ai-platform/) is already set up for you. But you can configure the forecast to use a different type of period to report by, such as changing from forecasting by month to forecasting by quarter. You can also choose the number of periods to calculate the forecast by, depending on how granular you want the forecast to be. We suggest that you forecast by month and with a 12 month horizon for the forecast.

> [!TIP]  
> Consider the length of the periods that the service will use in its calculations. The more data you provide, the more accurate the predictions will be. Also, watch out for large variances in periods. They will also impact predictions. If Azure AI does not find enough data, or the data varies a lot, the service will not make a prediction.

## Use the forecasts

The extension uses Azure AI to predict future sales based on your sales history to help you avoid inventory shortage. For example, when you choose an item on the **Items** page, the chart in the **Item Forecast** pane shows the estimated sales of this item in the coming period. This way you can see if you're likely to run out of stock of the item soon.  

You can also use the extension to suggest when to stock up on inventory. For example, you might create a purchase order for Fabrikam to buy their new desk chair. The Sales and Inventory Forecast extension might suggest that you also restock on the LONDON swivel chair that you usually buy from this vendor. The extension can forecast that you'll soon run out of stock of the LONDON swivel chair, so you might order more chairs already now.  

## Design details

Subscriptions for [!INCLUDE[prod_short](includes/prod_short.md)] come with access to several predictive web services in all regions where [!INCLUDE[prod_short](includes/prod_short.md)] is available. For more information, see the Microsoft Dynamics 365 Business Central Licensing Guide. The guide is available for download on the [Business Central](https://dynamics.microsoft.com/en-us/business-central/overview/) website.

These web services are stateless, meaning they use data only to calculate predictions on demand. They don't store data.

> [!NOTE]  
> You can also use your own predictive web service instead of ours. For more information, see [Create and use your own predictive web service for sales and inventory forecasts](#AnchorText). 

### Data required for forecast

To make predictions about future sales, the web service requires quantitative data about past sales. That data comes from the **Posting Date**, **Item No**, and **Quantity** fields on the **Item Ledger Entries** page, where:

- The entry type is "Sale."
- The posting date is between the date that is calculated based on the values in the **Historical Periods** and **Period Type** fields on the **Sales and Inventory Forecast Setup** page and the work date.

Before is uses the web service, [!INCLUDE[prod_short](includes/prod_short.md)] compresses transactions by **Item No.** and **Posting Date** based on the value in the **Period Type** field in the **Sales and Inventory Forecast Setup** page.

## <a name="AnchorText"> </a>Create and use your own predictive web service for sales and inventory forecasts

For [!INCLUDE[prod_short](includes/prod_short.md)] online, the model is published by Microsoft and connected to the Microsoft subscription. For other deployment options, you must create Machine Learning resources in your own Azure subscription. You can find sample steps in the [sample repo](https://github.com/microsoft/BCTech/tree/master/samples/MachineLearning). The purpose of this task is to get the API URI and API key.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales and Inventory Forecast Setup**, and then choose the related link.  
2. Expand the **General** FastTab, and then fill in the API URL and API key fields.

> [!NOTE]
> You can always switch back to resources managed by Microsoft by removing values from API URL and API Key fields.  

## Limitations of the Sales and Inventory Forecast extension

The Sales and Inventory Forecast extension produces aggregated forecast for all locations and variants. If you have multiple locations, for example, that represent different stores, you can't get a forecast for each location. You must distribute amounts afterwards.

Regarding throughput, we estimate that [!INCLUDE [prod_short](includes/prod_short.md)] can process approximately 50000 items in 12 hours, which is defined as the *Max Execution Timeout*. The exact number depends on the data and settings for extensions. For more information about report limits in [!INCLUDE [prod_short](includes/prod_short.md)] and how they're configured in the online service, see [Report limits in Business Central](/dynamics365/business-central/dev-itpro/administration/operational-limits-online#Reports).

The Sales and Inventory Forecast extension doesn't support filtering, means you can't split items into separate batches.

## Related information

[Sales](sales-manage-sales.md)  
[Inventory](inventory-manage-inventory.md)  
[Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md)  
[Use Artificial Intelligence in Microsoft Dynamics 365 Business Central](/training/paths/use-artificial-intelligence/)  
[Forecasting API overview](/dynamics365/business-central/dev-itpro/developer/ml-forecasting-api-overview)

[!INCLUDE[footer-include](includes/footer-banner.md)]
