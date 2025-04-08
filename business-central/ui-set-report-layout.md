---
title: Setting the Report Layout
description: Learn how to set the layout that's used on a report when previewing and printing.
author: jswymer
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 9652, 9650
ms.date: 06/13/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Set the layout used by a report

> **APPLIES TO:** Business Central online, Business Central on-premises 2022 release wave 1 and later. For earlier versions, go [here](ui-how-change-layout-currently-used-report.md).

A report layout determines the look of a report. It controls which data fields of a report dataset appear, how they're arranged, styled, and more. A report may have more than one layout, which you can then switch among as needed.

When there are multiple companies in the application, the layouts are set on a per-company basis. So the same report in one company can have a different layout in another company.

## Get started

There are a few ways to set which layout a report uses. Each way has advantages, depending on what you're looking to do: 

- From the report request page

  When setting up a report to run, the report request page includes the **Reports Layout** field that shows the current default layout used by the report. You can use this field to temporarily switch to another available layout the report you're running. After you run the report, the layout will revert to the default layout again. For more information, see [Run and Print Reports](ui-work-report.md#switch-the-report-layout).

- From the **Report Layout Selection** page

  The **Report Layout Selection** page displays a list of all reports. This page indicates what the current default layout for a report is. It lets you set layouts in different companies, without having to switch the company you're working with.

- From the **Report Layouts** page
  The **Report Layouts** page displays all available layouts for each report in the current company. It's also used to specify the default layout for reports. It's easy to find a specific layout by sorting or filtering the list. Once you find the layout, you can set it for a report with a single selection.

  > [!NOTE]
  > You can't use the **Report Layouts** page for Word and RDLC layouts that were created by using the legacy **Custom Layouts** feature. In fact, you won't even see these custom layouts listed on the **Report Layouts** page. For these layouts, you can only set them by using **Report Layout Selection** page.

## Set the layout from the Report Layouts page

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. Find the layout in the list, select it, then select the **Set Default** action at the top of the page.

## Set the layout from Report Layout Selection page

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layout Selection**, and then choose the related link.
  
   The page lists all the reports that are available for the company that's specified in the **Company** field at the top of the page. The **Layout Description** field specifies the layout that the report currently uses.
2. Set the **Company** field at the top to the company that includes the report.
3. Find and select the report in the list, then do one of the following steps:

   - If the layout that you want to switch to is a different type than the current layout, select the **Layout Type** field, then choose the type of the layout you want to set on the report. 
   - If the layout that you want to switch to the same type as the current layout, select the **Select Layout** action at the top.

4. In the **Report Layouts** page, select the layout, then select **OK**.

## Revert to the original default layout

Reports are designed to use a layout by default. You can switch back to the original default layout from **Report Layout Selection** page. Just select the report, then select the **Restore Default Selection** action at the top of the page.

## See Also

[Managing Report Layouts](ui-manage-report-layouts.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
