---
title: Installing Power BI apps for Business Central
description: Learn how to install Power BI apps for your Business Central.
author: kennieNP
ms.topic: get-started
ms.devlang: al
ms.search.keywords: analysis, reporting, business intelligence, KPI, installation, administration
ms.date: 06/11/2025
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
- Navigation links on Role Centers and Role Explorer.

## Prerequisites

To install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)], you must have:

- An environment in [!INCLUDE [prod_short](includes/prod_short.md)] online (it comes ready to integrate with [!INCLUDE [powerbi-name](includes/powerbi-name.md)].)

- Entitlements/permissions in [!INCLUDE [powerbi-name](includes/powerbi-name.md)] to:

    - Install template apps from AppSource.
    - Use shared workspaces.

The prerequisites for [!INCLUDE [powerbi-name](includes/powerbi-name.md)] can be met with a [!INCLUDE [powerbi-pro](includes/powerbi-pro-license-name.md)] license for the following users:

   - The user who installs the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app.
   - The user who refreshes the data.
   - Each user who accesses the reports, either in the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] service or embedded in [!INCLUDE [prod_short](includes/prod_short.md)].

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

| To get the template app for... | In [!INCLUDE [prod_short](includes/prod_short.md)] versions | Use this install link |
|--------------------------------| -------------- | ------------------------------------------------ |
| Finance                        | 27.0 and later | https://aka.ms/bc-pbi-finance-app                |
| Inventory                      | 27.0 and later | https://aka.ms/bc-pbi-inventory-app              |
| Inventory Valuation            | 27.0 and later | https://aka.ms/bc-pbi-inventory-valuation-app    |
| Manufacturing                  | 27.0 and later | https://aka.ms/bc-pbi-manufacturing-app          |
| Purchasing                     | 27.0 and later | https://aka.ms/bc-pbi-purchase-app               |
| Projects                       | 27.0 and later | https://aka.ms/bc-pbi-projects-app               |
| Sales                          | 27.0 and later | https://aka.ms/bc-pbi-sales-app                  |
| Subscription Billing           | 27.0 and later | https://aka.ms/bc-pbi-subscription-billing-app   |
| Sustainability                 | 27.0 and later | https://aka.ms/bc-pbi-sustainability-app         |


| To get the template app for... | In [!INCLUDE [prod_short](includes/prod_short.md)] versions | Use this install link |
|--------------------------------| -------------- | ------------------------------------------------ |
| Finance                        | 26.2 to 26.5 | https://aka.ms/bc-pbi-finance-app-26-2             |
| Inventory                      | 26.2 to 26.5 | https://aka.ms/bc-pbi-inventory-app-26-2           |
| Inventory Valuation            | 26.2 to 26.5 | https://aka.ms/bc-pbi-inventory-valuation-app-26-2 | 
| Manufacturing                  | 26.2 to 26.5 | https://aka.ms/bc-pbi-manufacturing-app-26-2       |
| Purchasing                     | 26.2 to 26.5 | https://aka.ms/bc-pbi-purchase-app-26-2            |
| Projects                       | 26.2 to 26.5 | https://aka.ms/bc-pbi-projects-app-26-2            |
| Sales                          | 26.2 to 26.5 | https://aka.ms/bc-pbi-sales-app-26-2               |
| Subscription Billing           | 26.2 to 26.5 | https://aka.ms/bc-pbi-subscription-billing-app     |
| Sustainability                 | 26.2 to 26.5 | https://aka.ms/bc-pbi-sustainability-app-26-2      |


| To get the template app for... | In [!INCLUDE [prod_short](includes/prod_short.md)] versions | Use this install link |
|--------------------------------| ------------ | -------------------------------------------------- |
| Finance                        | 25.2 to 26.1 | https://aka.ms/bc-pbi-finance-app-25-2             |
| Inventory                      | 25.2 to 26.1 | https://aka.ms/bc-pbi-inventory-app-25-2           |
| Inventory Valuation            | 25.2 to 26.1 | https://aka.ms/bc-pbi-inventory-valuation-app-25-2 | 
| Manufacturing                  | 25.2 to 26.1 | https://aka.ms/bc-pbi-manufacturing-app-25-2       |
| Purchasing                     | 25.2 to 26.1 | https://aka.ms/bc-pbi-purchase-app-25.2            |
| Projects                       | 25.2 to 26.1 | https://aka.ms/bc-pbi-projects-app-25-2            |
| Sales                          | 25.2 to 26.1 | https://aka.ms/bc-pbi-sales-app-25-2               |

Sign in to Microsoft AppSource using your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] account credentials. Follow the instructions to install the app in [!INCLUDE [powerbi-name](includes/powerbi-name.md)].

In the authentication step, choose **OAuth2** and set the **Privacy level setting for this data source** field to **Organizational**.

:::image type="content" source="media/powerbi/power-bi-install-app-authenticate.png" alt-text="Screenshot of the Power BI app installer." lightbox="media/powerbi/power-bi-install-app-authenticate.png"::::::

After you install it, the [!INCLUDE [prod_short](includes/prod_short.md)] [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app appears under **Apps** in [!INCLUDE [powerbi-name](includes/powerbi-name.md)], and there's a workspace with the same name that you can use to configure the app.

When you install the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app in your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] subscription, you must choose a workspace for the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic model and reports. We recommend that you use one workspace for each app because it's easier to set up functional boundaries with access controls for users and user groups.

> [!IMPORTANT]
> To install a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template app, you need a [!INCLUDE [powerbi-pro](includes/powerbi-pro-license-name.md)] license.

### Need Power BI apps for multiple companies?

[!INCLUDE [powerbi-apps-per-company-include](includes/powerbi-apps-per-company-include.md)]

## Run the Connect to Power BI assisted setup guide

After you install your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps, you can configure them to suit your business:

- Get help with the set-up process by using the **Connect to Power BI** assisted setup guide.
- Set up things yourself on the [Power BI Connector Setup](https://businesscentral.dynamics.com?page=36951) page.

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

## Restrict the amount of data that loads to Power BI

If you want to restrict the amount of data that loads to the semantic model in [!INCLUDE [powerbi-name](includes/powerbi-name.md)], you can define filters on each app.

On the [Power BI Connector Setup](https://businesscentral.dynamics.com?page=36951) page, choose an app for which you want to set up data filtering. The semantic models use these settings when they refresh the data.

All apps support start and end date filtering, where you specify the start and end date of an interval.

Some apps also support other filter options, such as *Start/End Date* or *Relative Date*. With the *Relative Date* type, you can apply a custom date formula.

## Connect the Power BI semantic models to Business Central

Do this part of the configuration in the semantic models in your [Power BI service](https://app.powerbi.com).

Each semantic model requires two parameters:

- Environment (holds the environment name)
- Company (holds the company name. The company parameter is case sensitive. )

You can find these values in the connection details of the assisted setup guide or on the [Power BI Connector Setup](https://businesscentral.dynamics.com?page=36951) page.

To set or change values for the parameters, open the app workspace in your [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)]. Locate the semantic model, and choose **More options**. Now choose **Settings**, and then **Parameters**.

## Get the latest data (refresh the semantic model)

Each [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app is based on a semantic model (also known as a dataset) that gets data from [!INCLUDE [prod_short](includes/prod_short.md)] APIs. Make sure that the data in your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] reports is up to date with the data in [!INCLUDE [prod_short](includes/prod_short.md)]. This concept is referred to as *refreshing* the model. Depending on your [!INCLUDE [powerbi-name](includes/powerbi-name.md)] setup, refreshing might not happen automatically. You can refresh data manually, or by scheduling a refresh. You can do a manual refresh at any time. A scheduled refresh lets you refresh data automatically at defined time intervals.

To learn more, go to [Refresh [!INCLUDE [powerbi-name](includes/powerbi-name.md)] semantic models](/dynamics365/business-central/across-working-with-powerbi#work-with-power-bi-reports).

## Job queue entry for updating dimension set entries

For dimension set entries to show up in the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps, the job queue entry that runs the *Update Dim. Set Entries* codeunit must run at least one time. If you change dimension sets or values, the codeunit must run again. Therefore, we recommend that you run the corresponding job queue entry one time each week, or maybe once a night outside normal working hours.

## Want links to show up in Report Explorer?

The profiles (roles) selected to display in the Role Explorer control the functional areas that show in Report Explorer. To specify whether profiles display, turn on or turn off the **Enabled** and **Show in Role Explorer** toggles on the **Profiles** page.

> [!TIP]
> For the built-in profiles that show in Report Explorer, the **Description** field contains **Navigation menu only**.

## Permissions

In [!INCLUDE [prod_short](includes/prod_short.md)], the user account you use to refresh the semantic model in [!INCLUDE [powerbi-name](includes/powerbi-name.md)] must have **Read** permissions to the tables in the model. The tables are documented in the KPI article for the app. For example, for the [!INCLUDE [power-bi-sales-app-name](includes/power-bi-sales-app-name.md)], to explore the [!INCLUDE [prod_short](includes/prod_short.md)] tables that a user needs Read permissions for, go to [KPIs and measures in the Power BI Sales app](sales-powerbi-sales-kpis.md).

In the [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)], we recommend that you add multiple admins for each [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app workspace. Grant Read permissions to users who should be able to view report pages in an app.

For the embedded pages in [!INCLUDE [prod_short](includes/prod_short.md)], there are permission sets for each [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app. If you need to exclude read access to all or some of these pages, you can exclude the permission set (or permission on individual pages) for the users.

## Governance of [!INCLUDE [powerbi-name](includes/powerbi-name.md)] workspaces

Consider having the template app workspaces highly governed and not used directly for the embedded experience. To learn more, go to [Workspace governance level](/power-bi/guidance/powerbi-implementation-planning-workspaces-tenant-level-planning#workspace-governance-level).

Instead, consider having a single workspace per company that you use for the embed experience. In this workspace, keep copies or custom versions of the template reports. This helps mitigate the problem of losing report customizations when you upgrade the template app workspace. To learn more about how to copy a report to another workspace, go to [Copy reports from other workspaces](/power-bi/connect-data/service-datasets-copy-reports).

## Updating a Power BI app

The [!INCLUDE [prod_short](includes/prod_short.md)] [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps are available as template app on AppSource. When a new version of a template app becomes available, we notify you in two ways:

- An update banner displays in the [!INCLUDE [powerbi-service-name](includes/powerbi-service-name.md)] informing you that a new version is available.
- A notification displays in Power BI's notification pane.

When you update a template app, it's important that you're aware of your options and how they might overwrite earlier changes to the reports. You can choose to:

- Update the workspace and the app.
- Update workspace content only, without updating the app.
- Install another copy of the app in a new workspace.

To learn more, go to [Install, share, and update template apps in your organization](/power-bi/connect-data/service-template-apps-install-distribute#update-a-template-app).

## Related information

[Power BI apps FAQ](across-powerbi-apps-faq.md)  
[Power BI apps by functional area](across-powerbi-apps-by-functional-area.md)  
[Introduction to Business Central and Power BI](admin-powerbi.md)  
[Work with Power BI reports](across-working-with-powerbi.md)  
