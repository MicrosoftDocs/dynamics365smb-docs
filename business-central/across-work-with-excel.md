---
title: View and Edit Business Central Data in Excel
description: Learn when to open Business Central lists in Excel for analysis and when to use the Excel add-in to edit records and publish your changes.
author: jswymer
ms.topic: concept-article
ms.devlang: al
ms.search.form: 1480,
ms.search.keywords: accountant, accounting, financial report
ms.date: 11/09/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# View and edit in Excel from Business Central

With pages that display a list of records in rows and columns, such as a list of customers, sale orders, or invoices, you can export the list to Microsoft Excel and view it there. Depending on the page, you have two options for viewing in Excel. Both are available from the **Share** icon :::image type="icon" source="media/share-icon.png"::: at the top of a page. You can either select the **Open in Excel** action or the **Edit in Excel** action on the page. This article explains the two actions.

> [!TIP]
> When you export data from [!INCLUDE[prod_short](includes/prod_short.md)] to Excel, you can use Copilot in Excel to help prepare, format, and analyze the data. Availability depends on your Microsoft 365 license and your organization's tenant configuration. Learn more in [Use Copilot in Excel to enhance data tasks](#use-copilot-in-excel-to-enhance-data-tasks).

## Open in Excel

With the **Open in Excel** action, you can make changes to the records in Excel, but you can't publish the changes back to [!INCLUDE[prod_short](includes/prod_short.md)]. You can only save the changes to the Excel file, without affecting data in [!INCLUDE[prod_short](includes/prod_short.md)].

- Excel respects filters on the page that limit the records shown. The Excel workbook has the same rows and columns that appear on the page in [!INCLUDE[prod_short](includes/prod_short.md)].
- This action works on both Windows and macOS.
- [!INCLUDE[open-edit-excel](includes/open-and-edit-excel.md)]

<!-- 
> [!IMPORTANT]
> For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, the **Open in Excel** action is available by default. However, if you set up [!INCLUDE[prod_short](includes/prod_short.md)] on-premises for editing data in Excel, then the **Open in Excel** action is replaced by the **Edit in Excel** action.-->

[!INCLUDE [send-report-excel](includes/send-report-excel.md)] 

> [!NOTE]
> In Excel, whole numbers in columns have a decimal symbol at the end (like a period `.` or comma `,`) even though the decimal symbol isn't shown in Business Central. The decimal symbol depends on your device's region settings. For example, `10` in Business Central could appear as `10.` or `10,` in Excel. You can change the format in Excel by selecting the values, then selecting <kbd>Ctrl</kbd>+<kbd>1</kbd>. Learn more about changing the number format in Excel at [Format numbers](https://support.microsoft.com/office/format-numbers-f27f865b-2dc5-4970-b289-5286be8b994a).

## Edit in Excel

The **Edit in Excel** action is available on most lists, but not all. With the **Edit in Excel** action, you make changes to records in Excel and then publish the changes back to [!INCLUDE[prod_short](includes/prod_short.md)]. When Excel opens, the **Excel Add-in** pane displays.

- With this action, Excel respects most filters on the page that limit the records shown, so the Excel workbook has almost the same records and columns.
- To get the latest data from [!INCLUDE[prod_short](includes/prod_short.md)], choose **Refresh** in the Excel Add-in pane.
- [!INCLUDE[open-edit-excel](includes/open-and-edit-excel.md)]

### First-time sign-in

The **Edit in Excel** action requires that the Business Central add-in is installed in Excel. In some cases, your administrator might set up the add-in to install automatically for you. In this case, you just have to sign in to Business Central in the **Excel Add-in** pane with your user name and password. Otherwise, the **New Office Add-in** pane opens. To install the add-in, choose **Trust this add-in**, which installs the add-in directly from the Office Store.

If the add-in doesn't install, either contact your admin or try to install it manually. Learn more in [Install the add-in manually for your own use](admin-deploy-excel-addin.md#install).

### Work across environments and companies

You can switch the company that you're working with. To switch a company, select the **Options** icon :::image type="icon" source="media/cogwheel.png"::: in the Excel Add-in pane, then select the company from the **Company** field.  

> [!IMPORTANT]
> When changing the company, make sure that the **Environment** field isn't empty. If it is, then set it to one of the available options; otherwise, the add-in doesn't work correctly.  

If you make changes to the add-in, you must reload it to update the connection. To reload, use the :::image type="icon" source="media/excel-addin-menu.png"::: menu in the upper-right corner of the add-in. If you can't load the add-in, talk to your administrator. Refer to [Get the Business Central add-in for Excel](admin-deploy-excel-addin.md) if you're the administrator.

> [!NOTE]
> The add-in works with Excel for the web (online) from any device as long as you use a supported browser. It also works with the Excel app for Windows (PC), but not for macOS.
>
> For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, the **Edit in Excel** action is only available if the Excel add-in has been configured by your administrator, and only available for the web client. For administrators, if you want to learn how to install the Excel add-in, see [Setting up the Business Central add-in for Excel in Business Central on-premises](/dynamics365/business-central/dev-itpro/administration/configuring-excel-addin).

### Limits when using Excel for the web

When **Edit in Excel** is used on list pages for tables with many columns, the resulting workbook might have too many columns for the file to be viewed in Excel for the web. [!INCLUDE[prod_short](includes/prod_short.md)] automatically limits the exported workbook to 99 columns when OneDrive is configured for system features.

<!--## See the differences between the options
<br><br>  

> [!Video https://go.microsoft.com/fwlink/?linkid=2086039]-->

<a name="use-agentic-excel-to-enhance-data-tasks"></a>

## Use Copilot in Excel to enhance data tasks

When you export data from [!INCLUDE[prod_short](includes/prod_short.md)] to Excel using **Open in Excel**, **Edit in Excel**, or financial report layouts, you can use Copilot in Excel to describe tasks in natural language. Copilot can edit the workbook directly in edit mode, propose a plan first in plan mode, or answer questions in chat mode. Review its output before using the results.

> [!NOTE]
> The workbook-editing capabilities previously called *Agent Mode* are now part of the regular Copilot in Excel experience.

### Scenario: Clean and prepare Business Central data

Copilot in Excel can help you prepare exported lists before you publish changes back to [!INCLUDE [prod_short](includes/prod_short.md)]. You can use natural language instructions to:

* Remove duplicates, standardize text formatting, or highlight anomalies and missing values.
* Fill in missing fields, apply consistent naming conventions, or detect unexpected outliers in item, vendor, or pricing data.
* Restructure a separate analysis worksheet or prepare data for a configuration package. Don't rename or remove the tables, bound columns, or key fields that the Excel add-in needs to publish changes.

Review the results before publishing changes to master data. Use **Open in Excel** when you want to explore or reshape data without a connection that can publish changes.

### Scenario: Analyze business data efficiently

After you export data from [!INCLUDE[prod_short](includes/prod_short.md)], Copilot in Excel can help you analyze the data by creating:

* Summaries and trends written in natural language.
* Charts, PivotTables, and dashboards.
* Conditional formatting rules to highlight key patterns, such as aging balances or low inventory levels.

You can generate insights without building formulas or complex workbook structures.

### Scenario: Support for iterative and multi-step workflows

Copilot in Excel can do multistep tasks that would otherwise require several manual operations. For example, you can:

1. Export a list of items from [!INCLUDE[prod_short](includes/prod_short.md)].
1. Ask Excel to clean inconsistent descriptions.
1. Request grouping by item category and generate a chart of sales trends.
1. Reformat a separate copy of the output to prepare it for import into a configuration package.

This conversational, iterative experience helps you refine results step-by-step without knowing specific Excel functions.

### Scenario: Format Excel templates for financial reports

Copilot in Excel can help you format the raw Excel output for a financial report from the Financial Reporting feature.

To learn more, go to [Format your report worksheet with Copilot in Excel](finance-financial-reporting-integrate-financial-reports-with-excel.md).

### Considerations when working with data

Copilot in Excel works in the workbook. If you use **Edit in Excel**, review the changes before choosing **Publish** in the Excel add-in. With **Open in Excel**, changes stay in the workbook and can't be published through the add-in. Configuration packages and report layouts have separate import procedures. Follow your organization's data governance practices, especially when working with sensitive data.

### Availability of Copilot in Excel

Availability depends on your Microsoft 365 license and your organization's tenant configuration.

To learn more, go to [Frequently asked questions about Copilot in Excel](https://support.microsoft.com/en-us/excel/copilot/frequently-asked-questions-about-copilot-in-excel).

## Related information

[Frequently asked questions about Copilot in Excel](https://support.microsoft.com/en-us/excel/copilot/frequently-asked-questions-about-copilot-in-excel)  
[Analyze list data using data analysis mode](analysis-mode.md)  
[Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
