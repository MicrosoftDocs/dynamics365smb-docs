---
title: Use Excel to import data into Business Central| Microsoft Docs
description: Use the default configuration package to add customer data in Excel and import the data back into Business Central .
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: migration, Excel
ms.date: 04/01/2020
ms.author: edupont

---
# Importing Business Data from Other Finance Systems
When you sign up for [!INCLUDE[d365fin](includes/d365fin_md.md)], you can choose to create an empty company so that you can upload your own data and to test your new [!INCLUDE[d365fin](includes/d365fin_md.md)] company. Depending on the finance solution that your business uses today, you can transfer information about customers, vendors, inventory, and bank accounts.  

From the Role Center, you can start an assisted setup guide that helps you transfer the business data from an Excel file or from other formats. The type of files you can upload depends on the extensions that are available. For example, you can migrate data from QuickBooks because [!INCLUDE[d365fin](includes/d365fin_md.md)] includes an extension that handles the conversion from QuickBooks. If you want to migrate data from other finance solutions, you must either check if an extension is available for that solution or import from Excel.  

[!INCLUDE[d365fin](includes/d365fin_md.md)] includes templates for accounts, customers, vendors, and inventory items that you can choose to apply when you import your data.

You can import master data and some transactional data from other finance systems based on the default configuration package in [!INCLUDE[d365fin](includes/d365fin_md.md)]. On the **Configuration Packages** page, you can work with the package to import and validate the data before you apply the package.  

> [!TIP]  
> Alternatively, use data migration wizards to import data from QuickBooks or Dynamics GP. For more information, see [QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md) or [Dynamics GP Data Migration](ui-extensions-dynamicsgp-data-migration.md).

> [!NOTE]  
> For larger implementation work, you can use RapidStart Services for [!INCLUDE[d365fin](includes/d365fin_md.md)], which is an extensive toolkit for setting up new solutions based on customers' business requirements and setup data. RapidStart Services also offers functionality for import of business data. For more information, see [Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md).

To import item pictures, you can use a dedicated function on the **Inventory Setup** page. For more information, see [Import Multiple Item Pictures](inventory-how-import-item-pictures.md).

## Importing Data from Configuration Packages
[!INCLUDE[d365fin](includes/d365fin_md.md)] includes a configuration package that you can export to Excel and set up your data there. Then, you can import the data from Excel again. The package consists of 27 tables, including master data such as customers, vendors, items, and accounts, other basic setup tables such as shipping methods, and transactions tables such as sales header and lines.  

> [!NOTE]  
>   Working with configuration packages is advanced functionality, and we recommend that you contact your administrator. For more information, see [Importing Data from Legacy Accounting Software using a Configuration Package](across-import-data-configuration-packages.md).

## Working with Data in Excel
When you export the default configuration package to Excel, the generated workbook contains a worksheet for each table in the package. To simplify your tasks, you can take advantage of the XML manipulation tools that are built into Excel. You can also use Excel built-in functions to help with data formatting and to put data in the correct cell. For example, add a blank worksheet and copy the legacy data to it. Then make an Excel formula to map data in the transformation worksheet between the fields in the exported worksheet and customer legacy data. After you have mapped all of the data, copy the range of data onto the table worksheet.  

> [!IMPORTANT]  
>  Do not change the columns in the worksheets. If they are moved, changed, or deleted, the worksheet cannot be imported into [!INCLUDE[d365fin](includes/d365fin_md.md)].

> [!NOTE]
> Fields of type Blob cannot be exported/imported using Excel.

## Tables in the Default Configuration Package
The default configuration package supports the following tables:

-   Payment Terms
-   Customer Price Group
-   Shipment Method
-   Salesperson/Purchaser
-   Location
-   GL Account
-   Customer
-   Vendor
-   Item
-   Sales Header
-   Sales Line
-   Purchase Header
-   Purchase Line
-   Gen. Journal Line
-   Item Journal Line
-   Customer Posting Group
-   Vendor Posting Group
-   Inventory Posting Group
-   Unit of Measure
-   Gen. Business Posting Group
-   Gen. Product Posting Group
-   General Posting Setup
-   Territory
-   Item Category
-   Sales Price
-   Purchase Price

## See Also
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md)  
[Dynamics GP Data Migration](ui-extensions-dynamicsgp-data-migration.md)  
[Import Multiple Item Pictures](inventory-how-import-item-pictures.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
