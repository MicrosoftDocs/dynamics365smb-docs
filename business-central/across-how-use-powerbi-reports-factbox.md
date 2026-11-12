---
title: Display Custom Power BI Reports in Business Central
description: Create and configure custom Power BI reports for Business Central list pages, with report filters and layouts that work in the Power BI FactBox.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords: business intelligence, KPI, Odata, Power App, SOAP, analysis
ms.date: 11/11/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

# Create Power BI reports for displaying list data in [!INCLUDE[prod_short](includes/prod_short.md)]

[!INCLUDE[prod_long](includes/prod_long.md)] includes a Power BI FactBox control element on many key list pages. The purpose of this FactBox is to display Power BI reports that are related to records in the lists, providing extra insight into the data. The idea is that as you move between rows in the list, the report updates for the selected entry.

[!INCLUDE[prod_long](includes/prod_long.md)] comes ready with some of these reports. You can also create your own custom reports that display in this FactBox. Creating these reports is similar to other reports. But there are a few design rules you have to follow to make sure the reports display as expected. These rules are explained in this article.

> [!NOTE]
> Refer to [Build Power BI Reports to Display [!INCLUDE [prod_long](includes/prod_long.md)] Data](across-how-use-financials-data-source-powerbi.md) for general information about creating and publishing Power BI reports for Business Central.

## Prerequisites

- A Power BI account.
- Power BI Desktop.

<!-- 
For more information about getting started, see [Use [!INCLUDE[prod_short](includes/prod_short.md)] as a Power BI Data Source](across-how-use-financials-data-source-powerbi.md).-->

## Create a report for a list page

1. Start Power BI Desktop.
1. Select **Get Data**, and start choosing the data source for the report.

    Specify the Business Central list pages that contain the data that you want in the report. For example, to create a report for the **Sales Invoices** list, include pages related to sales.

    Follow the instructions [Add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop](across-how-use-financials-data-source-powerbi.md#getdata) for more information.

1. Set the report filter.

    To make the data update to the selected record in the list, you add a filter to the report. The filter must include a field of the data source that's used to uniquely identify each record in the list. In developer terms, this field is the *primary key*. In most cases, the primary key for a list is the **No.** field.

    To set the filter, do the following steps:

    1. In the **Filters**, select the primary key field from the list of available fields.
    1. Drag the field to the **Filters** pane and drop it in the **Filters on all pages** box.
    1. Set the **Filter type** to **Basic filtering**. The filter must apply to all report pages, not to an individual page or visual. Business Central updates the first basic report-level filter, so ensure that this filter uses the field that identifies the list record.

    :::image type="content" source="./media/across-how-use-powerbi-reports-factbox/financials-powerbi-report-filter-v3.png" alt-text="Set the report filter for the Sales Invoice Activity report.":::
1. Design the report layout.

    Create the layout by dragging fields and adding visualizations. Learn more in [Work with Report view in Power BI Desktop](/power-bi/create-reports/desktop-report-view) in the Power BI documentation.

1. See the next sections about sizing the report and using multiple pages.

1. Save and name the report.

    Give the report a name that helps users recognize the associated list page, such as `Sales Invoices Activity.pbix`. The **Power BI Reports Selection** page lists reports grouped by workspace. The report name doesn't have to match the list page name.

1. When you're done, publish the report as usual.

    Learn more in [Publishing a Report](across-how-use-financials-data-source-powerbi.md#publish-reports).

1. Test the report.

    Once the report's been published to your workspace, it should be available from the Power BI FactBox on the list page in [!INCLUDE[prod_short](includes/prod_short.md)].

    To test it, do the following steps.

    1. Open [!INCLUDE[prod_short](includes/prod_short.md)] and go to the list page.
    1. If you don't see the Power BI FactBox, go to the action bar, and then select **Actions** > **Display** > **Show/Hide Power BI Reports**.
    1. In the Power BI FactBox, select **Select Report**, select the **Enabled** box for the report, and then select **OK**.

    If designed correctly, the report displays.  

## Set the report size and color

Design a compact report layout that fits the Power BI FactBox in [!INCLUDE[prod_short](includes/prod_short.md)]. Starting with version 27, the client determines the space available for the embedded report. A canvas size of 325 pixels by 310 pixels is a starting point, not a required size. Test the layout in the FactBox.

:::image type="content" source="./media/across-how-use-powerbi-reports-factbox/financials-powerbi-report-sizing-v3.png" alt-text="Set the report width and height for the Sales Invoice Activity report.":::

You can change the width and height of the report by choosing **Custom** in the **Type** field.

If you want the background of the report to blend with the background color of the Power BI FactBox control, set report background color to *#FFFFFF* (white). 

> [!TIP]
> Use the [!INCLUDE [prod_short](includes/prod_short.md)] theme file to build reports with the same color styling as the [!INCLUDE [prod_short](includes/prod_short.md)] apps. Learn more in [Use the [!INCLUDE [prod_short](includes/prod_short.md)] report theme](across-how-use-financials-data-source-powerbi.md#theme).

## Reports with multiple pages

With Power BI, you can create a single report with multiple pages. However, for reports that display with list pages, don't use more than one page. The Power BI FactBox hides page navigation. Business Central remembers the selected report page, including a page selected in expanded mode.

## Troubleshoot embedded report display

This section explains how to fix problems that you might run into when you try to view a Power BI report for a list page in [!INCLUDE[prod_short](includes/prod_short.md)].  

### You can't see the Power BI FactBox on a list page

By default, the Power BI FactBox is hidden from view. To show the FactBox on a page, from the action bar, select **Actions** > **Display** > **Show/Hide Power BI Reports**.

### You can't see the report in the report selection page

Expand the workspace that contains the report on the **Power BI Reports Selection** page. Verify that your Power BI account has access to the report and its workspace.

### Report is loaded but blank, not filtered, or filtered incorrectly

Verify that the first basic report-level filter contains the right primary key. In most cases, this field is the **No.** field, but in the **G/L Entry** table, for example, you must use the **Entry No.** field.

### Report is loaded, but it shows a page you didn't expect

Select **Expand** and choose the report page you want to display if page navigation is available. Business Central remembers the selected page. For a custom report designed for a list FactBox, use a single report page to avoid ambiguity.

### Report appears with an unwanted gray border, or it's too small or too large

Adjust the report's canvas size to fit the FactBox. Publish the updated report, and then reload the report in [!INCLUDE[prod_short](includes/prod_short.md)].

## Related information

[Enable Your Business Data for Power BI](admin-powerbi.md)  
[Use [!INCLUDE[prod_short](includes/prod_short.md)] as a Power BI Data Source](across-how-use-financials-data-source-powerbi.md)  
[Get Ready for Doing Business](ui-get-ready-business.md)  
[Set Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finance](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
