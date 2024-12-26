---
title: Introduction to Business Central and [!INCLUDE[powerbi-name](includes/powerbi-name.md)]
description: Get an overview of using [!INCLUDE[powerbi-name](includes/powerbi-name.md)] to get insights and KPIs from your Business Central data.
author: jswymer
ms.topic: overview
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.search.form: 6316, 6317
ms.reviewer: jswymer
ms.date: 04/24/2024
ms.author: jswymer
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Introduction to Business Central and [!INCLUDE[powerbi-name](includes/powerbi-name.md)]

It's easy to get insights into your [!INCLUDE[prod_short](includes/prod_short.md)] data with [[!INCLUDE[powerbi-name](includes/powerbi-name.md)]](https://powerbi.microsoft.com) - a data visualization system from Microsoft. [!INCLUDE[powerbi-name](includes/powerbi-name.md)] retrieves [!INCLUDE[prod_short](includes/prod_short.md)] data so that you can build dashboards and reports based on that data. [!INCLUDE[powerbi-name](includes/powerbi-name.md)] provides a flexible alternative to reports built in [!INCLUDE[prod_short](includes/prod_short.md)], enabling you drill down and customize the visualization, and even merge data from different companies in [!INCLUDE[prod_short](includes/prod_short.md)]. Some [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports can also be embedded in Business Central and viewed without leaving the system. More complex dashboards are better experienced from the [!INCLUDE[powerbi-name](includes/powerbi-name.md)] web site.

![[!INCLUDE[powerbi-name](includes/powerbi-name.md)] and Business Central.](media/power-bi-intro.png)

## What you can do with [!INCLUDE[powerbi-name](includes/powerbi-name.md)] and Business Central

There are various features for working with [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[powerbi-name](includes/powerbi-name.md)]. Some things you can do from [!INCLUDE[powerbi-name](includes/powerbi-name.md)], while other things are done from [!INCLUDE[prod_short](includes/prod_short.md)]. Also, some features are only available with [!INCLUDE[prod_short](includes/prod_short.md)] online, not on-premises. The following table gives you an overview.

|Feature|Description|Online|On-premises|Learn more|
|-------|-----------|--------------|-----------|----------------|
|View [!INCLUDE[prod_short](includes/prod_short.md)] data in [!INCLUDE[powerbi-name](includes/powerbi-name.md)]|You can view your data from [!INCLUDE[prod_short](includes/prod_short.md)] in reports in [!INCLUDE[powerbi-name](includes/powerbi-name.md)]. [!INCLUDE[prod_short](includes/prod_short.md)] online includes some predefined [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports. Or, your organization might have some custom reports.|![Works online.](media/check.png)|![Works on-premises](media/check.png)|[Here...](across-working-with-powerbi.md)|
|View [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports in the [!INCLUDE[prod_short](includes/prod_short.md)] client.| [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports that display [!INCLUDE[prod_short](includes/prod_short.md)] data can be embedded directly in parts [!INCLUDE[prod_short](includes/prod_short.md)] pages. You can switch the part to display any report that is made available to you. |![works online.](media/check.png)|![Works on-premises](media/check.png)<sup>[*](#onprem)</sup>|[Here...](across-working-with-powerbi.md).|
|Create reports and dashboards in [!INCLUDE[powerbi-name](includes/powerbi-name.md)] that display [!INCLUDE[prod_short](includes/prod_short.md)] data.|Use [!INCLUDE[powerbi-desktop-name](includes/powerbi-desktop-name.md)] to create your own reports and dashboards. You can publish the reports to your own [!INCLUDE[powerbi-service-name](includes/powerbi-service-name.md)] or share them with others within your organization.|![Works online.](media/check.png)|![works on-premises](media/check.png)|[Here...](across-how-use-financials-data-source-powerbi.md)|
|[!INCLUDE[prod_short](includes/prod_short.md)] apps in [!INCLUDE[powerbi-name](includes/powerbi-name.md)]| [!INCLUDE[prod_short](includes/prod_short.md)] publishes three apps for [!INCLUDE[powerbi-name](includes/powerbi-name.md)] on Microsoft AppSource. These apps create detailed reports and dashboards in your [!INCLUDE[powerbi-service-name](includes/powerbi-service-name.md)] for viewing [!INCLUDE[prod_short](includes/prod_short.md)] data. Available apps include: <ul><li>[!INCLUDE [prod_long](includes/prod_long.md)] - CRM </li><li>[!INCLUDE [prod_long](includes/prod_long.md)] - Finance </li><li>[!INCLUDE [prod_long](includes/prod_long.md)] - Sales </li></ul>  |![Works online.](media/check.png)||[Here...](across-powerbi-business-central-apps.md)|
|Work with [!INCLUDE [prod_short](includes/prod_short.md)] data in datamarts and dataflows|Starting in July 2022, you can use the [!INCLUDE [prod_short](includes/prod_short.md)] connector in Power Query Online to dataflows that you share across different reports and dashboards.|![works online.](media/check.png)||[Here...](across-powerbi-business-central-apps.md)|

<a name="onprem"><sup>*</sup></a> This feature requires a registered application for Business Central in Microsoft Azure. For more information, see [Registering Business Central on-premises in Microsoft Entra ID for integrating with other services](/dynamics365/business-central/dev-itpro/administration/register-app-azure).

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

## Get ready to use [!INCLUDE[powerbi-name](includes/powerbi-name.md)]

There are a few tasks that must be done before you can start using [!INCLUDE[powerbi-name](includes/powerbi-name.md)] with [!INCLUDE[prod_short](includes/prod_short.md)].<!-- Some of the tasks are typically only done by administrators or super users.--> The tasks depend on your role in your organization, and what you want to do with [!INCLUDE[powerbi-name](includes/powerbi-name.md)]:

- As a *business user*, you want to view [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports, either in the [!INCLUDE[powerbi-service-name](includes/powerbi-service-name.md)] or in Business Central
- As an *administrator*, you're responsible for the management of the organization-wide settings that control how Business Central and [!INCLUDE[powerbi-name](includes/powerbi-name.md)] work.
- As a *report creator*, you want to build custom [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports that you can share with other users.

|Task|Business user|Administrator|Report creator|More information|
|----|-------------|-------------|-----------------------|----------------|
|Get a [!INCLUDE[powerbi-name](includes/powerbi-name.md)] account.|![yet another checkmark.](media/check.png)|![it's a checkmark](media/check.png)|![again a checkmark](media/check.png)|Go to [https://powerbi.microsoft.com](https://powerbi.microsoft.com). To sign up for an account, use your work email address and password. <br /><br/>Sign-up requires that you have a license, but in most cases you should already have a free license, For more information, see [[!INCLUDE[powerbi-name](includes/powerbi-name.md)] Licensing](admin-powerbi-setup.md#license).|
|Get [!INCLUDE[powerbi-desktop-name](includes/powerbi-desktop-name.md)] |||![again a checkmark.](media/check.png)|To download, go to [[!INCLUDE[powerbi-desktop-name](includes/powerbi-desktop-name.md)]](https://powerbi.microsoft.com/desktop/). For more information, see [Get [!INCLUDE[powerbi-desktop-name](includes/powerbi-desktop-name.md)]](/power-bi/fundamentals/desktop-get-the-desktop).
|Expose Business Central data to [!INCLUDE[powerbi-name](includes/powerbi-name.md)]||![it's a checkmark.](media/check.png)|![again a checkmark](media/check.png)|[Expose data through API pages or OData web services](admin-powerbi-setup.md#exposedata)
|Enable [!INCLUDE[powerbi-name](includes/powerbi-name.md)] integration<br />(on-premises only)||![it's a checkmark.](media/check.png)||[Set up Business Central on-premises for [!INCLUDE[powerbi-name](includes/powerbi-name.md)] integration](across-working-with-business-central-in-powerbi.md#setup)|


## Next steps

- If you're an admin who needs to set up [!INCLUDE[powerbi-name](includes/powerbi-name.md)] in [!INCLUDE[prod_short](includes/prod_short.md)], go to [Enabling [!INCLUDE[powerbi-name](includes/powerbi-name.md)] Integration](admin-powerbi-setup.md).
- If [!INCLUDE[powerbi-name](includes/powerbi-name.md)] is already set up, and you want to try the features, go to [Work with [!INCLUDE[powerbi-name](includes/powerbi-name.md)] Reports in Business Central](across-working-with-powerbi.md).

## See also

[Track KPIs with [!INCLUDE[powerbi-name](includes/powerbi-name.md)] metrics](track-kpis-with-power-bi-metrics.md)   
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as a [!INCLUDE[powerbi-name](includes/powerbi-name.md)] Data Source](across-how-use-financials-data-source-powerbi.md)  
[[!INCLUDE[powerbi-name](includes/powerbi-name.md)] documentation](/power-bi/)  
[What is [!INCLUDE[powerbi-name](includes/powerbi-name.md)]?](/power-bi/fundamentals/power-bi-overview)  
[Quickstart: Connect to data in [!INCLUDE[powerbi-desktop-name](includes/powerbi-desktop-name.md)] ](/power-bi/desktop-quickstart-connect-to-data)  
[Introduction to datamarts](/power-bi/transform-model/datamarts/datamarts-overview)  
[Introduction to dataflows and self-service data preparation](/power-bi/transform-model/dataflows/dataflows-introduction-self-service)  
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)     

[!INCLUDE[footer-include](includes/footer-banner.md)]
