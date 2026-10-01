---
title: Set the Layout Used by a Report in Business Central
description: Learn how to select the default report layout for each company, temporarily use another layout, and distinguish layout selection from reusable branding.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 9652, 9650
ms.date: 09/09/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Set the layout used by a report

> **APPLIES TO:** Business Central online, Business Central on-premises 2022 release wave 1 and later. For earlier versions, learn more in [Set the layout used by a report in earlier versions](ui-how-change-layout-currently-used-report.md).

A report layout determines the content and format of a report. It controls which data fields appear, how they're arranged, and how the report is styled. A report can have more than one layout, which you can switch among as needed.

Select the default layout for each company. The same report can use a different default layout in each company.

## Distinguish layout selection from composite branding

Selecting a report layout and assigning reusable parts are separate tasks:

| Task | What it controls | Where to do it |
|---|---|---|
| Select the default layout | Which layout the report uses by default in a company | **Report Layouts** or **Report Layout Selection** |
| Select a layout for one run | Which available layout the report uses temporarily | The report request page |
| Assign a theme and header/footer | Which reusable branding parts are combined with a Word layout whose **Subtype** is **Body** | The **Composite layout** actions on **Report Layouts** |

The composite-layout actions are available when the **Document Report Experience** feature is enabled on the **Feature Management** page. Learn more about turning on features in [Enabling new and upcoming features ahead of time](admin-feature-management.md). Assigning a theme or header/footer doesn't change which body layout is the default. Likewise, when you change which body layout is the default, the theme and header/footer assignments from the previous default aren't copied to the new one. Learn more in [Set up reusable themes and header/footer layouts](ui-set-up-report-themes-header-footer-layouts.md).

## Get started

You can set the layout for a report in several ways. Each method has advantages, depending on what you want to do:

- From the report request page

  When you set up a report to run, the report request page includes the **Report Layout** field, which shows the current default layout. Use this field to temporarily select another available layout for that run. The selection doesn't change the default layout. Learn more in [Run and print reports](ui-work-report.md#switch-the-report-layout).

- From the **Report Layout Selection** page

  The **Report Layout Selection** page displays a list of all reports. This page indicates what the current default layout for a report is. It lets you set layouts in different companies, without having to switch the company you're working with.

- From the **Report Layouts** page

  The **Report Layouts** page displays all available layouts for each report in the current company. It's also used to specify the default layout for reports. It's easy to find a specific layout by sorting or filtering the list. Once you find the layout, you can set it for a report with a single selection.

  > [!NOTE]
  > You can't use the **Report Layouts** page for Word and RDLC layouts that you created by using the legacy [Custom Layouts feature](ui-how-create-custom-report-layout.md). You won't see these custom layouts listed on the **Report Layouts** page. For these layouts, you can only set them by using the **Report Layout Selection** page.

## Set the layout from the Report Layouts page

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Find and select the layout in the list.
1. Select **Layout** > **Set as default**.

## Set the layout from the Report Layout Selection page

The page lists the available reports. The **Company Name** field determines the company for which you set the default layout. The **Layout Description** field shows the layout that the report currently uses in that company.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Report Layout Selection**, and then select the related link.
1. Set the **Company Name** field to the company for which you want to select the default layout.
1. Find and select the report, and then use one of the following options:

   - If the layout is a different type than the current layout, select the **Layout Type** field, and then select the type.
   - If the layout is the same type as the current layout, select **Select Layout**.

1. On the page that opens, select the layout, and then select **OK**.

## Revert to the original default layout

Reports are designed to use a layout by default. You can switch back to the original default layout from the **Report Layout Selection** page. Select the report, and then select **Restore Default Selection**.

## Related information

[Set up reusable themes and header/footer layouts](ui-set-up-report-themes-header-footer-layouts.md)  
[Report and document layouts overview](ui-manage-report-layouts.md)  
[Get started creating report layouts](ui-get-started-layouts.md)  
[Run and print reports](ui-work-report.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
