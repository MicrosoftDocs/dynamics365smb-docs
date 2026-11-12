---
title: Business Central Power BI Apps FAQ
description: Find answers about licensing, installation, data refresh, dimensions, languages, and source files for the Business Central Power BI apps.
author: kennieNP
ms.topic: faq
ms.devlang: al
ms.search.keywords: analysis, reporting, business intelligence, KPI, installation, administration
ms.search.form: 36951, 
ms.date: 11/11/2026
ms.author: kepontop
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai-usage: ai-assisted
---

# Frequently asked questions about the Power BI apps in Business Central

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This article provides answers to frequently asked questions (FAQs) about the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)].

## What [!INCLUDE [powerbi-name](includes/powerbi-name.md)] licenses do I need?

Users who install and distribute Power BI template apps need a Power BI Pro or Premium Per User (PPU) license.

Users who view the reports also need Pro or PPU unless both the report and its semantic model are hosted in Premium capacity or Fabric F64 or larger capacity. In qualifying capacity, users with free licenses can view shared content with the required permissions, such as the workspace **Viewer** role. Content in a PPU workspace requires PPU licenses for viewers. Capacity doesn't replace the installer's paid license. Learn more in [Power BI license types](/power-bi/fundamentals/service-features-license-type).

Learn more in [Installing Power BI apps for Business Central (prerequisites)](across-powerbi-install-business-central-apps.md#prerequisites).

## Why do I need [!INCLUDE [powerbi-name](includes/powerbi-name.md)] licenses?

You must have [!INCLUDE [powerbi-name](includes/powerbi-name.md)] licenses for the following reasons:

1. You must install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template apps from Microsoft Marketplace.
2. You must share a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] workspace.

A free Power BI license lets you use your own reports in **My workspace**, but it doesn't let you install or distribute template apps. Free users can view shared app content hosted in qualifying capacity, as described in the previous answer.

## What Business Central licenses do I need?

[!INCLUDE[about_bc_licensing_for_powerbi](includes/about_bc_licensing_for_powerbi.md)]

[!INCLUDE[about_licensing](includes/about_licensing.md)]

## Can I install the same app multiple times for different companies or environments?

Yes. Select **Install another copy of the app into a new workspace** when you reinstall the app. Consider including the company name in the workspace name to make it easier to find.

:::image type="content" source="media/powerbi/power-bi-install-app.png" alt-text="Screenshot of the Power BI app installer." lightbox="media/powerbi/power-bi-install-app.png":::

## Can I use the same app to do reporting across multiple companies or environments?

No. [!INCLUDE [powerbi-apps-per-company-include](includes/powerbi-apps-per-company-include.md)]

## How do I refresh the data in an app?

Learn more in [Get the latest data (refresh the semantic model)](./across-powerbi-install-business-central-apps.md#get-the-latest-data-refresh-the-semantic-model).

## My semantic model doesn't refresh. How do I figure out what's wrong?

[!INCLUDE [powerbi-refresh-tsg-include](includes/powerbi-refresh-tsg-include.md)]

## I can't see any dimension data in my reports

All Power BI semantic models read dimension records from **PowerBI Flat Dim. Set Entry** (Table 36954). This is a different table from the standard **Dimension Set Entries** table.

The **PowerBI Flat Dim. Set Entry** table has flattened dimension set entry records that are purpose-built for PBI reporting. The **Update Dim. Set Entries** job queue entry (Codeunit 36952) periodically updates the table.

This job queue entry is created automatically when you install the Power BI connector app or initialize a company. If the entry is missing or needs to be reset, go to the **Power BI Reports Setup** page and select **Schedule Power BI Dimension Refresh**. The job queue entry's description is **Update Power BI Dimension Set Entries**, and it runs codeunit 36952, **Update Dim. Set Entries**.

### Troubleshoot dimension data

1. On the **Job Queue Entries** page, find the entry with the description **Update Power BI Dimension Set Entries** and codeunit ID **36952**, and ensure that its status is **Ready**.
1. Ensure that the job queue entry ran successfully. To verify that the job works, select the job and then select the **Run once (foreground)** action.
1. Open the **PowerBI Flat Dim. Set Entry** table in your browser to verify that records are present. If the table has data, you can refresh the semantic model and review the results.

Learn more in [Job queue entry for updating dimension set entries](across-powerbi-install-business-central-apps.md#job-queue-entry-for-updating-dimension-set-entries).

## How do I change the connection parameters for an app?

Learn more in [Connect the Power BI semantic models to Business Central](across-powerbi-install-business-central-apps.md#connect-the-power-bi-semantic-models-to-business-central).

## How do I update an app?

Learn more in [Update a Power BI app](across-powerbi-install-business-central-apps.md#update-a-power-bi-app).

## Are the apps available in multiple languages?

Yes, all apps are multilingual for many of the languages that [!INCLUDE[prod_short](includes/prod_short.md)] supports. Learn more in [Multilanguage Power BI apps for Business Central](across-powerbi-business-central-apps-multi-language.md).

## Can I get a copy of the source code (.pbix files) for the apps?

The source code (.pbix files) for the Power BI apps is available from the following versions.

| Power BI app for...            | Source code available from version |
|--------------------------------| -------------- |
| Finance                        | 26.2 and later |
| Inventory                      | 26.2 and later |
| Inventory Valuation            | 26.2 and later |
| Manufacturing                  | 26.2 and later |
| Purchasing                     | 27.0 and later |
| Projects                       | 27.0 and later |
| Sales                          | 27.0 and later |
| Subscription Billing           | 26.2 and later |
| Sustainability                 | 26.2 and later |

You can download the .pbix file by installing the app from Marketplace and then download the source code from the installed app.

## Are the apps available for on-premises installations?

No. [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps are only available for online environments.

## Related information

[Install Power BI apps for Business Central](across-powerbi-install-business-central-apps.md)  
[Power BI apps by functional area](across-powerbi-apps-by-functional-area.md)  
[Introduction to Business Central and Power BI](admin-powerbi.md)  
[Work with Power BI reports](across-working-with-powerbi.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
