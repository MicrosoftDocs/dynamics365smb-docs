---
title: Design Word Layouts with the Business Central Add-in
description: Learn how to use the Business Central Word add-in to add report fields, create repeating tables, add layout comments, and hide empty content.
author: SusanneWindfeldPedersen
ms.author: solsen
ms.reviewer: jswymer
ms.topic: how-to
ms.search.keywords: Word add-in, report layout, insert table, data binding, conditional content
ms.search.form: 9660, 9666
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Design report layouts with the Business Central Word add-in

Use the Business Central add-in for Word to add report data to a Word layout. The add-in helps you add report fields, build data tables, and control when content appears—without editing the underlying XML in the **XML Mapping Pane**.

## Install the Word add-in

1. In Word, go to the **Home** tab, and then select **Get Add-ins**.
1. Search for *Dynamics 365 Business Central Word add-in*.
1. Select the add-in, and then select **Add**.

The **Business Central** tab appears on the ribbon.

## Get a Word layout that contains report metadata

The add-in reads metadata embedded in the Word file. Export an existing layout or create a blank layout in [!INCLUDE [prod_short](includes/prod_short.md)] before you start designing.

1. [!INCLUDE [open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select the Word layout that you want to change.
1. Select **Layout** > **Update and Export Layout**.
1. Open the downloaded `.docx` file in Word.

> [!IMPORTANT]
> Use **Update and Export Layout** to include the current report dataset and the metadata that the add-in requires. If you use a file without this metadata, the add-in can't list the report fields.

To start without an existing design, create a blank Word layout in [!INCLUDE [prod_short](includes/prod_short.md)] first. Learn more in [Create a new layout](ui-get-started-layouts.md#create).

## Add report fields and labels

The **Add Data** action opens a task pane that organizes the values available to the layout.

| Group | What it contains |
|---|---|
| **Data** | Data items and fields from the report dataset. |
| **Labels** | Captions, headings, and other translated text supplied by the report. |
| **Report Information** | Report metadata, such as the report ID, date, and time. |

To add a value:

1. On the **Business Central** tab, select **Add Data**.
1. Expand the group and data item that contains the value.
1. Place the cursor where you want the value in the document.
1. Select the field or label in the task pane, and then select **Add field**.

The add-in inserts a *content control*, a Word placeholder that's bound to the selected report value so the value fills in when the report runs. Move or format the control by using standard Word features. To show a different report value, delete the content control and add the correct field from the task pane.

## Build a repeating data table

Add a *repeater* when you want a table row to repeat for every record in a report data item. You can use **Insert table** or create the table and repeater manually.

### Create a table with Insert table

The **Insert table** action creates the table, repeater, and field controls from one dialog.

1. Place the cursor where you want the table.
1. On the **Business Central** tab, select **Insert table**.
1. In the **Create Data Table** dialog, select the **Data source**.
1. Add the fields that you want to appear as columns in the table. Each field you add becomes one column.
1. Arrange the columns in the order that you want.
1. Turn on **Include header row** if you want column headings. Turn on **Auto-select headline** to use each field's caption as its column heading.
1. To include a footer row in the table, select **Add Footer**.
1. Select **Create table**.

You can change the table's formatting after the add-in inserts it. Don't delete the field bindings or the repeating row control, because they connect the table to the report data.

### Create a table and repeater manually

Use this method to create and bind the table structure yourself.

1. In Word, insert a table with a header row and a second row for report data.
1. On the **Business Central** tab, select **Add Data**.
1. In the **Data** group, expand the data item that you want to repeat.
1. In the document, select the entire second row.
1. In the task pane, select the data item, and then select **Add repeater**.
1. Place the cursor in the first cell of the repeating row.
1. In the task pane, select the field for that column, and then select **Add field**.
1. Repeat the previous step for each remaining column.

## Create a customer list

This example creates a Word layout for report 101 **Customer List**. The layout lists each customer's number, name, salesperson code, and balance.

### Create and export a blank layout

1. [!INCLUDE [open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select **New**.
1. In the **Add New Layout for a Report** dialog, set **Report ID** to **101**.
1. Enter a descriptive value in **Layout Name**, and then set **Format Options** to **Word**.
1. Turn on **Create a blank layout from the report object**, and then select **OK**.
1. Select the new layout, and then select **Layout** > **Update and Export Layout**.

### Add customer fields with the task pane

1. Open the downloaded layout in Word.
1. Insert a table with two rows and four columns.
1. In the first row, enter the headings **No.**, **Name**, **Salesperson code**, and **Balance**.
1. On the **Business Central** tab, select **Add Data**.
1. Expand **Data** > **Customer**.
1. Select the second table row, select the `Customer` data item, and then select **Add repeater**.
1. Add `Customer_No_`, `CustAddr_1_`, `Customer__Salesperson_Code`, and `Customer_Balance_LCY` to the corresponding cells in the repeating row.
1. Save the layout.

### Add customer fields with Insert table

1. Open the downloaded layout in Word, and then place the cursor where you want the table.
1. On the **Business Central** tab, select **Insert table**.
1. Set **Data source** to **Customer**.
1. Add `Customer_No_`, `CustAddr_1_`, `Customer__Salesperson_Code`, and `Customer_Balance_LCY` as columns.
1. Set the headline options, turn on **Include header row** if needed, and then select **Create table**.
1. Save the layout.

Complete the steps in [Save and test a Word layout](#save-and-test-a-word-layout) to import and run the customer list.

## Add layout comments

Use **Insert layout comment** to add maintenance notes or a change history to a layout. A layout comment can contain text or tables. The comment appears while you design the layout but isn't included in the rendered report.

Add a comment in either of these ways:

- Add the text or table first. Select the content, and then select **Business Central** > **Insert layout comment**.
- Place the cursor where you want the comment, and then select **Business Central** > **Insert layout comment**. Replace the sample text inside the comment control.

When you place the cursor inside the control, Word shows its **Hidden Comment** border.

### Add a version history table

1. In Word, add a table with the columns **Layout description**, **Version**, and **Date of change**.
1. Add a row that describes the current layout version and change date.
1. Select the entire table.
1. On the **Business Central** tab, select **Insert layout comment**.
1. Save and import the layout, and then run the report to verify that the version history isn't included.

## Hide content that has no value

Use the controls in **Hide if empty** to prevent irrelevant content from appearing in the rendered report.

| Control | What to select | Example use |
|---|---|---|
| **Hide Field if Zero** | A stand-alone field or a field in a repeater | Hide a zero amount. |
| **Hide Empty Table** | The table, not its repeater control | Remove a table when its data item has no records. |
| **Hide Empty Table Row** | The field in the repeating row that controls visibility | Remove a row when the controlling field is empty. |
| **Hide Empty Table Column** | The controlling field in the table header | Remove a column when the field is empty for all records. |

Select the content that you want to control, and then select the appropriate action under **Hide if empty** on the **Business Central** tab. The exact selection depends on the control. For example, select a table before you apply **Hide Empty Table**, but select the field that controls the row's visibility before you apply **Hide Empty Table Row**.

You can combine **Hide Field if Zero** with **Hide Empty Table Column**. Apply **Hide Field if Zero** to the field in the repeating row, and then apply **Hide Empty Table Column** to its corresponding field in the table header. For example, use these controls to remove a discount column from an invoice when none of its rows has a discount.

## Save and test a Word layout

After you finish editing a Word layout, replace the file on the [user-defined layout](ui-manage-report-layouts.md#layout-sources) and test the result.

1. Save the document in Word.
1. In [!INCLUDE [prod_short](includes/prod_short.md)], return to the **Report Layouts** page.
1. Select the user-defined Word layout.
1. Select **Replace Layout**, confirm the action, and then select the edited `.docx` file.
1. Select **Run Report** to preview the result.

You can't replace an [extension-provided layout](ui-manage-report-layouts.md#layout-sources). Create a user-defined copy first, and then replace the file on the copy.

## Use the XML Mapping Pane instead

You don't need the Word add-in to design a Word layout. Use Word's **XML Mapping Pane** to map report fields directly to content controls. This method is useful when a Word add-in action isn't available or when you need to inspect the underlying XML structure.

Learn more in [Map data fields with the XML Mapping Pane](ui-how-add-fields-word-report-layout.md).

## Related information

[Set up reusable themes and header/footer layouts](ui-set-up-report-themes-header-footer-layouts.md)  
[Get started creating report layouts](ui-get-started-layouts.md)  
[Map data fields with the XML Mapping Pane](ui-how-add-fields-word-report-layout.md)  
[Create a Word layout report in AL](/dynamics365/business-central/dev-itpro/developer/devenv-howto-report-layout)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
