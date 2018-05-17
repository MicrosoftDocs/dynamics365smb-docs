---
title: Use Excel to import data into Financials| Microsoft Docs
description: Use the default configuration package to add customer data in Excel and import the data back into Finance and Operations, Business edition .
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: migration, Excel
ms.date: 03/07/2018
ms.author: edupont

---
# Importing Data from Legacy Accounting Software using a Configuration Package
You can import master data and some transactional data from other finance systems based on the default configuration package in [!INCLUDE [d365fin](includes/d365fin_md.md)]. In the **Configuration Packages** window, you can work with the package to import and validate the data before you apply the package.  

> [!NOTE]
> Configuration packages are part of RapidStart Services for [!INCLUDE [d365fin](includes/d365fin_md.md)], an extensive toolkit for setting up new solutions based on customers' business requirements and setup data. RapidStart Services also offers functionality for import of legacy data. For more information, see [Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md).
> 
> [!TIP]
>   Alternatively, use data migration wizards to import data from QuickBooks or Dynamics GP. For more information, see [QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md) or [Dynamics GP Data Migration](ui-extensions-dynamicsgp-data-migration.md).  

## Working with Data in Excel
When you export the default configuration package to Excel, the generated workbook contains a worksheet for each table in the package. To simplify your tasks, you can take advantage of the XML manipulation tools that are built into Excel. You can also use Excel built-in functions to help with data formatting and to put data in the correct cell. For example, add a blank worksheet and copy the legacy data to it. Then make an Excel formula to map data in the transformation worksheet between the fields in the exported worksheet and customer legacy data. After you have mapped all of the data, copy the range of data onto the table worksheet.  

> [!IMPORTANT]
>  Do not change the columns in the worksheets. If they are moved, changed, or deleted, the worksheet cannot be imported into [!INCLUDE [d365fin](includes/d365fin_md.md)].

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

## Importing Customer Data
After the customer data has been entered in Excel, you import the data into [!INCLUDE [d365fin](includes/d365fin_md.md)]. In the **Configuration Packages** window, you import the data from the Excel file, and you can validate that the data is consistent with [!INCLUDE [d365fin](includes/d365fin_md.md)] before you apply the package.

## See Also
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Setting Up a Company With RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[QuickBooks Data Migration](ui-extensions-quickbooks-data-migration.md)  
[Dynamics GP Data Migration](ui-extensions-dynamicsgp-data-migration.md)  

## [!INCLUDE [d365fin](includes/free_trial_md.md)]  
## [!INCLUDE [d365fin](includes/training_link_md.md)]
