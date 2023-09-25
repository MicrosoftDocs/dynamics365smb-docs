---
title: Setting up Cash Flow Analysis (contains video)
description: Use Accountant Role Center charts to analyze the flow of money in your business, including expenses and income, liquidity, and cash receipts minus cash payments.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: money flow, expense and income, liquidity, cash receipts minus cash payments, Cartera, funds
ms.search.form: 846, 847, 849, 851, 855, 862, 869, 1818
ms.date: 08/23/2022
ms.author: bholtorf
---
# Setting Up Cash Flow Analysis

If you want some help to decide what to do with your cash, have a look at the charts on the Accountant Role Center:

* **Cash Cycle**  
* **Income & Expense**  
* **Cash Flow**  
* **Cash Flow Forecasts**  

This article describes where the data in the charts comes from and, if necessary, what to do to start using the charts.
<br><br>  

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4mJhc?rel=0]

## The Cash Cycle and Income & Expense charts

The **Cash Cycle** and **Income & Expense** charts are ready to go, based on the Chart of Accounts and financial reports. The accounts are where the data comes from, and financial reports calculate the relationship between sales and receivables. Some accounts and financial reports are provided. You can use them as-is, change them, and add new ones. If you add G/L accounts to your chart of accounts, for example, by importing them from QuickBooks, you'll need to map to the accounts on the **Financial Reports** page for the following reports:

| Financial Report Name | Where it's used |
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

To help you get going, some accounts and cash flow setups are provided. You can add, change, or remove them.  

To set up the accounts, search for **Chart of Cash Flow Accounts**, choose the link, and then fill in the fields. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)] Repeat these steps for **Cash Flow Setup**.

## Set up cash flow forecasts

The **Cash Flow Forecast** chart uses cash flow accounts, cash flow setups, and cash flow forecasts. Some are provided, however, you can set up your own by using an assisted setup guide. The guide helps you specify things like how often to update the forecast, the accounts to base it on, information about when you pay taxes, and whether to turn on [Azure AI](https://azure.microsoft.com/overview/ai-platform/).  

Cash flow forecasts can use Azure AI to create a more comprehensive forecast. The connection to Azure AI is already set up for you. You just need to turn it on. When you sign in to [!INCLUDE[prod_short](includes/prod_short.md)], a notification displays in a blue bar and provides a link to the default cash flow setup. The notification displays only once. If you close it but then decide to turn Azure AI  on, you can use the assisted setup guide or a manual process.  

> [!NOTE]
>
> Alternatively, you can use your own predictive web service. For more information, see [Create and use your own predictive web service for cash flow forecasts](#AnchorText).  

To use the assisted setup guide:  

1. In the Accountant Role Center, under the **Cash Flow Forecast** chart, choose the **Open Assisted Setup** action.
2. Fill in the fields in each step of the guide. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Back in the Accountant Role Center, choose the **Recalculate Forecast** action under the **Cash Flow Forecast** chart.

To use a manual process:  

1. In the Accountant Role Center, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Flow Setup**, then choose the related link.
2. Expand the **Azure AI** FastTab, then choose the **Azure AI Enabled** field.
3. Back in the Accountant Role Center, choose the **Recalculate Forecast** action under the **Cash Flow Forecast** chart.

> [!TIP]  
> Consider the length of the periods that the service will use in its calculations. The more data you provide, the more accurate the predictions will be. Also, watch out for large variances in periods. They will also impact predictions. If Azure AI does not find enough data, or the data varies a lot, the service will not make a prediction.  

## Design details

Subscriptions for [!INCLUDE[prod_short](includes/prod_short.md)] come with access to several predictive web services in all regions where [!INCLUDE[prod_short](includes/prod_short.md)] is available. Learn more at the Microsoft Dynamics 365 Business Central Licensing Guide. The guide is available for download on the [Business Central](https://dynamics.microsoft.com/business-central/overview/) website.

These web services are stateless, meaning they use data only to calculate predictions on demand. They do not store data.

> [!NOTE]
>
> You can use your own predictive web service instead of ours. For more information, see [Create and use your own predictive web service for cash flow forecasts](#AnchorText).

### Data required for forecast

To make predictions about future revenue and expenses, web services require historical data from receivables, payables, and taxes.

#### Receivables

**Due Date**, **Amount (LCY)** fields of the **Customer Ledger Entries** page, where:

* The document type is *Invoice* or *Credit Memo*.
* The due date is between date that is calculated based on the values in the **Historical Periods** and **Period Type** fields on the **Cash Flow Setup** page and the work date.

Before using the predictive web-service, [!INCLUDE[prod_short](includes/prod_short.md)] compresses transactions by **Due Date** based on the value in the **Period Type** field on the **Cash Flow Setup** page.

#### Payables

**Due Date**, **Amount (LCY)** fields on the **Vendor Ledger Entries** page, where:

* The document type is *Invoice* or *Credit Memo*.
* The due date is between date that is calculated based on values in the **Historical Periods** and **Period Type** fields on the **Cash Flow Setup** page and the work date.

Before using the predictive web-service, [!INCLUDE[prod_short](includes/prod_short.md)] compresses transactions by **Due Date** based on the value in the **Period Type** field on the **Cash Flow Setup** page.

#### Tax

**Document Date**, **Amount** fields on the **VAT (Tax) Ledger Entries** page, where:

* The document type is *sales*.
* The document date is between the date that is calculated based on values in the **Historical Periods** and **Period Type** fields on the **Cash Flow Setup** page and the work date.

Before using the predictive web-service, [!INCLUDE[prod_short](includes/prod_short.md)] compresses transactions by **Document Date** based on value in the **Period Type** field in the **Cash Flow Setup** page.

## <a name="AnchorText"></a>Create and use your own predictive web service for cash flow forecasts

You can also create your own predictive web service based on a public model named **Forecasting model for Microsoft Business Central**. This predictive model is available online in the Azure AI Gallery. To use the model, follow these steps:  

1. Open a browser and go to the [Azure AI Gallery](https://go.microsoft.com/fwlink/?linkid=828352).  
2. Search for **Forecasting Model for Microsoft Business Central**, and then open the model in Microsoft Azure Machine Learning studio.  
3. Use your Microsoft account to sign up for a workspace, and then copy the model.  
4. Run the model, and publish it as a web service.  
5. Make a note of the API URL and API key. You will use these credentials for a cash flow setup.  
6. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cash Flow Setup**, and then choose the related link.  
7. Expand the **Azure AI** FastTab, and then fill in the fields, including the API URL and API key provided from Azure Machine Learning studio. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
8. In the Accountant Role Center, choose the **Recalculate Forecast** action under the **Cash Flow Forecast** chart.

## See also

[Analyzing Cash Flow in Your Company](finance-analyze-cash-flow.md)  
[Setting Up Finance](finance-setup-finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
