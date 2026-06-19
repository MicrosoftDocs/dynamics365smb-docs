---
title: Integration overview for Business Central 
description: Find links to information about the ways you can integrate Business Central to products and services.
author: kennienp
ms.reviewer: jswymer
ms.topic: overview
ms.author: kepontop
ms.date: 06/19/2026
---

# Integration overview for Business Central 

This article provides on overview of how [!INCLUDE[prod_short](includes/prod_short.md)] integrates with other Microsoft applications.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/all-integrations.svg" alt-text="Shows how Business Central integrates to Microsoft 365" lightbox="/dynamics365/business-central/dev-itpro/developer/media/all-integrations.svg":::

The article describes integration scenarios as seen from the business. However, it doesn't include technical details about how to use or set up every integration. To learn more about the technical details of integrations, go to [Integration overview for Business Central (for administrators)](/dynamics365/business-central/dev-itpro/developer/integration-overview).

> [!NOTE]
> Some integrations require a separate subscription or license. Refer to the documentation for the application for requirements and details.

## Integrate with Office apps and [!INCLUDE[m365](includes/m365-name.md)]

[!INCLUDE[prod_short](includes/prod_short.md)] integrates with multiple [!INCLUDE[m365](includes/m365-name.md)] applications to gain extra features. Integrations help you stay in the flow of work by giving you access to the right data at the right time. 

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/m365-integrations-overview.svg" alt-text="Shows how Business Central integrates to Office" lightbox="/dynamics365/business-central/dev-itpro/developer/media/m365-integrations-overview.svg":::

[!INCLUDE [prod_short](includes/prod_short.md)] integrates to the following [!INCLUDE[m365](includes/m365-name.md)] products and services:

- [!INCLUDE[m365_excel](includes/m365-excel-name.md)]
- [!INCLUDE[m365_onedrive_for_business](includes/m365-onedrive-for-business-name.md)]
- [!INCLUDE[m365_outlook](includes/m365-outlook-name.md)]
- [!INCLUDE[m365_teams](includes/m365-teams-name.md)]
- [!INCLUDE[m365_word](includes/m365-word-name.md)]

### Examples of benefits of integrating with Office apps

Here are a few examples of how these integrations can help your business:

- Open your customer list in [!INCLUDE[m365_excel](includes/m365-excel-name.md)] to quickly analyze sales trends and create reports without leaving your familiar spreadsheet environment.
- Store and share important business documents like invoices and contracts in [!INCLUDE[m365_onedrive_for_business](includes/m365-onedrive-for-business-name.md)] so your team can access them from anywhere.
- Turn an incoming email into a vendor invoice or sales quote directly in [!INCLUDE[m365_outlook](includes/m365-outlook-name.md)], so you never lose track of important business opportunities.
- Share a customer card or sales order in a [!INCLUDE[m365_teams](includes/m365-teams-name.md)] chat, so your colleagues can quickly see the details they need without switching apps.
- Generate professional-looking quotes and invoices using customized [!INCLUDE[m365_word](includes/m365-word-name.md)] templates that reflect your company's branding.

Learn more at [Integrating Business Central with Microsoft 365](m365-integration-overview.md).

## Integrate Business Central with Power Platform

[!INCLUDE [prod_short](includes/prod_short.md)] integrates with the following Power Platform products and services:

- Power Apps
- Power Automate
- Power BI
- Power Pages

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/powerplatform-integrations.svg" alt-text="Shows how Business Central integrates to Power Platform" lightbox="/dynamics365/business-central/dev-itpro/developer/media/powerplatform-integrations.svg"::: 

### Examples of benefits of integrating with Power Platform

Here are a few examples of how these integrations can help your business:

- Build a custom Power Apps mobile app that lets your warehouse team update inventory counts on the go, with data flowing straight into [!INCLUDE[prod_short](includes/prod_short.md)].
- Set up a Power Automate flow that automatically sends an approval request to your manager whenever a purchase order exceeds a certain amount.
- Create interactive Power BI dashboards that give your leadership team real-time visibility into revenue, cash flow, and outstanding receivables.
- Use Power Pages to build a self-service portal where your vendors can check the status of their invoices without contacting your accounts payable team.

Learn more in [Integrating Business Central with Power Platform](powerplatform-integration-overview.md).

## Built-in: Integrate Business Central with Dataverse

[!INCLUDE[prod_short](includes/prod_short.md)] has four built-in ways to integrate with [!INCLUDE[dataverse_short](includes/dataverse_short.md)]:

- Data synchronization that replicates data between [!INCLUDE[prod_short](includes/prod_short.md)] and [!INCLUDE[dataverse_short](includes/dataverse_short.md)].
- Data virtualization with virtual tables in [!INCLUDE[dataverse_short](includes/dataverse_short.md)] via [!INCLUDE[prod_short](includes/prod_short.md)] API for create, read, update, and delete (CRUD) operations.
- Data change (CRUD) events using webhooks.
- Business events (preview).

### Examples of benefits of integrating with Dataverse

Here are a few examples of how these integrations can help your business:

- Keep customer and product data in sync across all your Dynamics 365 apps. Your teams always have the latest information, no matter which app they use.
- Use virtual tables to let other apps read and update [!INCLUDE[prod_short](includes/prod_short.md)] data in real time without duplicating records across systems.
- Trigger automated workflows the moment a new sales order is created, so downstream processes like fulfillment and invoicing start immediately.

Learn more in [Integrating Business Central with Microsoft Dataverse (administration documentation)](/dynamics365/business-central/dev-itpro/developer/dataverse-integration-overview).

## Built-in: Integrate Business Central with Dynamics 365 Sales

You can integrate [!INCLUDE[prod_short](includes/prod_short.md)] with Dynamics 365 Sales by first setting up integration to [!INCLUDE[dataverse_short](includes/dataverse_short.md)], and then completing the connection from [!INCLUDE[prod_short](includes/prod_short.md)] application. Integrating to Dynamics 365 Sales lets you view information from [!INCLUDE[prod_short](includes/prod_short.md)] while you're working in Dynamics 365 Sales. For example, when you prepare a sales quote, it could be useful to know whether you have enough inventory to fulfill the order.

### Examples of benefits of integrating with Sales

Here are a few examples of how this integration can help your business:

- Let your sales team check real-time inventory levels and pricing directly in Dynamics 365 Sales, so they can make accurate promises to customers without switching apps.
- Automatically sync completed sales orders from Dynamics 365 Sales into [!INCLUDE[prod_short](includes/prod_short.md)] for invoicing and fulfillment, eliminating manual data entry and reducing errors.
- Give your sales reps visibility into a customer's outstanding invoices and credit limits so they're informed in conversations and manage risk right from the deal stage.

Learn more at [Integrating Business Central with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md).

## Built in: Integrate Business Central with Dynamics 365 Field Service

Service organizations require a front-to-back application in which finance, inventory, and procurement are tightly coupled with service delivery. They generate financial data with every transaction. Every work order represents cost and revenue, and every resource generates profit and loss. Customer interactions add entries on the general ledger. The integration between [!INCLUDE [prod_short](includes/prod_short.md)] and [!INCLUDE [m365-field-service-name](includes/m365-field-service-name.md)] streamlines the end-to-end process of managing service operations and ensures a smooth flow of information between the two applications.

### Examples of benefits of integrating with Field Service

Here are a few examples of how this integration can help your business:

- Automatically consume inventory items in [!INCLUDE[prod_short](includes/prod_short.md)] when a field technician uses parts on a work order, keeping your stock levels accurate without any extra paperwork.
- Convert completed work orders into customer invoices quickly, so your billing team can close the books faster.
- Give your service managers full visibility into project costs and resource profitability by combining field service data with your financial records in one place.

Learn more at [Integrate with Microsoft Dynamics 365 Field Service](admin-integrate-field-service.md).

## Built-in: Integrate Business Central with Shopify

You can integrate [!INCLUDE[prod_short](includes/prod_short.md)] with Shopify by installing and configuring the Shopify Connector app. By connecting your Shopify stores to [!INCLUDE[prod_short](includes/prod_short.md)], you can maximize your business productivity and manage and view insights from your business and your Shopify store as one unit.

### Examples of benefits of integrating with Shopify

Here are a few examples of how this integration can help your business:

- Automatically sync your product catalog, pricing, and inventory levels between [!INCLUDE[prod_short](includes/prod_short.md)] and Shopify, so your online store always shows accurate availability.
- Pull Shopify orders directly into [!INCLUDE[prod_short](includes/prod_short.md)] for fulfillment and invoicing, saving your team from tedious copy-and-paste work.
- Get a unified view of your online and offline sales performance, making it easier to spot trends and plan for growth.

Learn more at [Get started with the Shopify connector](shopify/get-started.md).

## Related information

[Integrating Business Central with Office apps and Microsoft 365](m365-integration-overview.md)  
[Integrating Business Central with Power Platform](powerplatform-integration-overview.md)  
[Integrating Business Central with Microsoft Dataverse (administration documentation)](/dynamics365/business-central/dev-itpro/developer/dataverse-integration-overview)  
[Integrating Business Central with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)  
[Integrate with Microsoft Dynamics 365 Field Service](admin-integrate-field-service.md)  
[Integrating Business Central with Shopify](shopify/get-started.md)  
<!-- 
[Envestnet Yodlee Bank Feeds extension](ui-extensions-yodlee-bank-feeds.md)  
[AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md)  
 -->
