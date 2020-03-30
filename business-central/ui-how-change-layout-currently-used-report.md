---
title: Change the Way a Report Looks by Selecting a Different Layout | Microsoft Docs
description: You can use different layouts for a report, and switch between layouts to change how a report looks.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.date: 04/01/2020
ms.author: sgroespe

---
# Change the Current Report Layout
A report can be set up with more than one report layout, which you can then switch among as needed.

Depending on the layouts that are available for a report, you can choose to use a built-in RDLC report layout, a built-in Word report layout, or a custom layout. For more information about RDLC and Word report layouts, built-in and custom layouts, and more, see [Manage Report Layouts](ui-manage-report-layouts.md).

When custom report layouts are defined, you can select them from customer and vendor cards to specify that the selected layouts will be used for documents that you crate for the customer or vendor in question. For more information, see [Define Document Layouts for Customers and Vendors](ui-define-customer-vendor-document-layouts.md).

> [!TIP]  
> Document reports (not lists) that use a Word report layout are typically faster than those that use an RDLC report layout. So if you have the option to choose between a Word or RDLC report layout for a document report, use the Word report layout for the best performance.

## To change which report layout to use for a report or document
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layout Selection**, and then choose the related link.  
   The **Report Layout Selection** page lists all the reports that are available for the company that is specified in the **Company** field at the top of the page. The **Selected Layout** field specifies the layout that is currently used on the report.
2. Set the **Company** field at the top of the page to the company that includes the report.
3. To change the layout that is used by a report, on the row for the report, set the **Selected Layout** field to one of the following options:
   * **RDLC (built-in)**, uses the built-in RDLC report layout on the report.
   * **Word (built-in)**, uses the built-in Word report layout on the report.
   * **Custom**, uses a custom layout on the report.  

> [!NOTE]
> If you choose a report layout of type **RDLC (built-in)** or **Word (built-in)** and you get an error message that the report does not have a layout of the specified type, then you must choose another layout option or create a custom report layout of the type that you want to use. See the next procedure.

If you selected a built-in RDLC or Word report layout, then no further action is required, and the layout will be used the next time the report is run.

## To change the custom layout to use for a report layout
You may also want to change the currently used custom layout. For more information, see [Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md).

All custom report layouts that exist for report layouts in a company are listed on the **Custom Report Layouts** page. On the **Report Layout Selection** page, you can see which custom layouts are available for each report in the **Custom Layouts** FactBox.

1. On the **Report Layout Selection** page, on the line for the report layout that you want to change, choose the lookup button in the **Custom Layout Description** field.
2. On the **Custom Report Layouts** page, select the row for the custom layout that you want to use, and then choose the **OK** button.

The name of the selected custom layout is now shown in the **Custom Layout Description** field and will be used the next time the report or document is previewed, printed, or sent.

You can now go to your customer and vendor cards to specify which of the layouts to use for different documents that you crate for the customer or vendor in question, such as order confirmations or payment reminders. For more information, see [Define Document Layouts for Customers and Vendors](ui-define-customer-vendor-document-layouts.md).

## See Related Training at [Microsoft Learn](/learn/modules/change-documents-dynamics-365-business-central/index)

## See Also
[Managing Report Layouts](ui-manage-report-layouts.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
