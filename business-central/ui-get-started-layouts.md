---
title: Get Started Creating Layouts
description: Learn how to create layouts to personalize the appearance of a report when viewed, printed, or saved.
author: jswymer
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 9650, 9652
ms.date: 04/01/2021
ms.author: jswymer

---
# Get Started Creating Report Layouts

Business Central comes with many built-in layouts that you can use on your reports. Other layouts may have been added as part of other extensions. But it's also possible to create your own reports either from scratch or based an existing layout.

## Overview

When working with report layouts, it helps to think of the layout as a file that's imported and assigned to a report. Regardless of the layout type, how you manage layouts in Business Central is basically the same. For the most part, you'll work from the **Report Layouts** page. The main difference is how you design the layout using the application software that it's built on, like Word, Excel, or SQL Server Report Builder.

With this concept in mind. there are basically three or fours tasks involved in setting up a layout on a report:

1. Decide on the layout type.
2. Export a copy of an existing layout of the same type to use as a starting point.
3. Make changes to the layout file in the appropriate application.
4. Add the new layout file to the report.

## Get started

However, depending on what your situations is, the actual tasks will vary. Use the following table for specific guidelines to suit your situation.

|What do you want to do?|See...|
|-----------------------|------|
|Figure out what's the best layout type to use for my situation|[Decide what type of layout you want](#decide)|
|Create a new layout for a report based on an existing layout, and keep the existing layout as it is.|[Create a new layout](#create)|
|Make changes to an existing layout used on a report|[Modify a layout](#modify)|
|I have an new version of a layout file for a report. I want to replace the existing layout file.|[Replace a layout](#modify)|
|Switch the current layout used by a report to another layout|[Setting the Layout Used by a Report](ui-set-report-layout.md)|

## <a name="decide"></a>Decide what type of layout you want

The first thing to do is to decide which [layout type]() you want, like, Word, Excel, or RDLC [layout type](). The layout typ  will depend on how you want the generated report to look and your knowledge of application for creating the layouts, like Word, Excel, and SQL Server Report Builder.

* The general design concepts for Word and RDLC layouts are similar. However each type has certain design features that affect how the generated report appears in [!INCLUDE[prod_short](includes/prod_short.md)]. This means that the same report might look different when using the Word report layout compared to the RDLC report layout.

* The process for setting up Word, Excel, and RDLC report layouts on reports is the same. The main difference is in the way you modify the layouts. Word and especially Excel layouts are typically easier to create and modify than RDLC report layouts because you use Word and Excel. RDLC report layouts are modified by using SQL Server Report builder, which targets more advanced users.

* Not all reports and document have a dataset that is optimized for use with an Excel layout. For example, aggregations and complex calculations work best with RDLC or Word layouts. The same is true for documents.

For information about how to switch the layout currently used on a report, see [Set the Layout Used by a Report](ui-set-report-layout.md).

## <a name="create"></a>Create a new layout from an existing layout

There are two ways to create a new layout from an existing. The easiest way is by saving the existing layout to a copy. The other way is to export the existing layout.

> [!NOTE]
> You can't copy a layout that comes from an extension. You can only copy user-defined extensions. To learn about the difference between extension layouts and user-defined layouts, see [Layout source](ui-manage-report-layouts.md#layout-sources).

## [Copying](#tab/copy)

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layouts**, and then choose the related link.

   The **Report Layouts** page appears and lists all the layouts currently available for all reports.
2. Select the layout that you want a copy of for your new layout, then choose the **Edit Info** action.
3. Change the **Layout Name**.
4. Turn the **Save Changes to Copy** switch to **On**, then select **OK**

   The new layout shoes in the **Report Layouts** page.
5. If you want to make changes to the new layout, see [Exporting](#exporting).

### [Exporting](#tab/export)

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layouts**, and then choose the related link.

   The **Report Layouts** page appears and lists all the layouts currently available for all reports.
2. Select the layout that you want a copy of for your new layout, then choose the **Export Layout** action.

   The layout file is downloaded to your device. 

    > [!TIP]
    > To help you find the layout, use the **Search** box, **Filter** pane, and columns sorting.

3. Open the layout file in the appropriate application, like Word for a .docx file, Excel for a .xlsx file, or SQL Report Builder for an .rdl file.

   Make changes to the file and save it.

4. Back on the **Report Layouts**, select the **New Layout** action.
5. Fill in the following fields:

   |Field|Description|Mandatory|
   |-----|-----------|---------|
   |Report ID|Set to the ID assigned to the report|yes|
   |Layout Name| Type a brief description name for the layout to help you easily identify it.|yes|
   |Description| Type more details information the layout. |no|
   |Format Options|Set this to match the type of the layout, like Word, Excel, or RDLC.|yes|

6. Select **OK** > **Choose** to open file explorer on your device.
7. Find and select the Excel file, then select **Open**.

   The selected file is uploaded to the layout, and you return to the **Report Layouts** page.

If you want to see how the report looks with the new layout, select the layout in the list, then select **Run Report**.

---

## <a name="modify"></a>Modify an existing layout

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layouts**, and then choose the related link.

   The **Report Layouts** page appears and lists all the layouts currently available for all reports.
2. Select the layout that you want to modify, then choose the **Export Layout** action.

   The layout file is downloaded to your device. 

   > [!TIP]
   > To help you find the layout, use the **Search** box, **Filter** apne, and columns sorting.

3. Open the layout file in the appropriate application, like Word for a .docx file, Excel for a .xlsx file, or SQL Report Builder for an .rdl file.

   Make changes to the file and save it.

4. Back on the **Report Layouts**, select the existing layout, then select the **Replace Layout** action.
5. Select **OK** > **Choose** to open file explorer on your device.
6. Find and select the Excel file, then select **Open**.

   The selected file is uploaded to the layout, and you return to the **Report Layouts** page.

## <a name="replace"></a>Replace an existing layout with a new one

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layouts**, and then choose the related link.

   The **Report Layouts** page appears and lists all the layouts currently available for all reports.
2. Select the existing layout, then select the **Replace Layout** action.
5. Select **OK** > **Choose** to open file explorer on your device.
6. Find and select the Excel file, then select **Open**.

   The selected file is uploaded to the layout, and you return to the **Report Layouts** page.


## See Related Training at [Microsoft Learn](/learn/modules/change-documents-dynamics-365-business-central/index)

## See Also

[Managing Report Layouts](ui-manage-report-layouts.md)
[Working with Word Layouts](ui-how-add-fields-word-report-layout.md) 
[Working with Excel Layouts](ui-excel-report-layouts.md)  
[Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
[Prepare Financial Reporting with Account Schedules and Account Categories](bi-how-work-account-schedule.md) 
[Business Intelligence](bi.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]