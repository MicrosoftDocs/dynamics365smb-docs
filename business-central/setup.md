---
title: Overview of Tasks to Set Up Business Central
description: Read an overview of the tasks necessary to set up, initialize, and configure Business Central to suit your needs.
author: brentholtorf
ms.topic: overview
ms.devlang: al
ms.search.keywords: configure, initialize
ms.date: 12/19/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Overview of Tasks to Set Up [!INCLUDE[prod_short](includes/prod_short.md)]

[!INCLUDE[prod_short](includes/prod_short.md)] includes standard configurations for most business processes, but you can change the configuration to suit the needs of your organization. The [Business Central quick start](quick-start-business-central.md) articles help you take the first steps into making [!INCLUDE [prod_short](includes/prod_short.md)] your own. This article provides an overview of how you can configure [!INCLUDE [prod_short](includes/prod_short.md)] for your organization.

For example, the chart of accounts is prefilled with posting accounts that are ready for use. You can, of course, change the chart of accounts to suit your needs. Learn more at [Finance](finance.md).

Some areas described below require you to be an administrator in your [!INCLUDE[prod_short](includes/prod_short.md)] subscription. Learn more at [Administration](admin-setup-and-administration.md).  


## Assisted setup guides

From the ![Sprocket icon to open the Settings menu.](media/ui-experience/settings_icon_small.png) menu, you can access assisted setup guides to help you configure certain scenarios and add features to [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more about how to access all assisted and manual setup pages at [Getting Ready to Do Business](ui-get-ready-business.md).

:::image type="content" source="media/assisted-setup.png" alt-text="Screenshot of the assisted setup page" lightbox="media/assisted-setup.png":::

> [!NOTE]
> [!INCLUDE [ua-checklist](includes/ua-checklist.md)]


## Set up companies

[!INCLUDE[prod_short](includes/prod_short.md)] organizes business entities in *companies*. For each company, you must fill in some of the basic company details and relevant information on the **Company Information** page. Each company also contains setup data that you need to define.

| To | See |
| --- | --- |
|Improve the quality of implementation and shorten deployment time by using a toolset for setting up a new company using wizards, templates, worksheets, and customer questionnaires.|[Setting Up a Company With Configuration Packages](admin-set-up-a-company-with-rapidstart.md)|
| Ease working with multiple companies. | [Set up Company information](admin-company-information.md) |


## Set up general functionality

In addition to the assisted setup guides, some general functionality can be set up manually. The following table lists some of functionality you can set up manually.

| To | See |
| --- | --- |
|Set up and assign a base calendar to your company and its business partners, such as customers, vendors, or locations. Delivery and receipt dates on future sales order, purchase order, transfer order, and production order lines are then calculated according to the calendar's specified working days.|[Set Up Base Calendars](across-how-to-assign-base-calendars.md)|
| Set up unique identification codes for records, such as cards, documents, and journal lines, to track them in the system. |[Create Number Series](ui-create-number-series.md) |
|Access your Business Central data from your mobile device.|[Getting Business Central on Your Mobile Device](install-mobile-app.md)|
|Set up email communication in and out of [!INCLUDE[prod_short](includes/prod_short.md)].| [Set Up Email Manually or Using the Assisted Setup](admin-how-setup-email.md)|
|Connect to cloud-enabled printers.| [Printer Setup and Management Overview](admin-printer-setup-overview.md)|
|Set up default reports to use to print sales, purchases, and service documents, such as orders, quotes, and invoices, and which layout is used. | [Report selection for documents](across-report-selections.md)|


## Set up business processes

In addition to the assisted setup guides, specific business processes can be set up manually. The following table lists some of functionality you can set up manually.

| To | See |
| --- | --- |
| Set up payment methods, currencies, and the chart of accounts, and define rules and defaults for managing financial transactions. |[Setting Up Finance](finance-setup-finance.md) |
| Set up your own and your vendors' bank accounts and enable services for importing and exporting bank files. |[Setting Up Banking](bank-setup-banking.md) |
| Configure the rules and values that define your company's sales policies, register new customers, and set up how you communicate with customers. |[Setting Up Sales](sales-setup-sales.md) |
| Configure the rules and values that define your company's purchasing policies, register new vendors, and prioritize your vendors for payment processing. |[Setting Up Purchasing](purchasing-setup-purchasing.md) |
| Configure the rules and values that define the company's inventory policies, set up locations if you keep inventory in multiple warehouses, and categorize your items to improve searching and sorting. |[Setting Up Inventory](inventory-setup-inventory.md) |
| Set up resources, time sheets, and projects to manage projects. |[Setting Up Project Management](projects-setup-projects.md) |
| Configure how to insure, maintain, and depreciate fixed assets and set up how you record the costs of fixed assets in your company books. |[Setting Up Fixed Assets](fa-setup.md) |
|Define the general rules and values for warehouse processes and specific handling at each location.|[Setting Up Warehouse Management](warehouse-setup-warehouse.md)|
|Prepare production bills of materials (BOMs) and routings to define how end items are produced, and prepare machine or work centers to perform the required operations.|[Setting Up Manufacturing](production-configure-production-processes.md)|
|Establish standard services, symptoms, and fault codes and set up the service items, resources, and documentation needed to provide service to your customers.|[Setting Up Service Management](service-setup-service.md)|
|Read best practices for setting up items for inventory costing and supply planning.|[Setting Up Complex Application Areas Using Best Practices](set-up-complex-application-areas-using-best-practices.md)|


## Use Outlook, Teams, Onedrive, Power BI, Power Automate, and Power Apps

You can enhance your [!INCLUDE[prod_short](includes/prod_short.md)] experience by connecting to other Microsoft products such as Outlook, Teams, Onedrive, Power BI, Power Automate, and Power Apps.

| To | See |
| --- | --- |
|Use Business Central Outlook add-ins to see financial data related to customers and vendors or create and send financial documents, such as quotes and invoices.|[Use Business Central as Your Business Inbox in Outlook](admin-outlook.md)|
|Use Microsoft Teams with Business Central | [Business Central and Microsoft Teams](across-teams-overview.md) |
|Use OneDrive for Business with Business Central to store your files. | [Business Central and OneDrive](across-onedrive-overview.md) |
|Get insights into your Business Central data with Power BI and the Business Central content packs.|[Enabling Your Business Data for Power BI](admin-powerbi.md)|
|Use your Business Central data as part of a workflow in Power Automate.|[Use Business Central in an Automated Workflow](across-how-use-financials-data-source-flow.md)|
|Make your Business Central data available as a data source in Power Apps.|[Connecting to Your Business Central Data to Build a Business App Using Power Apps](across-how-use-financials-data-source-powerapps.md)|
|Do bulk invoicing of appointments created in Microsoft Bookings.|[Bulk Invoicing for Microsoft Bookings](finance-bookings.md)|


## Set up apps

On top of the core capabilities in [!INCLUDE [prod_short](includes/prod_short.md)], Microsoft adds some aps that are listed in [the **Extension Management** page](https://businesscentral.dynamics.com/?page=2500). Starting in October 2022, each app provides a link to launch its setup page - just choose the **Set up** action.  

You can also add capabilities to your [!INCLUDE [prod_short](includes/prod_short.md)] by adding AppSource apps. Learn more at [Customizing Business Central Online Using Extensions](ui-extensions.md).  

## Migrate data from other systems

If you migrate from other systems, you can transfer information such as customers, vendors, inventory, and bank accounts to your [!INCLUDE [prod_short](includes/prod_short.md)].

| To | See |
| --- | --- |
|Transfer customers, vendors, inventory, and bank accounts information from another system into [!INCLUDE[prod_short](includes/prod_short.md)]|[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md).|
|Use dedicated Quickbooks migration guides.|[Changing from a QuickBooks App to Business Central](across-quickbooks-to-business-edition.md)|


## See also

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
