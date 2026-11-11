---
title: (Obsolete) Set the Layout Used by a Report
description: Change the layout used by a report in versions of Business Central that still include the legacy Report Layout Selection and Custom Report Layouts pages.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 9652, 9650
ms.date: 11/11/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---
# (Obsolete) Set the layout used by a report

[!INCLUDE[legacy-custom-layouts](includes/legacy-custom-layouts.md)]

These procedures apply only to versions that still include the legacy pages. For the current workflow, learn more in [Set the layout used by a report](ui-set-report-layout.md).

A report can be set up with more than one report layout, which you can then switch among as needed.

Depending on the layouts that are available for a report, you can choose to use a built-in RDLC report layout, a built-in Word report layout, or a custom layout. Learn more in [Manage report layouts](ui-manage-report-layouts.md).

When custom report layouts are defined, you can select them from customer and vendor cards to specify that the selected layouts will be used for documents that you create for the customer or vendor in question. Learn more in [Define document layouts for customers and vendors](ui-define-customer-vendor-document-layouts.md).

> [!TIP]  
> Document reports (not lists) that use a Word report layout are typically faster than those that use an RDLC report layout. So if you have the option to choose between a Word or RDLC report layout for a document report, use the Word report layout for the best performance.

## Change the report layout type

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Report Layout Selection**, and then choose the related link.
  
   The **Report Layout Selection** page lists all the reports that are available for the company that's specified in the **Company Name** field at the top of the page. The **Layout Description** field specifies the layout that's currently used on the report.
1. Set the **Company Name** field to the company that includes the report.

   This field lets you set different layouts for the same report in different companies.

1. On the row for the report, set the **Layout Type** field to one of the following options:
   * **RDLC**: Uses a built-in RDLC report layout.
   * **Word**: Uses a built-in Word report layout.
   * **Custom Layout**: Uses a legacy custom layout.
1. If prompted, select the layout to use.

> [!NOTE]
> If you choose **RDLC** or **Word** and get an error that the report doesn't have a layout of that type, choose another layout type or create a custom layout of the required type.

If you selected a built-in RDLC or Word report layout, then no further action is required, and the layout will be used the next time the report is run.

## Change the selected custom layout

You may also want to change the currently used custom layout. Learn more in [Create and modify custom report layouts](ui-how-create-custom-report-layout.md).

All custom report layouts that exist for report layouts in a company are listed on the **Custom Report Layouts** page. On the **Report Layout Selection** page, you can see which custom layouts are available for each report in the **Custom Layouts** FactBox.

1. On the **Report Layout Selection** page, select the report with **Layout Type** set to **Custom Layout**, then choose **Select Layout**.
1. On the **Custom Report Layouts** page, select the row for the custom layout that you want to use, and then choose the **OK** button.

The name of the selected custom layout is now shown in the **Layout Description** field and will be used the next time the report or document is previewed, printed, or sent.

You can now go to your customer and vendor cards to specify which of the layouts to use for different documents that you create for the customer or vendor in question, such as order confirmations or payment reminders. Learn more in [Define document layouts for customers and vendors](ui-define-customer-vendor-document-layouts.md).

## Related information
[Managing Report Layouts](ui-manage-report-layouts.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
