---
title: Setting up cash flow analysis
description: Use Accountant Role Center charts to analyze the flow of money in your business, including expenses and income, liquidity, and cash receipts minus cash payments.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: money flow, expense and income, liquidity, cash receipts minus cash payments, Cartera, funds
ms.search.form: 846, 847, 849, 851, 855, 862, 869, 1818
ms.date: 07/01/2024
ms.service: dynamics-365-business-central

---
# Setting up cash flow analysis

If you want some help to decide what to do with your cash, have a look at the charts on the Accountant Role Center:

* **Cash Cycle**  
* **Income & Expense**  
* **Cash Flow**  
* **Cash Flow Forecasts**  

This article describes where the data in the charts comes from and, if necessary, what to do to start using the charts.
<br><br>  

> [!Video https://learn-video.azurefd.net/vod/player?id=4ecab63b-f107-4666-b88f-656a133a0f78]

## The Cash Cycle and Income & Expense charts

The **Cash Cycle** and **Income & Expense** charts are ready to go, based on the Chart of Accounts and financial reports. The accounts are where the data comes from, and financial reports calculate the relationship between sales and receivables. Some accounts and financial reports are provided. You can use them as-is, change them, and add new ones. If you add G/L accounts to your chart of accounts, for example, by importing them from QuickBooks, map the accounts on the **Financial Reports** page for the following reports:

| Financial report name | Where it's used |
| --- | --- |
| **I_CACYCLE** |Cash Cycle |
| **I_CASHFLOW** |Cash Flow |
| **I_INCEXP** |Income & Expense |
| **I_MINTRIAL** |As an income statement if you don't use the chart of accounts |

> [!NOTE]
> It's a good idea to keep the calculations that are provided for the financial report.

Enter accounts in the **Totaling** field for **Total Revenue**, **Total Receivables**, **Total Payables**, and **Total Inventory**. To map to a range of accounts, enter the account numbers separated by ".." as in **1111..4444**. Alternately, to map to specific accounts, enter the account numbers separated by a vertical bar as in **2222|3333|5555**.  

> [!TIP] 
> Verify your mapping by choosing the **Overview** action.  

## Set up the Cash Flow chart

The Cash Flow chart is based on:  

* A chart of cash flow accounts.
* One or more cash flow setups. These setups specify the accounts to use for general ledger, purchases, sales, services, and fixed assets.  

To help you get going, [!INCLUDE [prod_short](includes/prod_short.md)] provides some accounts and cash flow setups. You can add, change, or remove them.  

To set up the accounts, search for **Chart of Cash Flow Accounts**, choose the link, and then fill in the fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Repeat these steps for **Cash Flow Setup**.

## Set up cash flow forecasts

The **Cash Flow Forecast** chart uses cash flow accounts, cash flow setups, and cash flow forecasts. Some are provided, however, you can set up your own by using an assisted setup guide. The guide helps you specify things like:

* When to update the forecast
* Which accounts to base it on
* When you pay taxes
* Whether to turn on [Azure AI](https://azure.microsoft.com/overview/ai-platform/).  

Cash flow forecasts can use Azure AI to create a more comprehensive forecast. The connection to Azure AI is already set up for you. You just need to turn it on. When you sign in to [!INCLUDE[prod_short](includes/prod_short.md)], a notification displays in a blue bar and provides a link to the default cash flow setup. The notification displays only once. If you close it, but then decide to turn on Azure AI, you can use the assisted setup guide or a manual process.  

> [!NOTE]
>
> Alternatively, you can use your own predictive web service. For more information, see [Create and use your own predictive web service for cash flow forecasts](#AnchorText).  

To use the assisted setup guide:  

1. In the Accountant Role Center, under the **Cash Flow Forecast** chart, choose the **Open Assisted Setup** action.
2. Fill in the fields in each step of the guide. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Back in the Accountant Role Center, choose the **Recalculate Forecast** action under the **Cash Flow Forecast** chart.

To use a manual process:  

1. In the Accountant Role Center, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Cash Flow Setup**, then choose the related link.
2. Expand the **Azure AI** FastTab, then choose the **Azure AI Enabled** field.
3. Back in the Accountant Role Center, choose the **Recalculate Forecast** action under the **Cash Flow Forecast** chart.

> [!TIP]  
> Consider the length of the periods that the service will use in its calculations. The more data you provide, the more accurate the predictions will be. Also, watch out for large variances in periods. They will also impact predictions. If Azure AI does not find enough data, or the data varies a lot, the service will not make a prediction.  

## Design details

Subscriptions for [!INCLUDE[prod_short](includes/prod_short.md)] come with access to several predictive web services in all regions where [!INCLUDE[prod_short](includes/prod_short.md)] is available. Learn more at the Microsoft Dynamics 365 Business Central Licensing Guide. The guide is available for download on the [Business Central]( https://www.microsoft.com/dynamics-365/products/business-central/) website.

These web services are stateless, meaning they use data only to calculate predictions on demand. They don't store data.

> [!NOTE]
>
> You can use your own predictive web service instead of ours. For more information, see [Create and use your own predictive web service for cash flow forecasts](#AnchorText).

### Data required for forecast

To make predictions about future revenue and expenses, web services require historical data from receivables, payables, and taxes.

#### Receivables

**Due Date**, **Amount (LCY)** fields of the **Customer Ledger Entries** page, where:

* The document type is *Invoice* or *Credit Memo*.
* The due date is between date that is calculated based on the values in the **Historical Periods** and **Period Type** fields on the **Cash Flow Setup** page and the work date.

Before it uses the predictive web-service, [!INCLUDE[prod_short](includes/prod_short.md)] compresses transactions by **Due Date** based on the value in the **Period Type** field on the **Cash Flow Setup** page.

#### Payables

**Due Date**, **Amount (LCY)** fields on the **Vendor Ledger Entries** page, where:

* The document type is *Invoice* or *Credit Memo*.
* The due date is between date that is calculated based on values in the **Historical Periods** and **Period Type** fields on the **Cash Flow Setup** page and the work date.

Before it uses the predictive web-service, [!INCLUDE[prod_short](includes/prod_short.md)] compresses transactions by **Due Date** based on the value in the **Period Type** field on the **Cash Flow Setup** page.

#### Tax

**Document Date**, **Amount** fields on the **VAT (Tax) Ledger Entries** page, where:

* The document type is *sales*.
* The document date is between the date that is calculated based on values in the **Historical Periods** and **Period Type** fields on the **Cash Flow Setup** page and the work date.

Before it uses the predictive web-service, [!INCLUDE[prod_short](includes/prod_short.md)] compresses transactions by **Document Date** based on value in the **Period Type** field in the **Cash Flow Setup** page.

## <a name="AnchorText"></a>Create and use your own predictive web service for cash flow forecasts

For [!INCLUDE[prod_short](includes/prod_short.md)] online, the model is published by Microsoft and connected to the Microsoft subscription. For other deployment options, you have to create Machine Learning resources in your own Azure subscription. You can find sample steps in the [sample repo](https://github.com/microsoft/BCTech/tree/master/samples/MachineLearning). The purpose of this task is to get the API URI and API key.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Cash Flow Setup**, and then choose the related link.  
2. Expand the **Azure AI** FastTab, and then fill in the fields, including the API URL and API key provided from Azure Machine Learning studio. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. In the Accountant Role Center, choose the **Recalculate Forecast** action under the **Cash Flow Forecast** chart.

## Related information

[Analyzing Cash Flow in Your Company](finance-analyze-cash-flow.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Forecasting API overview](/dynamics365/business-central/dev-itpro/developer/ml-forecasting-api-overview)

[!INCLUDE[footer-include](includes/footer-banner.md)]
