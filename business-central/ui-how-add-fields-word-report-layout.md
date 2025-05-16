---
title: How to Add Fields to a Word Report Layout
description: This topic describes how to add fields of a report dataset to an existing Word report layout for a report.
author: jswymer
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 10/01/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Work with Word Layouts

A Word report layout determines the content and format of a report when it is previewed and printed from Business Central. You create and modify these layouts using Microsoft Word.

[![Example of a word report layout document for Business Central.](media/word-layout.png)](media/word-layout.png#lightbox) 

When you modify a Word report layout, you specify the fields of the report dataset to include on report and how the fields are arranged. You also define the general format of the report, such as text font and size, margins, and background images. You will typically arrange the content of the report by adding tables to the layout.

To make general formatting and layout changes, such as changing text font, adding and modifying a table, or removing a data field, just use the basic editing features of Word, like you do with any Word document.

If you're designing a Word report layout from scratch or adding new data fields, then start by adding a table that includes rows and columns that will eventually hold the data fields.

> [!TIP]  
> Show the table gridlines so that you see the boundaries of table cells. Remember to hide the gridlines when you're done editing. To show or hide table gridlines, select the table, and then under **Layout** on the **Table** tab, choose **View Gridlines**.

## Embedding Fonts in Word Layouts for Consistency

To ensure that reports always display and print with the intended fonts, wherever users open or print the reports, you can embed the fonts in the Word document. However, embedding fonts can significantly increase the size of the Word files. Learn more about embedding fonts in Word at [Embed fonts in Word, PowerPoint, or Excel](https://support.office.com/article/Embed-fonts-in-Word-PowerPoint-or-Excel-cb3982aa-ea76-4323-b008-86670f222dbc).

## Adding data fields

A report dataset can consist of fields that display labels, data, and images. This topic describes the procedure for adding fields of a report dataset to an existing Word report layout for a report. You add fields by using the Word custom XML part for the report and adding content controls that map to the fields of the report dataset. Adding fields requires that you have some knowledge of the report's dataset so that you can identify the fields that you want to add to the layout.  
  
> [!NOTE]  
> You cannot modify built-in report layouts<!--Onprem. Built-in layouts can only be modified by using the development environment-->.  

###  <a name="OpenXMLPart"></a> To open the Custom XML part for the Report in Word  
  
1. If it's not already open, then open the Word report layout document in Word.  
  
     For more information, see [Create and Modify a Custom Report Layout](ui-how-create-custom-report-layout.md).  
  
2. Display the **Developer** tab in the ribbon of Microsoft Word.  
  
     By default, the **Developer** tab is not shown in the ribbon. Learn more at [Show the Developer Tab on the Ribbon](/visualstudio/vsto/how-to-show-the-developer-tab-on-the-ribbon).  
  
3. On the **Developer** tab, select **XML Mapping Pane**.  
  
4. In the **XML Mapping** pane, in the **Custom XML Part** dropdown list, choose the custom XML part for [!INCLUDE[prod_short](includes/prod_short.md)] report, which is typically last in the list. The name of the custom XML part has the following format:  
  
     `urn:microsoft-dynamics-nav/reports/<report_name>/<ID>`  

     `<report_name>` is the name that is assigned to the report 

     `<ID>` is the identification number of the report.  
  
     After you select the custom XML part, the XML Mapping pane displays the labels and field controls that are available for the report.  
  
### To add a label or data field  
  
1. Place your cursor in the document where you want to add the control.  
  
2. In the **XML Mapping** pane, right-click the control that you want to add, choose **Insert Content Control**, and then choose **Plain Text**.  
  
    > [!NOTE]  
    > You cannot add a field by manually typing the dataset field name in the content control. You must use the **XML Mapping** pane to map the fields.  
  
### To add repeating rows of data fields to create a list  
  
1. In a table, add a table row that includes a column for each field that you want repeated.  
  
   This row will act as a placeholder for the repeating fields.  
  
2. Select the entire row.  
  
3. In the **XML Mapping** pane, right-click the control that corresponds to the report data item that contains the fields that you want repeated, choose **Insert Content Control**, and then choose **Repeating**.  
  
4. Add the repeating fields to the row as follows:  
  
    1. Place your pointer in a column.  
  
    2. In the **XML Mapping** pane, right-click the control that you want to add, choose **Insert Content Control**, and then choose **Plain Text**.  
  
    3. For each field, repeat steps a and b.  
  
## Adding image fields

A report dataset can include a field that contains an image, such as a company logo or a picture of an item. To add an image from the report dataset, you insert a **Picture** content control.  
  
Images align in the top-left corner of the content control and resize automatically in proportion to fit the boundary of the content control.  
  
> [!IMPORTANT]  
> You can only add images that have a format that is supported by Word, such as .bmp, .jpeg, and .png file types. If you add an image that has a format that is not supported by Word, you will get an error when you run the report from the [!INCLUDE[prod_short](includes/prod_short.md)] client.  
  
### To add an image  
  
1. Place your pointer in the document where you want to add the control.  
  
2. In the **XML Mapping** pane, right-click the control that you want to add, choose **Insert Content Control**, and then choose **Picture**.  
  
3. To increase or decrease the image size, drag a sizing handle away from or towards the center of the content control.  

##  <a name="RemoveField"></a> Removing label and data fields

Label and data fields of a report are contained in content controls in Word. The following figure illustrates a content control when it's selected in the Word document.  

![Content control for field in Word report layout.](media/nav_wordreportlayouts_contentcontrol.png "NAV_WordReportLayouts_ContentControl")  

The name of the label or data field name displays in the content control. In the example, the field name is CompanyAddr1.  

### To remove a label or data field  

1. Right-click the field that you want to delete, and then choose **Remove Content Control**.  

     The content control is removed, but the field name remains as text.  

2. Delete the remaining text as needed.

## Custom XML Part Overview

Word report layouts are built on *custom XML parts*. A custom XML part for a report consists of elements that correspond to the data items, columns, and labels that comprise the report's dataset. <!--OnPrem The data as defined in the Report Dataset Designer in Microsoft Dynamics NAV Development Environment. -->The custom XML part is used to map the data into a report when the report is run.

### XML structure of custom XML part

The following table provides a simplified overview of the XML of a custom XML part.  
  
|XML Elements|Description|  
|------------------|-----------------|  
|`<?xml version="1.0" encoding="utf-16"?>`|Header|  
|`<WordReportXmlPart xmlns="urn:microsoft-dynamics-365/report/<reportname>/<id>/"`|XML namespace specification. `<reportname>` is the name that is assigned to the report. `<id>` is the ID that is assigned to the report.|  
|`..<Labels>`<br /><br /> `....<ColumnNameCaption>ColumnNameCaption</ColumnNameCaption>`<br /><br /> `....<LabelName>LabelCaption</LabelName>`<br /><br /> `..</Labels>`|Contains all the labels for the report.<!--OnPren The element includes labels that are related to columns that have the IncludeCaption Property.--><br />-   Label elements that are related to columns have the format `<ColumnNameCaption>ColumnNameCaption</ColumnNameCaption>`<!--OnPrem where `ColumnName` is determined by the column's Name Property.-->.<br />-  Label elements have the format `<LabelName>LabelName</LabelName`<!--OnPrem where LabelName is determined by the label's Name Property.-->.<br />-   Labels are listed in alphabetical order.|  
|`..<DataItem1>`<br /><br /> `....<DataItem1Column1>DataItem1Column1</DataItem1Column1>`|Top-level data item and columns. Columns are listed in alphabetical order.<!--OnPrem <br /><br /> The element names and values are determined by the Name Property of the data item or column.-->|  
|`....<DataItem2>`<br /><br /> `......<DataItem2Column1>DataItem2Column1</DataItem2Column1>`<br /><br /> `....</DataItem2>`<br /><br /> `....<DataItem3>`<br /><br /> `......<DataItem3Column1>DataItem3Column1</DataItem3Column1>`<br /><br /> `....</DataItem3>`|Data items and columns that are nested in the top-level data item. Columns are listed in alphabetical order under the respective data item.|  
|`..</DataItem1>`<br /><br /> `</WordReportXmlPart>`|Closing element.|  
  
### Custom XML part in Word

 In Word, you open the custom XML part in the **XML Mapping** pane, and then use the pane to map elements to content controls in the Word document. The **XML Mapping** pane is accessible from the **Developer** tab (learn more at [Show the Developer Tab on the Ribbon](/visualstudio/vsto/how-to-show-the-developer-tab-on-the-ribbon)).  
  
 The elements in the **XML Mapping** pane appear in a structure that is similar to the XML source. Label fields are grouped under a common **Labels** element and data item and columns are arranged in a hierarchal structure that corresponds to the XML source, with columns listed in alphabetical order. Elements are identified by their column name as defined in the report's dataset in AL code. Learn more in [Defining a Report Dataset](/dynamics365/business-central/dev-itpro/developer/devenv-report-dataset).  
  
 The following figure illustrates the simple custom XML part from the previous section in the **XML Mapping** pane of a Word document.  
  
 ![Clip of the XML Mapping pane in word.](media/nav_reportlayout_xmlmappingpane.png "NAV_ReportLayout_XMLMappingPane")  
  
* To add a label or field to the layout, you insert a content control that maps to the element in the **XML Mapping** pane.  
  
* To create repeating rows of columns, insert a **Repeating** content control for the parent data item element, and then add content control for the columns.  
  
* For labels, the actual text that appears in the generated report is the value of the **Caption** property for the field in the data item table (if the label is related to the column in the report dataset) or a label in the Report Label Designer (if the label is not related to a column in the dataset).  
  
* The language of the label that is displayed when you run the report depends on the language setting of the report object.  
  
## Related information

[Create and Modify a Custom Report Layout](ui-how-create-custom-report-layout.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
