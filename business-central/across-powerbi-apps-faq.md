---
title: Power BI apps FAQ
description: FAQ for the Business Central Power BI apps.
author: kennieNP
ms.topic: get-started
ms.devlang: al
ms.search.keywords: analysis, reporting, business intelligence, KPI, installation, administration
ms.date: 01/17/2025
ms.author: kepontop
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Frequently asked questions about the Power BI apps in Business Central

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This article provides answers to frequently asked questions (FAQs) about the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)].

## What [!INCLUDE [powerbi-name](includes/powerbi-name.md)] licenses do I need?

To use the Power BI apps, you need [!INCLUDE [powerbi-pro-license-name](includes/powerbi-pro-license-name.md)] licenses for the following users:

- Users who install the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template apps.
- Users who refresh the report data.
- Users who access the reports.

Alternatively, you can use [!INCLUDE [powerbi-premium-capacity-name](includes/powerbi-premium-capacity-name.md)].

To learn more, go to [Installing Power BI apps for Business Central (prerequisites)](across-powerbi-install-business-central-apps.md#prerequisites).

## Why do I need [!INCLUDE [powerbi-name](includes/powerbi-name.md)] licenses?

You must have [!INCLUDE [powerbi-name](includes/powerbi-name.md)] licenses for the following reasons:

1. You must install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] template apps from Microsoft AppSource.
2. You must share a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] workspace.

The use of free license alternative for [!INCLUDE [powerbi-name](includes/powerbi-name.md)] allows you to embed your own reports. Anything in the free [!INCLUDE [powerbi-name](includes/powerbi-name.md)] license must be present in your personal [!INCLUDE [powerbi-name](includes/powerbi-name.md)] workspace. So, the free license alternative does not work with the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps.

## What [!INCLUDE[prod_short](includes/prod_short.md)] licenses do I need?

[!INCLUDE[about_bc_licensing_for_powerbi](includes/about_bc_licensing_for_powerbi.md)]

[!INCLUDE[about_licensing](includes/about_licensing.md)]


## Can I install the same app multiple times for different companies or environments?

Yes. Just rename the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] workspace after installing the app.

To learn more, see [Rename a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] workspace](/power-bi/create-reports/service-rename#rename-a-workspace).

## Can I use the same app to do reporting across multiple companies or environments?

No. [!INCLUDE [powerbi-apps-per-company-include](includes/powerbi-apps-per-company-include.md)]

## How do I refresh the data in an app?

To learn more, go to [Get the latest data (refresh the semantic model)](./across-powerbi-install-business-central-apps.md#get-the-latest-data-refresh-the-semantic-model).

## My semantic model does not refresh. How do I see what is wrong?

[!INCLUDE [powerbi-refresh-tsg-include](includes/powerbi-refresh-tsg-include.md)]

## I can't see any dimension data in my reports

Check whether the job queue entry for updating dimension set data is stopped.

To learn more, go to [Job queue entry for updating dimension set entries](across-powerbi-install-business-central-apps.md#job-queue-entry-for-updating-dimension-set-entries).

## How do I change the connection parameters for an app?

To learn more, go to [Connect the Power BI semantic models to Business Central](across-powerbi-install-business-central-apps.md#connect-the-power-bi-semantic-models-to-business-central).

## How do I update an app?

To learn more, go to [Updating a Power BI app](across-powerbi-install-business-central-apps.md#updating-a-power-bi-app).

## Can I get a copy of the source code (.pbix files) for the apps?

No. At the moment, the source code (.pbix files) for the apps isn't available. However, its availability might change in a later release.

## Are the apps available for on-premises installations?

No. At the moment, the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps are only available for online environments.

## Related information

[Installing Power BI apps for Business Central](across-powerbi-install-business-central-apps.md)  
[Power BI apps by functional area](across-powerbi-apps-by-functional-area.md)  
[Introduction to Business Central and Power BI](admin-powerbi.md)  
[Work with Power BI reports](across-working-with-powerbi.md)  
