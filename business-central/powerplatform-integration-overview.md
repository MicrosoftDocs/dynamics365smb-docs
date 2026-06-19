---
title: Integrate with Microsoft Power Platform
description: Learn how to integrate Business Central with the Microsoft Power Platform
author: kennienp
ms.reviewer: jswymer
ms.topic: overview
ms.author: kepontop
ms.date: 06/19/2026
ms.custom: bap-template
ai-usage: ai-assisted
---

# Integrate Business Central with Microsoft Power Platform

You can integrate [!INCLUDE [prod_short](includes/prod_short.md)] with Microsoft Power Platform to enhance your business' productivity and efficiency. The integration lets you analyze data, build solutions, automate processes, and create virtual agents. You can apply the data and business logic of [!INCLUDE [prod_short](includes/prod_short.md)], and benefit from the analytical and automation capabilities of Microsoft Power Platform.

This article outlines how to integrate [!INCLUDE [prod_short](includes/prod_short.md)] with Microsoft Power Platform, and offers links to more information.

## Business Central connector for Power Platform

A *connector* is a proxy, or a wrapper, for APIs that gives you access to data in another application. [!INCLUDE[prod_short](includes/prod_short.md)] has a connector that allows Power Platform products such as Power Automate, Power Apps, and Logic apps to communicate with [!INCLUDE[prod_short](includes/prod_short.md)] through REST APIs.

To learn more about connectors, go to [Power Platform Connectors Overview](/connectors/overview) in the Power Platform documentation. To learn more about the [!INCLUDE [prod_short](includes/prod_short.md)] Connector, go to [Dynamics 365 Business Central Connector](/dynamics365/business-central/dev-itpro/powerplatform/power-automate-overview#the-business-central-connector).

## Integrate Business Central with Microsoft Power Apps

You can integrate [!INCLUDE[prod_short](includes/prod_short.md)] with Microsoft Power Apps by using the [!INCLUDE[prod_short](includes/prod_short.md)] connector for Power Platform. With Power Apps, you have the flexibility to build the perfect solution for your business domain; one that uses [!INCLUDE[prod_short](includes/prod_short.md)] data and processes and maximizes your productivity. With Power Apps custom UI, AI builder, and augmented-reality (AR)/mixed-reality (MR) technologies, you can take your business to the next level with cutting-edge innovation and customized UI.

Learn more at [Integrating with Microsoft Power Apps overview (administration documentation)](/dynamics365/business-central/dev-itpro/powerplatform/power-apps-overview)

## Integrate Business Central with Microsoft Power Automate

You can integrate [!INCLUDE[prod_short](includes/prod_short.md)] with Microsoft Power Automate by using the [!INCLUDE[prod_short](includes/prod_short.md)] connector for Power Platform. With Power Automate, you can set up and use flows to connect business-process tasks performed by different users. You can include system tasks, such as automatic posting, as steps in flows, preceded or followed by user tasks. For example, requesting and granting approval to create new records are typical steps in flows.

Learn more at [Integrating with Microsoft Power Automate overview (administration documentation)](/dynamics365/business-central/dev-itpro/powerplatform/power-automate-overview)

## Integrate Business Central with Microsoft Power BI

You can integrate [!INCLUDE[prod_short](includes/prod_short.md)] with Microsoft Power BI in two ways:

- Connect a Power BI semantic model to [!INCLUDE[prod_short](includes/prod_short.md)] to read data.
- Embed a Power BI report, page, or visual in the [!INCLUDE[prod_short](includes/prod_short.md)] application.

### Connect a Power BI semantic model to Business Central to read data

[!INCLUDE[prod_short](includes/prod_short.md)] integrates with Power BI through a connector. Learn more at [Power BI integration overview](admin-powerbi-overview.md).

### Embed a Power BI report, page, or visual in Business Central

You can use an iframe to embed a Power BI report, page, or visual in [!INCLUDE [prod_short](includes/prod_short.md)].

There are two ways to add a Power BI report, page, or visual to a page in [!INCLUDE[prod_short](includes/prod_short.md)]:

1. You can embed a Power BI report, page, or scorecard on pages that include a Power BI part. Learn more at [Working with Power BI Reports in Business Central](across-working-with-powerbi.md).
1. A developer can programmatically add them from AL. Learn more at [Adding Power BI Report parts to pages](/dynamics365/business-central/dev-itpro/developer/devenv-power-bi-report-parts).

## Integrate Business Central with Microsoft Power Pages

You can integrate [!INCLUDE[prod_short](includes/prod_short.md)] with Microsoft Power Pages by using virtual tables in Dataverse. With Power Pages, you can give unlicensed, external users access data in [!INCLUDE[prod_short](includes/prod_short.md)].

Learn more at [Integrating with Microsoft Power Pages (preview)](/dynamics365/business-central/dev-itpro/developer/power-pages-on-virtual-tables-overview).

## Related information

[Business Central connector for Power Platform](/connectors/dynamicssmbsaas)  
[Integrating with Microsoft Power Apps overview](/dynamics365/business-central/dev-itpro/powerplatform/power-apps-overview)  
[Integrating with Microsoft Power Automate overview](/dynamics365/business-central/dev-itpro/powerplatform/power-automate-overview)  
[Integrating with Microsoft Power Pages (preview)](/dynamics365/business-central/dev-itpro/developer/power-pages-on-virtual-tables-overview)  
[Integrating with Microsoft Power BI](admin-powerbi-overview.md)  
[How users can embed Power BI Reports in Business Central](across-working-with-powerbi.md)  
[Business Central integrations overview](integration-overview.md)  