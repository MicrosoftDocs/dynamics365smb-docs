---
title: Introduction to Business Central and Power BI
description: Get an overview of using Power BI to get insights and KPIs from your Business Central data.
author: jswymer
ms.topic: overview
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.search.form: 6316, 6317
ms.reviewer: jswymer
ms.date: 05/19/2025
ms.author: jswymer
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Introduction to Business Central and Power BI

It's easy to get insights into your [!INCLUDE[prod_short](includes/prod_short.md)] data with [[!INCLUDE[powerbi-name](includes/powerbi-name.md)]](https://powerbi.microsoft.com) - a data visualization system from Microsoft. [!INCLUDE[powerbi-name](includes/powerbi-name.md)] retrieves [!INCLUDE[prod_short](includes/prod_short.md)] data so that you can build dashboards and reports based on that data. [!INCLUDE[powerbi-name](includes/powerbi-name.md)] provides a flexible alternative to reports built in [!INCLUDE[prod_short](includes/prod_short.md)], enabling you drill down and customize the visualization, and even merge data from different companies in [!INCLUDE[prod_short](includes/prod_short.md)]. Some [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports can also be embedded in Business Central and viewed without leaving the system. More complex dashboards are better experienced from the [!INCLUDE[powerbi-name](includes/powerbi-name.md)] web site.

:::image type="content" source="media/finance/financial-overview.png" alt-text="Screenshot of the Finance Overview report" lightbox="media/finance/financial-overview.png":::

<!--  
![[!INCLUDE[powerbi-name](includes/powerbi-name.md)] and Business Central.](media/power-bi-intro.png)
 -->

## What you can do with [!INCLUDE[powerbi-name](includes/powerbi-name.md)] and Business Central

[!INCLUDE[prod_short](includes/prod_short.md)] includes multiple [!INCLUDE[powerbi-name](includes/powerbi-name.md)] features. Some things you can do from [!INCLUDE[powerbi-name](includes/powerbi-name.md)], while other things are done from [!INCLUDE[prod_short](includes/prod_short.md)]. Also, some features are only available with [!INCLUDE[prod_short](includes/prod_short.md)] online, not on-premises. The following table gives you an overview.

|Feature|Description|Online|On-premises|Learn more|
|-------|-----------|:----:|:---------:|----------|
| Use built-in [!INCLUDE[powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE[prod_short](includes/prod_short.md)] | [!INCLUDE[prod_short](includes/prod_short.md)] publishes many different apps for [!INCLUDE[powerbi-name](includes/powerbi-name.md)] on Microsoft Marketplace. These apps create detailed reports and dashboards in your [!INCLUDE[powerbi-service-name](includes/powerbi-service-name.md)] for viewing [!INCLUDE[prod_short](includes/prod_short.md)] data. |![Works online.](media/check.png)||[Here...](across-powerbi-apps-by-functional-area.md) |
|Use [!INCLUDE[powerbi-name](includes/powerbi-name.md)] with [!INCLUDE[prod_short](includes/prod_short.md)] | You can use your data from [!INCLUDE[prod_short](includes/prod_short.md)] in reports in [!INCLUDE[powerbi-name](includes/powerbi-name.md)]. [!INCLUDE[prod_short](includes/prod_short.md)] online includes many [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports. Or, your organization might have some custom reports.|![Works online.](media/check.png)|![Works on-premises](media/check.png)|[Here...](across-working-with-powerbi.md)|
|View [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports in the [!INCLUDE[prod_short](includes/prod_short.md)] client.| [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports that display [!INCLUDE[prod_short](includes/prod_short.md)] data can be embedded directly in parts [!INCLUDE[prod_short](includes/prod_short.md)] pages. You can switch the part to display any report that is made available to you. |![works online.](media/check.png)|![Works on-premises](media/check.png)<sup> [*](#onprem)</sup>|[Here...](across-working-with-powerbi.md).|
|Create reports and dashboards in [!INCLUDE[powerbi-name](includes/powerbi-name.md)] that display [!INCLUDE[prod_short](includes/prod_short.md)] data.|Use [!INCLUDE[powerbi-desktop-name](includes/powerbi-desktop-name.md)] to create your own reports and dashboards. You can publish the reports to your own [!INCLUDE[powerbi-service-name](includes/powerbi-service-name.md)] or share them with others within your organization.|![Works online.](media/check.png)|![works on-premises](media/check.png)|[Here...](across-how-use-financials-data-source-powerbi.md)|
|Work with [!INCLUDE [prod_short](includes/prod_short.md)] data in datamarts and dataflows | Use the [!INCLUDE [prod_short](includes/prod_short.md)] connector in Power Query Online to define dataflows that you share across different reports and dashboards.|![works online.](media/check.png)||[Here...](across-powerbi-business-central-apps.md)|

<a name="onprem"><sup>*</sup></a> This feature requires a registered application for [!INCLUDE [prod_short](includes/prod_short.md)] in Microsoft Azure. For more information, see [Registering [!INCLUDE [prod_short](includes/prod_short.md)] on-premises in Microsoft Entra ID for integrating with other services](/dynamics365/business-central/dev-itpro/administration/register-app-azure).

## Get ready to use Power BI

There are a few tasks that must be done before you can start using [!INCLUDE[powerbi-name](includes/powerbi-name.md)] with [!INCLUDE[prod_short](includes/prod_short.md)]. The tasks depend on your role in your organization and what you want to do with [!INCLUDE[powerbi-name](includes/powerbi-name.md)]:

- As a *user*, you want to view [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports in the [!INCLUDE[powerbi-service-name](includes/powerbi-service-name.md)] or Business Central.
- As an *administrator*, you're responsible for managing the organization-wide settings that control how Business Central and [!INCLUDE[powerbi-name](includes/powerbi-name.md)] work.
- As a *report creator*, you want to build custom [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports to share with other users.

| To...  | User |Administrator|Report creator| Learn more... |
|--------|:----:|:-----------:|:------------:|---------------|
|Get a [!INCLUDE[powerbi-name](includes/powerbi-name.md)] account|![Checkmark](media/check.png)|![Checkmark](media/check.png)|![Checkmark](media/check.png)|Go to [https://powerbi.microsoft.com](https://powerbi.microsoft.com). To sign up for an account, use your work email address and password. <br /><br/>Sign-up requires that you have a license, but in most cases you should already have a free license. To learn more, go to [Power BI Licensing](admin-powerbi-setup.md#license). |
|Use built-in [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)] | ![Checkmark](media/check.png) | | | Get started here: [Power BI apps/reports by functional area](across-powerbi-apps-by-functional-area.md) |
|Enable [!INCLUDE[powerbi-name](includes/powerbi-name.md)] integration for [!INCLUDE [prod_short](includes/prod_short.md)] | | ![Checkmark](media/check.png) | | [Enabling Power BI Integration](admin-powerbi-setup.md) |
| Install [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)] | | ![Checkmark](media/check.png) | | [Installing Power BI apps for Business Central](across-powerbi-install-business-central-apps.md) <br><br> [Power BI apps FAQ](across-powerbi-apps-faq.md) |
|Get [!INCLUDE[powerbi-desktop-name](includes/powerbi-desktop-name.md)] |||![Checkmark](media/check.png)|To download, go to [[!INCLUDE[powerbi-desktop-name](includes/powerbi-desktop-name.md)]](https://powerbi.microsoft.com/desktop/). For more information, see [Get [!INCLUDE[powerbi-desktop-name](includes/powerbi-desktop-name.md)]](/power-bi/fundamentals/desktop-get-the-desktop). |
|Expose Business Central data to [!INCLUDE[powerbi-name](includes/powerbi-name.md)]||![Checkmark](media/check.png)|![Checkmark](media/check.png)|[Expose data through API pages or OData web services](admin-powerbi-setup.md#exposedata) |
|Enable [!INCLUDE[powerbi-name](includes/powerbi-name.md)] integration<br />(on-premises only)||![Checkmark](media/check.png)||[Set up Business Central on-premises for [!INCLUDE[powerbi-name](includes/powerbi-name.md)] integration](across-working-with-business-central-in-powerbi.md#setup) |

## Learn more about [!INCLUDE[powerbi-name](includes/powerbi-name.md)]

The following articles help you get familiar with using [!INCLUDE[powerbi-name](includes/powerbi-name.md)]:

- [What is [!INCLUDE[powerbi-name](includes/powerbi-name.md)]?](/power-bi/fundamentals/power-bi-overview)
- [[!INCLUDE[powerbi-name](includes/powerbi-name.md)] documentation](/power-bi/)
- [Track KPIs with [!INCLUDE[powerbi-name](includes/powerbi-name.md)] metrics](track-kpis-with-power-bi-metrics.md)

The following articles help you get familiar with creating [!INCLUDE[powerbi-name](includes/powerbi-name.md)] reports:

- [Quickstart: Connect to data in [!INCLUDE[powerbi-desktop-name](includes/powerbi-desktop-name.md)]](/power-bi/desktop-quickstart-connect-to-data)
- [Introduction to datamarts](/power-bi/transform-model/datamarts/datamarts-overview)
- [Introduction to dataflows and self-service data preparation](/power-bi/transform-model/dataflows/dataflows-introduction-self-service)

## Next steps

- If [!INCLUDE[powerbi-name](includes/powerbi-name.md)] is already set up, and you want to try the reports, go to [Work with [!INCLUDE[powerbi-name](includes/powerbi-name.md)] Reports in Business Central](across-working-with-powerbi.md). Or go to [Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md) to set up your own scorecards.
- If you're an admin who needs to set up [!INCLUDE[powerbi-name](includes/powerbi-name.md)] in [!INCLUDE[prod_short](includes/prod_short.md)], go to [Enabling [!INCLUDE[powerbi-name](includes/powerbi-name.md)] Integration](admin-powerbi-setup.md).

## Related information

[Available [!INCLUDE[powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE[prod_short](includes/prod_short.md)]](across-powerbi-apps-by-functional-area.md)  
[Track KPIs with [!INCLUDE[powerbi-name](includes/powerbi-name.md)] metrics](track-kpis-with-power-bi-metrics.md)   
[Analytics, business intelligence, and reporting overview](reports-bi-reporting.md)     

[!INCLUDE[footer-include](includes/footer-banner.md)]
