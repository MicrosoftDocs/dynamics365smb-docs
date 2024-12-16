---
title: Get started creating report layouts
description: Learn how to create layouts to personalize the appearance of a report when it's viewed, printed, or saved.
author: jswymer
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 9650, 9652, 9660_Primary
ms.date: 12/16/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Get started creating report layouts

[!INCLUDE [prod_short](includes/prod_short.md)] includes many built-in layouts that you can use on your reports. Other layouts might be added as part of extensions. In addition, you can create your own report layouts, either from scratch or based on an existing layout.

> [!NOTE]
> You can also use report layouts to add content to email messages. Report layouts can help save time and ensure consistency by reusing the same content when you communicate with your customers. Only custom report layouts of the **Word** type can be used with email. You can't use layouts of the **RDLC** with email. Learn more in [Set up reusable email texts and layouts](admin-how-setup-email.md#set-up-reusable-email-texts-and-layouts).

## Overview of report layouts

It can be helpful to think of a report layout as a file that is imported and assigned to a report. You manage all layouts in [!INCLUDE [prod_short](includes/prod_short.md)] in basically the same way, regardless of the layout type. Usually, you work from the **Report Layouts** page. The layouts differ mainly in the way that you design them. Each layout is designed by using the software that the layout is built on, such Word, Excel, or SQL Server Report Builder.

The process of setting up a layout for a report involves three or four basic tasks.

1. Choose the layout type.
2. Export a copy of an existing layout so that you can use it as a starting point.
3. Make changes to the layout file in the appropriate application.
4. Add the new layout file to the report.

> [!IMPORTANT]
> You can modify or replace only user-defined layouts. You can't modify or replace *extension layouts*, which are layouts that originate from an extension. On the **Report Layouts** page, you can tell whether a layout is a user-defined layout or an extension layout by looking in the **Extension** column. For an extension layout, the **Extension** column shows information about the source extension. For a user-defined layout, the **Extension** column is blank.
>
> Learn more about the difference between extension layouts and user-defined layouts in [Layout sources](ui-manage-report-layouts.md#layout-sources).

## Get started

Depending on your situation, the actual tasks vary. Use the following table to get started.

| What do you want to do? | Learn more |
|---|---|
| Figure out the best layout type to use for my situation. | [Decide what type of layout you want](#decide) |
| Create a new layout for a report, either from scratch or based on a copy of an existing layout. | [Create a new layout](#create) |
| Make changes to the layout that a report uses. | [Modify a layout](#modify) |
| Replace the current layout file that a report uses with a new version of the layout file. | [Replace a layout](#replace) |
| Change the current layout that a report uses to another layout. | [Setting the Layout Used by a Report](ui-set-report-layout.md) |
| Change the name and description of a layout. | [Rename a layout](#rename) |

## <a name="decide"></a>Decide what type of layout you want

The first task when you create a layout is to decide which [layout type](ui-manage-report-layouts.md#layout-types) you want. You can choose among the **Word**, **Excel**, and **RDLC** layout types. Your choice depends on how you want the generated report to look. It also depends on your knowledge of the software that is used to create the layout, such as Word, Excel, and SQL Server Report Builder.

* **Excel** layouts are generally the easiest to create and modify because the features for summarizing data, adding graphics, and styling are common Excel features.
* Not all reports have a dataset that is optimized for use with an Excel layout. For example, aggregations and complex calculations work best with **RDLC** or **Word** layouts. The same is true for documents.
* If you're making only style changes, such as changes to the font type, size, and colors, a **Word** layout is a good choice.
* The capabilities for adding and rearranging data fields are more advanced in **Word** and **RDLC** layouts than in **Excel** layouts.
* **Word** and **RDLC** layouts are a good choice for reports that will eventually be printed.
* The general design concepts for **Word** and **RDLC** layouts are similar. However, each type has specific design features that affect how the generated report looks in [!INCLUDE[prod_short](includes/prod_short.md)]. Therefore, the same report might look different, depending on whether a **Word** layout or an **RDLC** layout is used.

## <a name="create"></a>Create a new layout

There are different methods for creating a new layout. The easiest methods involve using a copy of an existing layout. For these methods, you can either save the existing layout directly as a copy, or export it and then import it into a new layout. Another, more advanced method is to create a layout from scratch by using a blank layout.

### [Save existing as copy](#tab/copy)

By copying an existing layout, you can quickly create a new layout that is identical to it. You can then make modifications by exporting the new layout.

[!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. Select the layout that you want to copy for the new layout, and then select the **Edit Info** action.

    If you select an extension layout, you're asked whether you want to edit a copy of it. Select **Yes**.

    > [!TIP]
    > To find the layout that you want, use the search field, the filter pane, and column sorting.

3. In the **Layout Name** field, enter a new name.
4. Set the **Save Changes to Copy** option to **On**.
5. Select **OK**.

    The new layout appears on the **Report Layouts** page.

6. [Make any changes that you want to make to the new layout](#modify).

### [Export existing as copy and import as new](#tab/export)

[!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. Select the layout that you want to copy for the new layout, and then select the **Export Layout** action.

    The layout file is downloaded to your device.

    > [!TIP]
    > To find the layout that you want, use the search field, the filter pane, and column sorting.

3. Open the layout file in the appropriate application, such as Word (for a .docx file) or Excel (for an .xlsx file).

    Learn more:

    * [Work with Word Layouts](ui-how-add-fields-word-report-layout.md)
    * [Working with Microsoft Excel layouts](ui-excel-report-layouts.md)
    * [Working with RDLC Layouts](ui-rdlc-report-layouts.md)

4. Make the required changes to the file, and then save it.
5. On the **Report Layouts** page, select **New**.
6. In the **Add New Layout for a Report** dialog box, set the following fields.

    | Field | Description | Mandatory |
    |---|---|---|
    | Report ID | Enter the ID that is assigned to the report. | Yes |
    | Layout Name | Enter a brief descriptive name for the layout to help you easily identify it. | Yes |
    | Description | Enter more detailed information about the layout. | No |
    | Format Options | Set this field to match the type of the layout (for example, **Word**, **Excel**, or **RDLC**). | Yes |

7. Select **OK**.
8. Follow one of these steps to upload the layout file for the report:

    [!INCLUDE[file-upload](includes/file-upload.md)]

    The selected file is uploaded to the layout, and you're returned to the **Report Layouts** page.

To view how the report looks with the new layout, select the layout in the list, and then select **Run Report**.

### [Create from blank](#tab/blank)

When you create a new layout from a blank layout, you must design it completely. The layout file provides all the report fields that you can add and arrange as you require.

[!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. Select any layout that is for the same report that you want use the new layout for.
3. Select **New**.
4. In the **Add New Layout for a Report** dialog box, set the following fields.

    | Field | Description | Mandatory |
    |---|---|---|
    | Report ID | Enter the ID that is assigned to the report. | Yes |
    | Layout Name | Enter a brief descriptive name for the layout to help you easily identify it. | Yes |
    | Description | Enter more detailed information about the layout. | No |
    | Format Options | Set this field to match the type of the layout (for example, **Word**, **Excel**, or **RDLC**). | Yes |

5. Turn on the **Create a blank layout from the report object** option.
6. Select **OK**.

    The new layout appears in the list. The layout is blank, but all the report fields and captions are available so that you can start to add them to the layout.

7. You can now start to [design the layout](#modify).

---

## <a name="modify"></a>Modify a layout

Follow these steps to modify an existing user-defined layout.

[!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. Select the layout that you want to modify, and then select the **Export Layout** action.

    The layout file is downloaded to your device.

    > [!TIP]
    > To find the layout that you want, use the search field, the filter pane, and column sorting.

3. Open the layout file in the appropriate application, such as Word (for a .docx file) or Excel (for an .xlsx file).

    Learn more:

    * [Work with Word Layouts](ui-how-add-fields-word-report-layout.md)
    * [Working with Microsoft Excel layouts](ui-excel-report-layouts.md)
    * [Working with RDLC Layouts](ui-rdlc-report-layouts.md)

4. Make the required changes to the file, and then save it.
5. On the **Report Layouts** page, select the existing layout, and then select the **Replace Layout** action.
6. Select **OK** and then **Choose** to open File Explorer on your device.
7. Find and select the Excel file, and then select **Open**.

    The selected file is uploaded to the layout, and you're returned to the **Report Layouts** page.

8. To view how the report looks with the new layout, select the layout in the list, and then select **Run Report**.

## <a name="replace"></a>Replace a layout

Follow these steps to replace the existing user-defined layout file with a new file.

[!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. Select the existing layout, and then select the **Replace Layout** action.
3. Select **OK** and then **Choose** to open File Explorer on your device.
4. Find and select the Excel file, and then select **Open**.

    The selected file is uploaded to the layout, and you're returned to the **Report Layouts** page.

5. To view how the report looks with the new layout, select the layout in the list, and then select **Run Report**.

## <a name="rename"></a>Rename a layout

Follow these steps if you want to change the name and description of a user-defined layout.

[!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. Select the layout that you want to rename, and then select the **Edit Info** action.

    > [!TIP]
    > To find the layout that you want, use the search field, the filter pane, and column sorting.

3. In the **Layout Name**, enter a new name.
4. Select **OK**.

## Related information

[Report and document layouts overview](ui-manage-report-layouts.md)  
[Work with Word Layouts](ui-how-add-fields-word-report-layout.md)  
[Working with Microsoft Excel layouts](ui-excel-report-layouts.md)  
[Run and print reports in Business Central](ui-work-report.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
