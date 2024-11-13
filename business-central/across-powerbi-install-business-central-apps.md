---
title: Installing Power BI apps for Business Central
description: Learn how to install Power BI apps for your Business Central.
author: kennieNP
ms.topic: get-started
ms.devlang: al
ms.search.keywords: analysis, reporting, business intelligence, KPI, installation, administration
ms.date: 10/29/2024
ms.author: kepontop
ms.service: dynamics-365-business-central
---

# Install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)]

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This article describes how to install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)]. The apps are specific to each functional area of [!INCLUDE [prod_short](includes/prod_short.md)]. The apps include:

- APIs for reading data.
- [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic models and reports.
- Pages that embed the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports in [!INCLUDE [prod_short](includes/prod_short.md)].
- Navigation links on role centers and in the Role Explorer.

## Prerequisites

To install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)], you need to have:

- An environment in [!INCLUDE [prod_short](includes/prod_short.md)] online (it comes ready to integrate with [!INCLUDE [powerbi-name](includes/powerbi-name.md)].)
- A [!INCLUDE [powerbi-pro](includes/powerbi-pro-license-name.md)] license for the following users:

   - The user who installs the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app.
   - The user who you use to refresh the data.
   - Each user who accesses the reports.

To learn more, go to [Get started with [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports in [!INCLUDE [prod_short](includes/prod_short.md)]](across-working-with-powerbi.md#get-started).

## Installing a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app

[!INCLUDE [powerbi-apps-overview](includes/powerbi-apps-overview.md)]

Each app consists of two parts:

- A connector (AL) app that contains APIs, setup pages, and embed pages. Connectors are preinstalled with [!INCLUDE [prod_short](includes/prod_short.md)].
- A [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app that contains a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic model and [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports.

You must install and configure both apps for the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports to work on a functional area.

### Installing the connector (AL) app

The connector apps are preinstalled with [!INCLUDE [prod_short](includes/prod_short.md)].

### Installing a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app

Template apps are available to install from Microsoft AppSource. To install or update one or more of the template apps, go to one of the install links in the following table and select **Get it now**.

| To get the template app for... | Use this install link             |
|--------------------------------| --------------------------------- |
| Finance                        | https://aka.ms/bc-pbi-finance-app |
| Sales                          | https://aka.ms/bc-pbi-sales-app   |
| Purchasing                     | https://aka.ms/bc-pbi-purchase-app|
| Inventory                      | https://aka.ms/bc-pbi-inventory-app |
| Inventory Valuation | https://aka.ms/bc-pbi-inventory-valuation-app| 
| Manufacturing   | https://aka.ms/bc-pbi-manufacturing-valuation-app |
| Projects        | https://aka.ms/bc-pbi-projects-valuation-app      |

Sign in to Microsoft AppSource using your Power BI account name and password. Follow the online instructions to get the app installed in Power BI.

After you install it, the Business Central Power BI app appears under Apps in Power BI, and there's a workspace with the same name that you can use to configure the app.

When installing the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app in your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] subscription, you must choose a workspace for the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic model and reports. We recommend that you use one workspace for each app it's easier to set up functional boundaries with access controls for users and user groups.

The [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps currently work per company in [!INCLUDE [prod_short](includes/prod_short.md)]. If you have multiple companies in your [!INCLUDE [prod_short](includes/prod_short.md)] environment, you must install and set up a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app for each company.

> [!IMPORTANT]
> To install a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app, you need a [!INCLUDE [powerbi-pro](includes/powerbi-pro-license-name.md)] license.

## Get the latest data

Each [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app is based on a semantic model (also known as a dataset) that gets data from [!INCLUDE [prod_short](includes/prod_short.md)] APIs. Make sure that the data in your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports is up to date with the data in [!INCLUDE [prod_short](includes/prod_short.md)]. This concept is referred to as *refreshing* the model. Depending on your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] setup, refreshing might not happen automatically. You can refresh data manually, or by scheduling a refresh. You can do a manual refresh at any time. A scheduled refresh lets you refresh data automatically at defined time intervals.

To learn more, go to [Refresh [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic models](/dynamics365/business-central/across-working-with-powerbi#work-with-power-bi-reports).

## See also

[Power BI apps by functional area](across-powerbi-apps-by-functional-area.md)  
[Introduction to Business Central and Power BI](admin-powerbi.md)  
[Work with Power BI reports](across-working-with-powerbi.md)  
