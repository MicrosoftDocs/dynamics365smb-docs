---
title: Installing Power BI apps for Business Central
description: Learn how to install Power BI apps for your Business Central.
author: kennieNP
ms.topic: get-started
ms.devlang: al
ms.search.keywords: analysis, reporting, business intelligence, KPI, installation, administration
ms.date: 12/06/2024
ms.author: kepontop
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)]

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This article describes how to install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)]. The apps are specific to each functional area of [!INCLUDE [prod_short](includes/prod_short.md)]. The apps include:

- APIs for reading data.
- [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic models and reports.
- Pages that embed the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports in [!INCLUDE [prod_short](includes/prod_short.md)].
- Navigation links on Role Centers and in the Role Explorer.

## Prerequisites

To install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)], you must have:

- An environment in [!INCLUDE [prod_short](includes/prod_short.md)] online (it comes ready to integrate with [!INCLUDE [powerbi-name](includes/powerbi-name.md)].)

- Entitlements/permissions in [!INCLUDE [powerbi-name](includes/powerbi-name.md)] to:

    - Install template apps from AppSource.
    - Use shared workspaces.

The prerequisites for [!INCLUDE [powerbi-name](includes/powerbi-name.md)] can be met with a [!INCLUDE [powerbi-pro](includes/powerbi-pro-license-name.md)] license for the following users:

   - The user who installs the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app.
   - The user who refreshes the data.
   - Each user who accesses the reports.

An alternative to using [!INCLUDE [powerbi-pro](includes/powerbi-pro-license-name.md)] licenses is to use [!INCLUDE [powerbi-name](includes/powerbi-name.md)] or [!INCLUDE [fabric-name](includes/fabric-name.md)] Premium capacity.

To learn more, go to [Get started with [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports in [!INCLUDE [prod_short](includes/prod_short.md)]](across-working-with-powerbi.md#get-started).

## Installing a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app

[!INCLUDE [powerbi-apps-overview](includes/powerbi-apps-overview.md)]

Each app consists of two parts:

- A connector (AL) app that contains APIs, setup pages, and embed pages. Connectors are preinstalled with [!INCLUDE [prod_short](includes/prod_short.md)].
- A [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app that contains a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic model and [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports.

You must install and configure both apps for the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports to work.

### Installing the connector (AL) app

The connector apps are preinstalled with [!INCLUDE [prod_short](includes/prod_short.md)].

### Installing a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app

Template apps are available to install from Microsoft AppSource. To install or update one or more of the template apps, go to one of the install links in the following table and select **Get it now**.

| To get the template app for... | Use this install link             |
|--------------------------------| --------------------------------- |
| Finance                        | https://aka.ms/bc-pbi-finance-app                 |
| Sales                          | https://aka.ms/bc-pbi-sales-app                   |
| Purchasing                     | https://aka.ms/bc-pbi-purchase-app                |
| Inventory                      | https://aka.ms/bc-pbi-inventory-app               |
| Inventory Valuation            | https://aka.ms/bc-pbi-inventory-valuation-app     | 
| Manufacturing                  | https://aka.ms/bc-pbi-manufacturing-valuation-app |
| Projects                       | https://aka.ms/bc-pbi-projects-valuation-app      |

Sign in to Microsoft AppSource using your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] account credentials. Follow the instructions to install the app in [!INCLUDE [powerbi-name](includes/powerbi-name.md)].

After you install it, the [!INCLUDE [prod_short](includes/prod_short.md)] [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app appears under **Apps** in [!INCLUDE [powerbi-name](includes/powerbi-name.md)], and there's a workspace with the same name that you can use to configure the app.

When you install the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app in your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] subscription, you must choose a workspace for the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic model and reports. We recommend that you use one workspace for each app because it's easier to set up functional boundaries with access controls for users and user groups.

The [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps currently work per company in [!INCLUDE [prod_short](includes/prod_short.md)]. If you have multiple companies in your [!INCLUDE [prod_short](includes/prod_short.md)] environment, you must install and set up a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app for each company.

> [!IMPORTANT]
> To install a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app, you need a [!INCLUDE [powerbi-pro](includes/powerbi-pro-license-name.md)] license.

## Run the Connect to Power BI assisted setup guide

After you install your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps, you can configure them to suit your business:

- Get help with the set-up process by using the **Connect to Power BI** assisted setup guide.
- Set up things yourself on the **[Power BI Connector Setup](https://businesscentral.dynamics.com?page=36951)** page.

The assisted setup guide helps you configure the following components:

1. [Calendar Type](#configure-the-calendar-type)
1. [UTC Offset](#specify-the-utc-offset)
1. [Date Table Range](#set-up-a-date-table-range)
1. [Work Days](#specify-work-days)
1. [Report Mapping](#map-embedded-reports)

### Configure the calendar type

Choose the type of calendar the year boundaries apply to.

- **Fiscal**: A 12-month calendar that begins in any month and ends 12 months after.
- **Standard**: A 12-month calendar that begins on January 1 and ends on December 31.
- **Weekly**: A calendar that supports 445, 454, or 544 week groupings. The first and last day of the year might not correspond to a first and last day of a month, respectively.

> [!IMPORTANT]
> By default, all [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports are configured to use Fiscal Calendar date fields and Fiscal Time Intelligence measures.

<!-- If you choose a calendar type other than Fiscal, you will need to edit the Power BI reports and change the date field references and measure references accordingly.  -->

### Specify the UTC offset

The UTC offset defines the UTC time zone in the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] date table.

The UTC offset allows your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic model to accurately calculate what the current day is in respect to your geographical location. This setting is necessary because your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps might be hosted in a data center located in a different region.

UTC offsets are based on [!INCLUDE [prod_short](includes/prod_short.md)] time zones.

### Set up a date table range

The **Starting Date** and **Ending Date** fields are set automatically based on your accounting periods in [!INCLUDE [prod_short](includes/prod_short.md)]. Based on these dates, [!INCLUDE [powerbi-name](includes/powerbi-name.md)] generates a series of continuous dates for your date table.

> [!NOTE]
> If your budgets extend past the last date in your Account Period table, you must manually set the ending date to accommodate the extended range.

### Specify work days

You can define the days of the week you consider as work days. The default setting is Monday to Friday.

### Map embedded reports

To enable the embedded report pages in [!INCLUDE [prod_short](includes/prod_short.md)], you must set up links to the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps in the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] service.

1. For each functional area in [!INCLUDE [prod_short](includes/prod_short.md)], select the ellipsis to open the **Select Power BI Workspace** page.
1. Select the workspace where you store the corresponding [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app.
1. Select the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] report (app) you want to map.

## Connect the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic models to [!INCLUDE [prod_short](includes/prod_short.md)]

Do this part of the configuration in the semantic models in your [Power BI service](https://app.powerbi.com).

Each semantic model requires two parameters:

- Environment (holds the environment name)
- Company (holds the company name. The company parameter is case sensitive. )

You can find these values in the connection details of the assisted setup guide or on the [Power BI Connector Setup](https://businesscentral.dynamics.com?page=36951) page.

## Get the latest data (refresh the semantic model)

Each [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app is based on a semantic model (also known as a dataset) that gets data from [!INCLUDE [prod_short](includes/prod_short.md)] APIs. Make sure that the data in your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports is up to date with the data in [!INCLUDE [prod_short](includes/prod_short.md)]. This concept is referred to as *refreshing* the model. Depending on your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] setup, refreshing might not happen automatically. You can refresh data manually, or by scheduling a refresh. You can do a manual refresh at any time. A scheduled refresh lets you refresh data automatically at defined time intervals.

To learn more, go to [Refresh [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic models](/dynamics365/business-central/across-working-with-powerbi#work-with-power-bi-reports).

## Updating a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app

The [!INCLUDE [prod_short](includes/prod_short.md)] [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps are available as template app on AppSource. When a new version of a template app becomes available, we notify you in two ways:

- An update banner displays in the [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)] informing you that a new version is available.
- A notification displays in Power BI's notification pane.

When you update a template app, it's important that you're aware of your options and how they might overwrite earlier changes to the reports. You can choose to:

- Update the workspace and the app.
- Update workspace content only, without updating the app.
- Install another copy of the app in a new workspace.

To learn more, go to [Install, share, and update template apps in your organization](/power-bi/connect-data/service-template-apps-install-distribute#update-a-template-app).

## Related information

[Power BI apps by functional area](across-powerbi-apps-by-functional-area.md)  
[Introduction to Business Central and Power BI](admin-powerbi.md)  
[Work with Power BI reports](across-working-with-powerbi.md)  
