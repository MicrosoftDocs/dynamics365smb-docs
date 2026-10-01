---
title: Map Data Fields in Word Layouts
description: Learn how to use the XML Mapping Pane in Word to manually map Business Central report data, labels, images, and repeating rows to content controls.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Word layout, XML Mapping Pane, custom XML part, content control, report field
ms.date: 09/09/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Add report data with the XML Mapping pane in Word

A Word layout controls the content and format of a report when you preview, print, or save it from Business Central. You can use Microsoft Word to arrange report fields, labels, images, and repeating data in a layout.

Use the Business Central add-in for Word for common layout tasks. The add-in provides a task pane for adding fields, repeaters, and data tables. Learn more in [Design Word layouts with the Business Central add-in](ui-design-word-layouts-business-central-add-in.md).

Use the **XML Mapping pane** when the Add-in isn't available, when you need to inspect the underlying custom XML, or when you want to map content controls manually.

:::image type="content" source="media/word-layout.png" alt-text="A Word layout with labels for the Developer tab, XML Mapping pane, data controls, tables, and repeating rows." lightbox="media/word-layout.png":::

> [!IMPORTANT]
> The **XML Mapping pane** is available in the desktop version of Word for Windows. If you use Word for the web or Word for Mac, use the Business Central Word add-in instead.

## Get a Word layout to modify

Export an existing layout or create a blank Word layout before you open the **XML Mapping pane**.

1. [!INCLUDE [open-report-layouts-page](includes/open-report-layouts-page.md)]
1. Select the Word layout that you want to use as a starting point.
1. Select **Layout** > **Update and Export Layout**.
1. Open the downloaded .docx file in Word.

Using **Update and Export Layout** updates the file with the current report dataset. To start without an existing design, create a blank Word layout. Learn more about creating a user-defined layout in [Create a new layout](ui-get-started-layouts.md#create).

> [!IMPORTANT]
> You can't replace an extension-provided layout. Create a user-defined copy before you upload your changes. Learn more in [Create a new layout](ui-get-started-layouts.md#create).

## Open the report custom XML part

The report's *custom XML part* contains elements for its data items, fields, and labels. You map these elements to Word content controls.

1. In Word, display the **Developer** tab. Learn more in [Show the Developer tab on the ribbon](/visualstudio/vsto/how-to-show-the-developer-tab-on-the-ribbon).
1. On the **Developer** tab, select **XML Mapping Pane**.
1. In the **Custom XML Part** list, select the Business Central report part. It's usually the last item and uses a name similar to this example:

   `urn:microsoft-dynamics-nav/reports/<report-name>/<id>`

The **XML Mapping** pane displays the labels, data items, and fields available in the report dataset.

## Add a label or data field

Add a mapped content control instead of typing the dataset field name into the document.

1. Place the cursor where you want the value.
1. In the **XML Mapping** pane, right-click the label or field.
1. Select **Insert Content Control** > **Plain Text**.

Word adds a content control that's mapped to the selected report value. Use standard Word features to position and format it.

## Add repeating rows

Use a repeating content control to show one table row for each record in a report data item.

1. Add a Word table with a placeholder row that has one column for each field that you want to repeat.
1. Select the entire placeholder row.
1. In the **XML Mapping** pane, right-click the data item that contains the fields you want to repeat.
1. Select **Insert Content Control** > **Repeating**.
1. Place the cursor in the first cell of the repeating row.
1. In the **XML Mapping** pane, right-click the field for that column, and then select **Insert Content Control** > **Plain Text**.
1. Repeat the previous step for the other cells in the row.

> [!TIP]
> To see the boundaries of table cells while you work, select the table, and then select **Layout** > **View Gridlines** under **Table**. Gridlines don't appear when the report is printed.

## Add an image field

A report dataset can include an image, such as a company logo or an item picture.

1. Place the cursor where you want the image.
1. In the **XML Mapping** pane, right-click the image field.
1. Select **Insert Content Control** > **Picture**.
1. Resize the content control as needed.

The image aligns in the upper-left corner and keeps its proportions when it is resized to fit the content control. Use Word formatting to change the alignment of the image.

> [!IMPORTANT]
> Use an image format supported by Word, such as .bmp, .jpeg, or .png. The report shows an error if Word can't render the image format.

## Remove a mapped field

Mapped fields appear as content controls in the Word document.

:::image type="content" source="media/nav_wordreportlayouts_contentcontrol.png" alt-text="A selected content control for a field in a Word layout.":::

1. Right-click the content control.
1. Select **Remove Content Control**.
1. Delete the remaining text if you no longer want it in the layout.

Removing the content control removes the mapping. It doesn't automatically remove the text displayed inside the control.

## Save and test the layout

1. Save the .docx file in Word.
1. In Business Central, return to the **Report Layouts** page.
1. Select the user-defined Word layout.
1. Select **Replace Layout**, confirm the action, and then select the edited file.
1. Select **Run Report** to preview the result.

## Understand the custom XML structure

The custom XML part reflects the report dataset:

- The `Labels` element contains report labels and captions.
- Top-level data item elements each contain the fields for that data item.
- Nested data items appear below their parent data item.
- Fields and labels are listed by the names defined in the report dataset.

:::image type="content" source="media/nav_reportlayout_xmlmappingpane.png" alt-text="The XML Mapping Pane showing labels, data items, and fields for a report.":::

The text displayed for a field label comes from the field caption or a label defined in the report. The report language determines the translated label used when the report runs.

Learn more about the underlying dataset in [Define a report dataset](/dynamics365/business-central/dev-itpro/developer/devenv-report-dataset).

## Embed fonts for consistent output

You can embed fonts in the Word document to help reports display and print consistently on different devices. Embedded fonts can significantly increase the size of the layout file. Learn more in [Embed fonts in Word, PowerPoint, or Excel](https://support.microsoft.com/office/embed-fonts-in-word-or-powerpoint-cb3982aa-ea76-4323-b008-86670f222dbc).

## Related information

[Design Word layouts with the Business Central add-in](ui-design-word-layouts-business-central-add-in.md)  
[Get started creating report layouts](ui-get-started-layouts.md)  
[Report and document layouts overview](ui-manage-report-layouts.md)  
[Set the layout used by a report](ui-set-report-layout.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
