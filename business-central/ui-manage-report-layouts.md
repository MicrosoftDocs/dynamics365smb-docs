---
title: Custom and Built-In Layouts for Reports and Documents
description: Use report layouts to customize documents, for example, to personalize the font, logo, or page settings of PDF files you send to customers.
author: jswymer
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 9652, 9650
ms.date: 04/01/2021
ms.author: jswymer

---
# Managing Report and Document Layouts

A report layout controls content and format of the report, including which data fields of a report dataset appear on the report and how they're arranged, text style, images, and more. From [!INCLUDE[prod_short](includes/prod_short.md)], you can change which layout is used on a report, create new layout, or modify the existing layouts.

> [!NOTE]  
> In [!INCLUDE[prod_short](includes/prod_short.md)], the term "report" also covers externally-facing documents, such as sales invoices and order confirmations that you send to customers as PDF files.

In particular, a report layout sets up the following things:

* The label and data fields to include from the dataset of the [!INCLUDE[prod_short](includes/prod_short.md)] report.
* The text format, such as font type, size, and color.
* The company logo and its position.
* General page settings, such as margins and background images.

A report can be set up with multiple report layouts, which you can switch among as required. <!--You can use one of the built-in report layouts or you can create custom report layouts and assign them to your reports as needed. For more information, see [Create a Custom Report or Document Layout](ui-how-create-custom-report-layout.md).-->

There are two important aspects of report layouts that will influence how you work with layout: the layout type and the layout source. The layout type indicates the kind of file that the layout is based on. The layout source indicates the original of the layout.

## Layout types

There are four types of layouts that you can use on reports: Word, RDLC, Excel, and external.

### Word type

Word layouts are based on Word documents (.docx file type). Word layouts enable you to design report layouts by using Microsoft Word. A Word layout determines the report's content - controlling how that content elements are arranged and how they look. A Word layout document will typically use tables to arrange content, where the cells can contain data fields, text, or pictures.

 ![Example of a word report layout document for NAV.](media/nav_wordreportlayout_edit_in_word_example.png "NAV_WordReportLayout_Edit_In_Word_Example")  

### Excel type

Excel layouts are based on Microsoft Excel workbooks (.xlsx files). They let you create reports by using familiar Excel features for summarizing, analyzing, and presenting data. Use tools like formulas, PivotTables, PivotCharts, and more.

![Shows the an example of an Excel layout.](media/excel-layout-2.png)

### RDLC type

RDLC layouts are based on client report definition layouts (.rdlc or .rdl file types). These layouts are created and modified by using SQL Server Report Builder. The design concept for RDLC layouts is similar to Word layouts, where the layout defines the general format of the report and determines the fields from the dataset to include. Designing RDLC layouts is more advanced than Word layouts. For more information, see [Designing RDLC Report Layouts](/dynamics-nav/Designing-RDLC-Report-Layouts).

### External type

An external layout type is custom layout type.

## Layout source: extension or user-defined

Layouts can originate from two sources. They can be part of an extension that's been installed on the environment. These layouts are typically standard layouts provided by Microsoft as part of the base application. Or, they could be layouts that are included in extensions from other software providers. You can recognize these extension-based layouts on the **Report Layouts** because the extension name and publisher is listed in the **Extension** column.

The other source of layouts are users themselves. From inside Business Central, users can add new layouts in various ways, like downloading an existing layout, making modifications, then uploading it as a new layout. You On the **Report Layouts**,  user-defined layout will have an empty **Extension** column.

The important thing to remember is that you can't modify an extension-based layout from inside Business Central. In other words, you aren't allowed to change its name or type, or upload and replace it with another version. If you try, you'll get an error message.  

### Built-in and custom report layouts

[!INCLUDE[prod_short](includes/prod_short.md)] includes several built-in layouts. Built-in layouts are predefined layouts that are designed for specific reports. [!INCLUDE[prod_short](includes/prod_short.md)] reports will have a built-in layout as either an RDLC report layout, Word report layout, or in some cases both. You can’t modify a built-in report layout from [!INCLUDE[prod_short](includes/prod_short.md)] but you use them as a starting point for building your own custom report layouts.

Custom layouts are report layouts that you design to change the appearance of a report. You typically create a custom layout based on a built-in layout, but you can create them from scratch or from a copy of an existing custom layout. Custom layouts enable you to have multiple layouts for the same report, which you switch among as needed. For example, you can have different layouts for each [!INCLUDE[prod_short](includes/prod_short.md)] company, or you can have different layouts for the same company for specific occasions or events, like a special campaign or holiday season.

## Deciding on the layout type

Deciding on whether to use a Word, Excel, or RDLC layout type will depend on how you want the generated report to look and your knowledge of tools for creating the layouts, like Word, Excel, and SQL Server Report Builder.

The general design concepts for Word and RDLC layouts are very similar. However each type has certain design features that affect how the generated report appears in [!INCLUDE[prod_short](includes/prod_short.md)]. This means that the same report might look different when using the Word report layout compared to the RDLC report layout.

The process for setting up Word report layouts and RDLC report layouts on reports is the same. The main difference is in the way you modify the layouts. Word report layouts are typically easier to create and modify than RDLC report layouts because you can use Word. RDLC report layouts are modified by using SQL Server Report builder which targets more advanced users.

Not all reports and document have a dataset that is optimized to to use an Excel layout. For example, aggregations and complex calculations work best for RDLC or Word layout. The same is for documents.

For information on how to change which layout to use, see [Change the Current Report Layout](ui-how-change-layout-currently-used-report.md).

## See Related Training at [Microsoft Learn](/learn/modules/change-documents-dynamics-365-business-central/index)

## See Also

[Update Custom Report Layouts](ui-update-report-layouts.md)  
[Create and Modify Custom Report Layouts](ui-how-create-custom-report-layout.md)  
[Import and Export a Custom Report or Document Layout](ui-how-import-and-export-report-layout.md)  
[Define Special Document Layouts for Customers and Vendors](ui-define-customer-vendor-document-layouts.md)  
[Send Documents by Email](ui-how-send-documents-email.md)  
[Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]