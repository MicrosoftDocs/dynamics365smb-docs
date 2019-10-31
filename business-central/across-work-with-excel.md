---
title: Viewing and Editing in Excel From Business Central | Microsoft Docs
description: Learn about how you can open the pages in Microsoft Excel from Business Central for better data analysis.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accountant, accounting, financial report
ms.date: 10/24/2019
ms.author: jswymer

---
# Viewing and Editing in Excel From Business Central

With pages that display a list of records in rows and columns, like a list of customers, sale orders, or invoices, you can also view the records using Microsoft Excel. To do this, you have two options. You can either select the **Open in Excel** action or the **Edit in Excel** action on the page. The differences between the two actions is as follows:  

## Open in Excel

- With this action, Excel respects any filters on the page that limit the records shown. This means that the Excel workbook will contain the same rows and columns that appear on the page in [!INCLUDE[prodshort](includes/prodshort.md)].

- You can make changes to the records in Excel, but you cannot publish the changes back to [!INCLUDE[prodshort](includes/prodshort.md)]. You can only save the changes to Excel file on your computer. 

- This action works on both on Windows and macOS. 

> [!NOTE]
> For [!INCLUDE[prodshort](includes/prodshort.md)] on-premises, the **Open in Excel** action is available by default. However, if you set up [!INCLUDE [prodshort](includes/prodshort.md)] on-premises for editing data in Excel, then the **Open in Excel** action is replaced by the **Edit in Excel** action.

## Edit in Excel

- With this action, Excel respects most filters on the page that limit the records shown. This means that the Excel workbook will contain almost the same records and columns.

- The advantage of the **Edit in Excel** action is that it lets you make changes to records in Excel and then publish the changes back to [!INCLUDE[prodshort](includes/prodshort.md)].

- It only works on Windows; not macOS.

This was enhanced in 2019 release wave 2. For more information, see [Enhancements to Excel integration](/dynamics365-release-plan/2019wave2/dynamics365-business-central/enhancements-excel-integration).

> [!NOTE]
> For [!INCLUDE[prodshort](includes/prodshort.md)] on-premises, the **Edit in Excel** action is only available if the Excel add-in has been configured by your administrator. For administrators, if you want to learn how to install the excel add-in, see [Setting up the Excel Add-In for Editing Business Central Data](/dynamics365/business-central/dev-itpro/administration/configuring-excel-addin).

> [!NOTE]
> For [!INCLUDE[prodshort](includes/prodshort.md)] on-premises, this feature is only available for the Web client.

### See the differences between the options 
> [!Video https://go.microsoft.com/fwlink/?linkid=2086039]

## See Also
[Working with Business Central](ui-work-product.md)  
