---
title: Create and Modify Custom Layouts for Reports and Documents
description: Learn how to create customized layouts to personalize the appearance of a report when viewed, printed, or saved.
author: SorenGP

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 9650, 9652
ms.date: 04/01/2021
ms.author: edupont

---
# Create and Modify Custom Report Layouts

By default, a report will have a built-in report layout, which can be either an RDLC report layout or Word report layout, or both. You can't modify built-in layouts. But you can create your own custom layouts that enable you to change the appearance of report when it's viewed, printed, or saved. You can create multiple custom report layouts for the same report, and then switch the layout that is used by a report as needed.

> [!NOTE]  
> In [!INCLUDE[prod_short](includes/prod_short.md)], the term "report" also covers externally-facing documents, such as sales invoices and order confirmations that you send to customers as PDF files.

To create a custom layout, you either make a copy of an existing custom layout or add a new custom layout, which is commonly based on a built-in layout. When you add a new custom layout, you can choose to add an RDLC report layout type, Word report layout type, or both. The new custom layout will automatically be based on the built-in layout for the report if one is available. If there's no built-in layout for the type, a new blank layout is a created. You'll have to modify and design this blank layout from scratch. For more information about RDLC and Word report layouts, built-in and custom layouts, and more, see [Manage Report Layouts](ui-manage-report-layouts.md).  

> [!TIP]
> Use account schedules to get insight into the financial data stored in your chart of accounts. For more information, see [Prepare Financial Reporting with Account Schedules and Account Categories](bi-how-work-account-schedule.md).

When custom report layouts are defined, you can select them from customer and vendor cards to specify that the selected layouts will be used for documents that you create for the customer or vendor in question. For more information, see [Define Document Layouts for Customers and Vendors](ui-define-customer-vendor-document-layouts.md).

## To add layout

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layout**, and then choose the related link.

    The **Report Layouts** page lists all the reports layouts that are available. 
2. Choose **New Layout**.
3. Set the **Report ID** field to the ID of the report you want to create the layout for. 

   > [!TIP]
   > If you select an existing layout for the report from the **Report Layouts** page, the **Report ID** field will be filled in for you.

4. In the **Layout Name** field, type a name for the layout. This name is used to identify the report layout, so make sure it is descriptive enough.

5. Set the **Format Options** field to the layout type.
6. On the **Choose layout file** page, select **Choose**.
7. Find the layout file, select it, then choose **Open**

The layout has been addedTo try it out, select You can now modify the custom layout as needed.

> [!TIP]
> You can export the report results to an Excel file for viewing the full dataset, including all columns, but without the layout. The Excel file can help you validate that the report returns the expected data or diagnose problems. For more information, see [Analyzing Report Data with Excel](report-analyze-excel.md).

## <a name="ModifyCustomLayout"></a>Modifying a custom layout

To modify a report layout, you must first export the report layout as a file to a location on your computer or network. Then, open the exported document and make the changes. When you're finished making the changes, you import the report layout.

### To modify a custom layout

1.  You export a custom layout from the **Custom Report Layouts** page. If this page isn't already open, search for and open the **Report Layout Selection** page, select the report that has the layout that you want to modify, and then choose the **Custom Layouts** action.  
2.  On the **Custom Report Layouts** page, select the layout that you want to modify, choose the **Export Layout** action, and then choose **Save** or **Save As** to save the report layout document to a location on your computer or network.  

3.  Open the report layout document that you saved, and then make changes.

      If you're changing a Word layout, open the layout document in Word. For editing details, see the next section [Making Changes to the Report Layout](ui-how-create-custom-report-layout.md#MakeChangesToLayout).

      RDLC report layouts are more advanced than Word report layouts. For more information about modifying an RDLC report layout, see [Designing RDLC Report Layouts](/dynamics-nav/Designing-RDLC-Report-Layouts).

      Remember to save you changes when done.

4.  Return to the **Custom Report Layouts** page, select the report layout that you exported and modified, and then choose the **Import Layout** action.  

5. In the **Import** dialog box, select **Choose** to find and select the modified report layout document, and then choose **Open**.

> [!IMPORTANT]
> Remember to import the report layout document that you modified. Otherwise, the new report layout will not be available.

##  <a name="MakeChangesToLayout"></a> Create and Modify Custom Report Layouts

To make general formatting and layout changes, such as changing text font, adding and modifying a table, or removing a data field, just use the basic editing features of Word, like you do with any Word document.

If you're designing a Word report layout from scratch or adding new data fields, then start by adding a table that includes rows and columns that will eventually hold the data fields.

> [!TIP]  
> Show the table gridlines so that you see the boundaries of table cells. Remember to hide the gridlines when you're done editing. To show or hide table gridlines, select the table, and then under **Layout** on the **Table** tab, choose **View Gridlines**.

### Embedding Fonts in Word Layouts for Consistency

To ensure that reports always display and print with the intended fonts, wherever users open or print the reports, you can embed the fonts in the Word document. However, embedding fonts can significantly increase the size of the Word files. For more information about embedding fonts in Word, see [Embed fonts in Word, PowerPoint, or Excel](https://support.office.com/article/Embed-fonts-in-Word-PowerPoint-or-Excel-cb3982aa-ea76-4323-b008-86670f222dbc).

###  <a name="RemoveField"></a> Removing Label and Data Fields in Word Layouts

 Label and data fields of a report are contained in content controls in Word. The following figure illustrates a content control when it's selected in the Word document.  

 ![Content control for field in Word report layout.](media/nav_wordreportlayouts_contentcontrol.png "NAV_WordReportLayouts_ContentControl")  

 The name of the label or data field name displays in the content control. In the example, the field name is CompanyAddr1.  

### To remove a label or data field  

1. Right-click the field that you want to delete, and then choose **Remove Content Control**.  

     The content control is removed, but the field name remains as text.  

2. Delete the remaining text as needed.  

### Adding data fields

Adding data fields from a report dataset is a more advanced and requires some knowledge of the report dataset. For information about adding fields for data, labels, data, and images, see [Add Fields to a Word Report Layout](ui-how-add-fields-word-report-layout.md).  

## See Related Training at [Microsoft Learn](/learn/modules/change-documents-dynamics-365-business-central/index)

## See Also

[Managing Report Layouts](ui-manage-report-layouts.md)  
[Change the Current Report Layout](ui-how-change-layout-currently-used-report.md)  
[Import and Export a Custom Report or Document Layout](ui-how-import-and-export-report-layout.md)  
[Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
[Prepare Financial Reporting with Account Schedules and Account Categories](bi-how-work-account-schedule.md) 
[Business Intelligence](bi.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]