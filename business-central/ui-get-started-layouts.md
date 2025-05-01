---
title: Get started creating report layouts
description: Learn how to create and customize report layouts in Dynamics 365 Business Central. Personalize your reports for viewing, printing, or saving.
author: jswymer
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: customized report, document layout, logo, personalize
ms.search.form: 9650, 9652, 9660_Primary
ms.date: 03/13/2025
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
| Mark a layout as obsolete | [Mark a layout as obsolete](#mark-a-layout-as-obsolete) |
| Validate a layout. | [Validate a layout](#validate) |
| View information about a layout. | [Get information about a layout](#get-information-about-a-layout) |
| Delete a user-defined layout. | [Delete a layout](#delete) |

## <a name="decide"></a>Decide what type of layout you want

The first task when you create a layout is to decide which [layout type](ui-manage-report-layouts.md#layout-types) you want. You can choose among the **Word**, **Excel**, and **RDLC** layout types. Your choice depends on how you want the generated report to look. It also depends on your knowledge of the software that is used to create the layout, such as Word, Excel, and SQL Server Report Builder.

* **Excel** layouts are generally the easiest to create and modify because summarizing data, adding graphics, and styling are common Excel features. However, not all reports have datasets optimized for Excel layouts. Aggregations and complex calculations work best with **RDLC** or **Word** layouts. The same applies to documents.
* If you're making only style changes, such as changes to the font type, size, and colors, a **Word** layout is a good choice.
* The capabilities for adding and rearranging data fields are more advanced in **Word** and **RDLC** layouts than in **Excel** layouts.
* **Word** and **RDLC** layouts are good choices for printable reports.
* The design concepts for **Word** and **RDLC** layouts are similar, but each has specific features that affect the report's appearance in [!INCLUDE[prod_short](includes/prod_short.md)]. The same report might look different depending on whether a **Word** or **RDLC** layout is used.

## <a name="create"></a>Create a new layout

There are different methods for creating a new layout. The easiest methods involve using a copy of an existing layout. For these methods, you can either save the existing layout directly as a copy, or export it and then import it into a new layout. Another, more advanced method is to create a layout from scratch by using a blank layout.

### [Copy a layout](#tab/copy)

Copying an existing layout lets you quickly create a new, identical layout that you can customize.

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]

   The **Report Layouts** page lists all layouts for all reports.
1. Select the layout that you want to copy for the new layout, and then select the **Edit Info** action.

    If you select an extension layout, you're asked whether you want to edit a copy of it. Select **Yes**.

    > [!TIP]
    > To find the layout that you want, use the search field, the filter pane, and column sorting.

1. In the **Layout Name** field, enter a new name.
1. Turn on the **Save Changes to Copy** toggle, if it isn't already on.
1. Select **OK**.

    The new layout appears on the **Report Layouts** page.

If needed, you can change the settings in your new layout. To learn more, go to [Change settings in a new layout](#modify).

### [Export a layout copy and import it as a new layout](#tab/export)

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select the layout that you want to copy for the new layout, and then select the **Export Layout** action.

    The layout file is downloaded to your device.

    > [!TIP]
    > To find the layout that you want, use the search field, the filter pane, and column sorting.

1. Open the layout file in the appropriate application, such as Word (for a .docx file) or Excel (for an .xlsx file).

    Learn more in the following articles:

    * [Work with Word Layouts](ui-how-add-fields-word-report-layout.md)
    * [Working with Microsoft Excel layouts](ui-excel-report-layouts.md)
    * [Working with RDLC Layouts](ui-rdlc-report-layouts.md)

1. Make the required changes to the file, and then save it.
1. On the **Report Layouts** page, select **New**.
1. In the **Add New Layout for a Report** dialog box, fill in the fields described in the following table.

    | Field | Description | Mandatory |
    |---|---|---|
    | Report ID | Enter the ID that is assigned to the report. | Yes |
    | Layout Name | Enter a brief, descriptive name for the layout to help you easily identify it. | Yes |
    | Description | Enter more detailed information about the layout. | No |
    | Format Options | Set this field to match the type of the layout (for example, **Word**, **Excel**, or **RDLC**). | Yes |

1. Select **OK**.
1. Follow one of these steps to upload the layout file for the report:

    [!INCLUDE[file-upload](includes/file-upload.md)]

    The selected file is uploaded to the layout, and you're returned to the **Report Layouts** page.

To view how the report looks with the new layout, select the layout in the list, and then select **Run Report**.

### [Create from blank](#tab/blank)

When you create a new layout from a blank layout, you must design it completely. The layout file provides all the report fields that you can add and arrange as you require.

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select any layout that is for the same report that you want use the new layout for.
1. Select **New**.
1. In the **Add New Layout for a Report** dialog box, set the following fields.

    | Field | Description | Mandatory |
    |---|---|---|
    | Report ID | Enter the ID that is assigned to the report. | Yes |
    | Layout Name | Enter a brief descriptive name for the layout to help you easily identify it. | Yes |
    | Description | Enter more detailed information about the layout. | No |
    | Format Options | Set this field to match the type of the layout (for example, **Word**, **Excel**, or **RDLC**). | Yes |

1. Turn on the **Create a blank layout from the report object** option.
1. Select **OK**.

    The new layout appears in the list. The layout is blank, but all the report fields and captions are available so that you can start to add them to the layout.

1. You can now start to [design the layout](#modify).

---

## <a name="modify"></a>Modify a layout

Follow these steps to modify an existing user-defined layout.

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select the layout that you want to modify, and then select the **Export Layout** action.

    The layout file downloads to your device.

    > [!TIP]
    > To find the layout that you want, use the search field, the filter pane, and column sorting.

1. Open the layout file in the appropriate application, such as Word (for a .docx file) or Excel (for an .xlsx file).

    Learn more in the following articles:

    * [Work with Word Layouts](ui-how-add-fields-word-report-layout.md)
    * [Working with Microsoft Excel layouts](ui-excel-report-layouts.md)
    * [Working with RDLC Layouts](ui-rdlc-report-layouts.md)

1. Make the required changes to the file, and then save it.
1. On the **Report Layouts** page, select the existing layout, and then select the **Replace Layout** action.
1. Select **OK** and then **Choose** to open File Explorer on your device.
1. Find and select the Excel file, and then select **Open**.

    The selected file is uploaded to the layout, and you're returned to the **Report Layouts** page.

1. To view how the report looks with the new layout, select the layout in the list, and then select **Run Report**.

## <a name="replace"></a>Replace a layout

Follow these steps to replace the existing user-defined layout file with a new file.

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select the existing layout, and then select the **Replace Layout** action.
1. Select **OK** and then **Choose** to open File Explorer on your device.
1. Find and select the Excel file, and then select **Open**.

    The selected file is uploaded to the layout, and you're returned to the **Report Layouts** page.

1. To view how the report looks with the new layout, select the layout in the list, and then select **Run Report**.

## <a name="rename"></a>Rename a layout

Follow these steps if you want to change the name and description of a user-defined layout.

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select the layout that you want to rename, and then select the **Edit Info** action.

    > [!TIP]
    > To find the layout that you want, use the search field, the filter pane, and column sorting.

1. In the **Layout Name**, enter a new name.
1. Select **OK**.

## <a name="validate"></a>Validate a layout

<!--[!INCLUDE[introduced_in_2025rw1](includes/introduced_in_2025rw1.md)]-->

Validate a user-defined layout to check for problems and view the results. Follow these steps to validate a layout.

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select the layout you want to validate, and then select the **Validate** action.

    > [!TIP]
    > To find a layout, use the Search field, Filter pane, or column sorting.

1. A dialog opens to show the validation results.

## Get information about a layout

<!--[!INCLUDE[introduced_in_2025rw1](includes/introduced_in_2025rw1.md)]-->

View information about the layout, such as its ID, the report it's based on, and when it was created and last modified. This information is useful for troubleshooting. Follow these steps to view layout information.

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select the layout you want to gather information for, and then select the **Show layout info** action.

    > [!TIP]
    > To find a layout, use the search field, the filter pane, or column sorting.

1. In the **Layout information** dialog, select the text and copy it to share with others.

## <a name="delete"></a>Delete a layout

To delete a user-defined layout, follow these steps.

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select the layout that you want to delete, and then select the **Delete** action.

    > [!TIP]
    > To find a layout, use the Search field, the Filter pane, or column sorting.

1. In the **Delete layout** dialog, select **Yes**.

## Mark a layout as obsolete

A layout can become obsolete for various reasons. For example, the data model might change, making the layout outdated, or a more efficient layout might be introduced, making the current layout redundant. Marking a layout as obsolete signals to others that it will likely be removed in a later release, so they should use an alternative layout.

To identify which layouts are obsolete, refer to the **Obsolete** column on the **Report Layouts page**. You can mark a user-defined layout as obsolete if needed. 

1. [!INCLUDE[open-report-layouts-page](includes/open-report-layouts-page.md)]
2. Select the layout that you want to change, and then select the **Edit Info** action.
3. Turn on the **Mark layout as obsolete** toggle.
4. Select **OK**.

> [!NOTE]
> Extension layouts are marked as obsolete in AL code using the [ObsoleteState property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-obsoletestate-property) and can't be changed using the **Edit Info** action.

## Related information

[Report and document layouts overview](ui-manage-report-layouts.md)  
[Work with Word Layouts](ui-how-add-fields-word-report-layout.md)  
[Working with Microsoft Excel layouts](ui-excel-report-layouts.md)  
[Run and print reports in Business Central](ui-work-report.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
