---
title: Viewing and Editing in Excel From Business Central (contains video)
description: Learn about how you can open the pages in Microsoft Excel from Business Central for better data analysis.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accountant, accounting, financial report
ms.date: 04/01/2021
ms.author: jswymer

---
# Viewing and Editing in Excel From Business Central

With pages that display a list of records in rows and columns, like a list of customers, sale orders, or invoices, you can export the list to Microsoft Excel, and view it there. Depending on the page, you have two options for viewing in Excel. Both options are available from the **Share** icon ![Share a page in another app.](media/share-icon.png) at the top of a page. You can either select the **Open in Excel** action or the **Edit in Excel** action on the page. This article explains the differences between the two actions.

## Open in Excel

With the **Open in Excel** action, you can make changes to the records in Excel, but you can't publish the changes back to [!INCLUDE[prod_short](includes/prod_short.md)]. You can only save the changes to Excel file, without affecting data in [!INCLUDE[prod_short](includes/prod_short.md)].

- With this action, Excel respects any filters on the page that limit the records shown. The Excel workbook will contain the same rows and columns that appear on the page in [!INCLUDE[prod_short](includes/prod_short.md)].

- This action works on both on Windows and macOS.

- Starting with update 18.3, you can also view lists that are shown in page parts, like the lines in a sales order. 

> [!NOTE]
> For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, the **Open in Excel** action is available by default. However, if you set up [!INCLUDE[prod_short](includes/prod_short.md)] on-premises for editing data in Excel, then the **Open in Excel** action is replaced by the **Edit in Excel** action.

[!INCLUDE [send-report-excel](includes/send-report-excel.md)]  

## Edit in Excel

The **Edit in Excel** action is available on most lists, but not all. With the **Edit in Excel** action, you make changes to records in Excel and then publish the changes back to [!INCLUDE[prod_short](includes/prod_short.md)]. When Excel opens, you'll see the **Excel Add-in** pane on the right.

- With this action, Excel respects most filters on the page that limit the records shown, so the Excel workbook will contain almost the same records and columns.

- To get the latest data from [!INCLUDE[prod_short](includes/prod_short.md)], choose **Refresh** in the the Excel Add-in pane.

- You can switch the company that you're working with. To switch company, select the **Options** icon ![Excel add-in options.](media/cogwheel.png "Excel add-in options") in the Excel Add-in pane, then select the company from the **Company** field.  

    > [!IMPORTANT]
    > When changing the company, make sure that the **Environment** field is not empty. If it is, then set it to one of the available options; otherwise, the add-in will not work correctly.  

If you make changes to the add-in, you must reload it to update the connection. To reload, use the ![Excel add-in menu](media/excel-addin-menu.png "Excel add-in menu") menu in the top-right corner of the add-in. If you can't load the add-in, talk to your administrator. If you're the administrator, see [Get the Business Central Add-in for Excel](admin-deploy-excel-addin.md).

> [!NOTE]
> The add-in works with Excel for the web (online) from any device as long as as use a supported browser. It also works with the Excel app for Windows (PC); but not for macOS.
>
> For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, the **Edit in Excel** action is only available if the Excel add-in has been configured by your administrator, and only available for the Web client. For administrators, if you want to learn how to install the Excel add-in, see [Setting up the Excel Add-In for Editing Business Central Data](/dynamics365/business-central/dev-itpro/administration/configuring-excel-addin).


<!-- Note for later: here we're immediately jumping to pretty advanced topics like changing company or reloading the addin. Fine to keep them for now. In the future, we will first need to explain in more detail the actual functionality of the addin, primarily these sub-sections:

Refreshing record data in Excel
Editing and publishing back to Business Central
Creating new records from Excel
Crafting your own editable Excel.
Point (4) is where it gets interesting for changing/specifying company, environment and other connection settings-->

### First-time sign-in

The **Edit in Excel** action requires that the Business Central add-in is installed in Excel. In some cases, your administrator may have set up the add-in to install automatically for you. In this case, you just have to sign in to Business Central in **Excel Add-in** pane with your user name and password. Otherwise, the **New Office Add-in** pane opens. To install the add-in, choose **Trust this add-in**, which will install the add-in directly from the Office Store.

If for some reason the add-in doesn't install, contact your admin or try to install it manually. For more information, see [Install the add-in manually for your own use](admin-deploy-excel-addin.md#install).

## See the differences between the options
<br><br>  

> [!Video https://go.microsoft.com/fwlink/?linkid=2086039]

## See Related Training at [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## See Also

[Analyzing Financial Statements in Microsoft Excel](finance-analyze-excel.md)  
[Working with Business Central](ui-work-product.md)  
[Enhancements to Excel integration in 2019 release wave 2](/dynamics365-release-plan/2019wave2/dynamics365-business-central/enhancements-excel-integration)  


[!INCLUDE[footer-include](includes/footer-banner.md)]