---
title: Installing Power BI apps for Business Central
description: Learn how to install Power BI apps for your Business Central data.
author: kennieNP
ms.topic: get-started
ms.devlang: al
ms.search.keywords: analysis, reporting, business intelligence, KPI, installation, administration
ms.date: 10/29/2024
ms.author: kepontop
ms.service: dynamics-365-business-central
---

# Install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for Business Central

**TODO**: Add note about 2024 release wave 2 (25.1). Is an include file in the PR for PBI sales app

In this article, you learn how to install the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)]. The apps are specific to each functional area of [!INCLUDE [prod_short](includes/prod_short.md)] and include APIs for reading data, [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic models and reports, and pages that embeds the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports in the [!INCLUDE [prod_short](includes/prod_short.md)] client including navigation links from relevant role centers.


## Prerequisites

To install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)], you need to have
- an environment in [!INCLUDE [prod_short](includes/prod_short.md)] online (it is already set up to integrate with [!INCLUDE [powerbi-name](includes/powerbi-name.md)].)
- a [!INCLUDE [powerbi-pro](includes/powerbi-pro-license-name.md)] license for the user who is installing the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app, the user who will be used for refreshing the data, and for each user who will access the reports. For more information, see [Get started with [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports in [!INCLUDE [prod_short](includes/prod_short.md)]](across-working-with-powerbi.md#get-started).


## Installing a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app 

[!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps are available for the following functional areas in [!INCLUDE [prod_short](includes/prod_short.md)]:
- Finance
- Sales
- Purchasing
- Inventory
- Inventory Valuation
- Warehouse
- Projects

Each app consists of two parts:
- A connector (AL) app that contains APIs, setup pages, and embed pages. This comes pre-installed with [!INCLUDE [prod_short](includes/prod_short.md)].
- A [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app that contains a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic model and [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports.

Both apps needs to be installed and configures for the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports to work on a functional area.

### Installing the connector (AL) app

The connector apps comes pre-installed with [!INCLUDE [prod_short](includes/prod_short.md)].

### Installing a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app

The template apps are available to install from Microsoft AppSource.

To install or update one or more of the template app, go to one of the install links in the table below and select "Get it now".

| To get the template app for... | Use this install link                             | 
|--------------------------------| ------------------------------------------------- | 
| Finance                        | https://aka.ms/bc-pbi-finance-app                 |
| Sales                          | https://aka.ms/bc-pbi-sales-app                   | 
| Purchasing                     | https://aka.ms/bc-pbi-purchase-app                |
| Inventory                      | https://aka.ms/bc-pbi-inventory-app               |
| Inventory Valuation            | https://aka.ms/bc-pbi-inventory-valuation-app     | 
| Manufacturing                  | https://aka.ms/bc-pbi-manufacturing-valuation-app |
| Projects                       | https://aka.ms/bc-pbi-projects-valuation-app      |

You'll first have to sign in to Microsoft AppSource using your Power BI account name and password, if you aren't already signed in. Follow the online instructions to get the app installed in Power BI.

Once installed, the Business Central Power BI app appears under Apps in Power BI. A workspace with the same name is also installed for configuring the app.


When installing the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app in your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] subscription, you need to choose a workspace for the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic model and reports. It is recommended to use one workspace for each app as this makes it easier to setup functional boundaries with access controls for which users or user groups are able to access the reports. 

The [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps currently work per company in [!INCLUDE [prod_short](includes/prod_short.md)]. If you have multiple companies in your [!INCLUDE [prod_short](includes/prod_short.md)] environment, then you need to install and setup a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app for each company.

> [!IMPORTANT]
> To install a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app, you need a [!INCLUDE [powerbi-pro](includes/powerbi-pro-license-name.md)] license.

## Get the latest data

Each [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app is based on a semantic model (also known as a dataset) that gets data from [!INCLUDE [prod_short](includes/prod_short.md)] APIs. You want to make sure that the data in your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports is up to date with the data in [!INCLUDE [prod_short](includes/prod_short.md)]. This concept is referred to as *refreshing* the model. Depending on how your organization has set up [!INCLUDE [powerbi-name](includes/powerbi-name.md)], refreshing might not happen automatically. There are two ways to refresh data: manually or by scheduling a refresh. Manual refreshing is done on-demand, as needed. Scheduled refreshing lets you refresh automatically at defined time intervals.

For more information, see [Refresh [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic models](https://learn.microsoft.com/dynamics365/business-central/across-working-with-powerbi#work-with-power-bi-reports).


## See also

[Introduction to Business Central and Power BI](admin-powerbi.md)   
[Work with Power BI reports](across-working-with-powerbi.md)   
