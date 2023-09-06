---
title: Export Your Business Central Data to Excel
description: You can export your financial reports and business intelligence data from Business Central to Excel, or open your data in Excel.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: analysis, reporting, financial report, business intelligence, BI, Excel
ms.search.form: 9901
ms.date: 04/01/2021
ms.author: bholtorf
---
# Export Your Business Data to Excel

Excel is a powerful tool to work with data. From inside [!INCLUDE[prod_short](includes/prod_short.md)], you can open any list in Excel. You can even modify data in Excel and then submit it back to [!INCLUDE [prod_short](includes/prod_short.md)]. The same capability makes it easy for you to take your data with you if you decide to cancel your subscription.

## Opening Lists in Excel

You can open data in Excel from any journal, list, or worksheet. You just open the page that you want, and then choose **Open in Excel**. For example, open the list of customers (search for **Customers**), and then choose **Open in Excel**. Your browser will prompt you to open or save the generated Excel workbook.  

> [!NOTE]
> Use this option when you do not want to make changes and publish those changes back to [!INCLUDE[prod_short](includes/prod_short.md)].  

Each list includes some columns. The export to Excel includes any columns that are in your current view. Change the columns by opening the shortcut menu for any column, and then specifying which columns that you want to see. The list of columns is different for most lists. The columns reflect the structure in the database that stores your data. If you aren't sure what type of data a certain column contains, add it to your view. You can always remove it again.  

### Edit Data in Excel

Your [!INCLUDE[prod_short](includes/prod_short.md)] experience includes an add-in for Excel so you can edit data in Excel. For more information, see [Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md).  

## Exporting Data to Other Finance Systems

If you decide to cancel your subscription for [!INCLUDE[prod_short](includes/prod_short.md)], you can export your data to Excel and take it with you to your next finance system.  

You can export all pages, but that might be more than you really need. So consider exporting the following essential pages, and remember to add all columns as described earlier:  

* Chart of Accounts  
* Customers  
* Vendors  
* Banks  
* Items  

If you want all your financial transactions as well, it's a large amount of data, so the export will often take more than a few minutes of time. The financial transactions are shown on the **General Ledger Entries** page.  

We recommend that you also consider exporting data from the following pages:  

* Customer Ledger Entries  
* Vendor Ledger Entries  
* Bank Account Ledger Entries  
* Item Ledger Entries  
* General Posting Setup  
* Customer Posting Groups  
* Vendor Posting Groups  
* Item Posting Groups  
* Bank Posting Group  
* G/L Budgets  
* G/L Budget Entries  
* Sales Quotes  
* Sales Invoices  
* Purchase Invoices  
* Contacts  
* Salespeople  

> [!NOTE]  
> If you have set up more than one company in [!INCLUDE[prod_short](includes/prod_short.md)], you must export the relevant data from each company.

> [!NOTE]
> You must have at least one of the following permissions to open or edit data in Excel:
>
> * Permission set *D365 Excel Export Action*  
> * System permission 6110 *Allow Action Export To Excel*.  

For more information, see [To get an overview of a user's permissions](ui-define-granular-permissions.md#to-get-an-overview-of-a-users-permissions).

## See Also
[Canceling Your Subscription for [!INCLUDE[prod_short](includes/prod_short.md)]](admin-cancel.md)  
[Importing Business Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md)  
[Finance](finance.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
