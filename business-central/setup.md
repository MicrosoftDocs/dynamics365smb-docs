---
title: Overview of tasks to set up Business Central
description: Read an overview of the tasks necessary to set up, initialize, and configure Business Central to suit your needs.
author: brentholtorf
ms.topic: overview
ms.devlang: al
ms.search.keywords: configure, initialize
ms.date: 12/30/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Overview of tasks to set up [!INCLUDE[prod_short](includes/prod_short.md)]

[!INCLUDE[prod_short](includes/prod_short.md)] includes standard configurations for most business processes, but you can change the configuration to suit the needs of your organization. The [Business Central quick start](quick-start-business-central.md) articles help you take the first steps into making [!INCLUDE [prod_short](includes/prod_short.md)] your own. This article provides an overview of how you can configure [!INCLUDE [prod_short](includes/prod_short.md)] for your organization.

For example, the chart of accounts is prefilled with posting accounts that are ready for use. You can change the chart of accounts to suit your needs. Learn more at [Finance](finance.md).

Some of the tasks and tools that this article describes require that you're an administrator in your [!INCLUDE[prod_short](includes/prod_short.md)] subscription. Learn more at [Administration](admin-setup-and-administration.md).  

## Assisted setup guides

From the ![Sprocket icon to open the Settings menu.](media/ui-experience/settings_icon_small.png) menu, you can access assisted setup guides to help you configure certain scenarios and add features to [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more about how to access all assisted and manual setup pages at [Getting Ready to Do Business](ui-get-ready-business.md).

:::image type="content" source="media/assisted-setup.png" alt-text="Screenshot of the assisted setup page" lightbox="media/assisted-setup.png":::

> [!NOTE]
> [!INCLUDE [ua-checklist](includes/ua-checklist.md)]

## Set up companies

[!INCLUDE[prod_short](includes/prod_short.md)] organizes business entities in *companies*. For each company, you must provide some details on the **Company Information** page. Each company also contains setup data that you must define.

| To | Go to |
| --- | --- |
|Improve the quality of implementation and shorten deployment time by using tools for setting up a new company. For example, you can use assisted setup guides, templates, worksheets, and customer questionnaires.|[Setting Up a Company With Configuration Packages](admin-set-up-a-company-with-rapidstart.md)|
| Ease working with multiple companies. | [Set up Company information](admin-company-information.md) |

## Set up general functionality

In addition to the assisted setup guides, you can manually set up some general functionality. The following table provides examples.

| To | Go to |
| --- | --- |
|Set up and assign a base calendar to your company and its business partners, such as customers, vendors, or locations. [!INCLUDE [prod_short](includes/prod_short.md)] uses the working days you specify on the calendar to calculate delivery and receipt dates on sales orders, purchase orders, transfer orders, and production order lines.|[Set Up Base Calendars](across-how-to-assign-base-calendars.md)|
| Set up unique identification codes for records, such as cards, documents, and journal lines, to track them in the system. |[Create Number Series](ui-create-number-series.md) |
|Access your [!INCLUDE [prod_short](includes/prod_short.md)] data from your mobile device.|[Getting Business Central on Your Mobile Device](install-mobile-app.md)|
|Set up email communication in and out of [!INCLUDE[prod_short](includes/prod_short.md)].| [Set Up Email Manually or Using the Assisted Setup](admin-how-setup-email.md)|
|Connect to cloud-enabled printers.| [Printer Setup and Management Overview](admin-printer-setup-overview.md)|
|Set up default reports to use to print sales, purchases, and service documents, such as orders, quotes, and invoices, and which layout is used. | [Report selection for documents](across-report-selections.md)|

## Set up business processes

In addition to the assisted setup guides, you can manually set up specific business processes. The following table provides examples.

| To | Go to |
| --- | --- |
| Set up payment methods, currencies, and the chart of accounts, and define rules and defaults for managing financial transactions. |[Setting Up Finance](finance-setup-finance.md) |
| Set up your own and your vendors' bank accounts and enable services for importing and exporting bank files. |[Setting Up Banking](bank-setup-banking.md) |
| Configure the rules and values that define your company's sales policies, register new customers, and set up how you communicate with customers. |[Setting Up Sales](sales-setup-sales.md) |
| Configure the rules and values that define your company's purchasing policies, register new vendors, and prioritize your vendors for payment processing. |[Setting Up Purchasing](purchasing-setup-purchasing.md) |
| Configure the rules and values that define your inventory policies. Set up locations if you keep inventory in multiple warehouses. Categorize your items to improve searches and sorting. |[Setting Up Inventory](inventory-setup-inventory.md) |
| Set up resources, time sheets, and projects to manage projects. |[Setting Up Project Management](projects-setup-projects.md) |
| Configure how to insure, maintain, and depreciate fixed assets and set up how you record the costs of fixed assets in your company books. |[Setting Up Fixed Assets](fa-setup.md) |
|Define the general rules and values for warehouse processes and specific handling at each location.|[Setting Up Warehouse Management](warehouse-setup-warehouse.md)|
|Prepare production bills of materials (BOMs) and routings to define how end items are produced, and prepare machine or work centers to perform the required operations.|[Setting Up Manufacturing](production-configure-production-processes.md)|
|Establish standard services, symptoms, and fault codes and set up the service items, resources, and documentation needed to provide service to your customers.|[Setting Up Service Management](service-setup-service.md)|
|Read best practices for setting up items for inventory costing and supply planning.|[Setting Up Complex Application Areas Using Best Practices](set-up-complex-application-areas-using-best-practices.md)|

## Connect to other Microsoft products

You can enhance your [!INCLUDE[prod_short](includes/prod_short.md)] experience by connecting to other Microsoft products, such as:

- [!INCLUDE [outlook-name](includes/outlook-name.md)]
- [!INCLUDE [teams-name](includes/teams-name.md)]
- [!INCLUDE [word-name](includes/word-name.md)]
- [!INCLUDE [onedrive-for-business-name](includes/onedrive-for-business-name.md)]
- [!INCLUDE [powerbi-name](includes/powerbi-name.md)]
- Power Automate
- Power Apps
- Field Service
- Sales

| To | Go to |
| --- | --- |
|Use Business Central Outlook add-ins to explore financial data related to customers and vendors, or create and send financial documents, such as quotes and invoices.|[Use Business Central as Your Business Inbox in [!INCLUDE [outlook-name-short](includes/outlook-name-short.md)]](admin-outlook.md)|
|Use Microsoft Teams with [!INCLUDE [prod_short](includes/prod_short.md)] | [Business Central and Microsoft Teams](across-teams-overview.md) |
|Use [!INCLUDE [word-name](includes/word-name.md)] with [!INCLUDE [prod_short](includes/prod_short.md)] | [Work with Word layouts](ui-how-add-fields-word-report-layout.md) |
|Use OneDrive with [!INCLUDE [prod_short](includes/prod_short.md)] to store your files. | [Business Central and OneDrive](across-onedrive-overview.md) |
|Get insights into your [!INCLUDE [prod_short](includes/prod_short.md)] data with Power BI and the [!INCLUDE [prod_short](includes/prod_short.md)] content packs.|[Enabling Your Business Data for Power BI](admin-powerbi.md)|
|Use your [!INCLUDE [prod_short](includes/prod_short.md)] data as part of a workflow in Power Automate.|[Use Business Central in an Automated Workflow](across-how-use-financials-data-source-flow.md)|
|Make your [!INCLUDE [prod_short](includes/prod_short.md)] data available as a data source in Power Apps.|[Connecting to Your Business Central Data to Build a Business App Using Power Apps](across-how-use-financials-data-source-powerapps.md)|
|Create and manage work orders, track the progress of service tasks, assign resources, and capture consumption details.|[Integrate with Microsoft Dynamics 365 Field Service](admin-integrate-field-service.md)|
|View information in [!INCLUDE [prod_short](includes/prod_short.md)] while you're working in [!INCLUDE [crm_md](includes/crm_md.md)].|[Integrating with Dynamics 365 Sales](admin-prepare-dynamics-365-for-sales-for-integration.md)|

## Set up apps

On top of the core capabilities in [!INCLUDE [prod_short](includes/prod_short.md)], Microsoft adds some apps that are listed on the [Extension Management](https://businesscentral.dynamics.com/?page=2500) page. Each app provides a link to launch its setup page. Choose the **Set up** action to get started.  

You can also add capabilities to your [!INCLUDE [prod_short](includes/prod_short.md)] by adding AppSource apps. Learn more at [Customizing Business Central Online Using Extensions](ui-extensions.md).  

## Migrate data from other systems

If you migrate from other systems, you can transfer information such as customers, vendors, inventory, and bank accounts to your [!INCLUDE [prod_short](includes/prod_short.md)].

| To | Go to |
| --- | --- |
|Transfer customers, vendors, inventory, and bank accounts information from another system into [!INCLUDE[prod_short](includes/prod_short.md)]|[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md).|
|Use dedicated QuickBooks migration guides.|[Changing from a QuickBooks App to Business Central](across-quickbooks-to-business-edition.md)|

## Related information

[Company Information Overview](admin-company-information.md)  
[Administration](admin-setup-and-administration.md)  
[Finance](finance.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Inventory](inventory-manage-inventory.md)  
[Project Management](projects-manage-projects.md)  
[Fixed Assets](fa-manage.md)  
[Assembly Management](assembly-assemble-items.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Creating New Companies in [!INCLUDE[prod_short](includes/prod_short.md)]](about-new-company.md)  
[Getting Ready to Do Business](ui-get-ready-business.md)  
[Business Central Quick Starts](quick-start-business-central.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
