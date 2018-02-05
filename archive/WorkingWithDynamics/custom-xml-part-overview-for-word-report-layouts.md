---
    title: Custom XML Part Overview for Word Report Layouts | Microsoft Docs
    description: Word report layouts are built on *custom XML parts*. A custom XML part is structured XML that represents the dataset of a ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> client.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Custom XML Part Overview for Word Report Layouts
Word report layouts are built on *custom XML parts*. A custom XML part is structured XML that represents the dataset of a ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> client.  
  
## XML Structure of Custom XML Part  
 A custom XML part for a ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/nav_dev_long_md.md)]-->.  
  
 The following table provides a simplified overview of the XML of a custom XML part.  
  
|XML Elements|Description|  
|------------------|-----------------|  
|`<?xml version="1.0" encoding="utf-16"?>`|Header|  
|`<NavWordReportXmlPart xmlns="urn:microsoft-dynamics-nav/report/<reportname>/<id>/"`|XML namespace specification. `<reportname>` is the name that is assigned to the report object in ADD INCLUDE<!--[!INCLUDE[nav_dev_long](../../includes/nav_dev_long_md.md)]-->. `<id>` is the ID that is assigned to the report.|  
|`..<Labels>`<br /><br /> `....<ColumnNameCaption>ColumnNameCaption</ColumnNameCaption>`<br /><br /> `....<LabelName>LabelCaption</LabelName>`<br /><br /> `..</Labels>`|Contains all the labels for the report. The element includes labels that are related to columns that have the [IncludeCaption Property](../FullExperience/Name%20Property-duplicate.md).<br />-   Labels are listed in alphabetical order.|  
|`..<DataItem1>`<br /><br /> `....<DataItem1Column1>DataItem1Column1</DataItem1Column1>`|Top-level data item and columns. Columns are listed in alphabetical order.<br /><br /> The element names and values are determined by the [Name Property-duplicate](../FullExperience/Name%20Property-duplicate.md) of the data item or column.|  
|`....<DataItem2>`<br /><br /> `......<DataItem2Column1>DataItem2Column1</DataItem2Column1>`<br /><br /> `....</DataItem2>`<br /><br /> `....<DataItem3>`<br /><br /> `......<DataItem3Column1>DataItem3Column1</DataItem3Column1>`<br /><br /> `....</DataItem3>`|Data items and columns that are nested in the top-level data item. Columns are listed in alphabetical order under the respective data item.|  
|`..</DataItem1>`<br /><br /> `</NavWordReportXmlPart>`|Closing element.|  
  
## Custom XML Part in Word  
 In Word, you open the custom XML part in the **XML Mapping** pane, and then use the pane to map elements to content controls in the Word document. The **XML Mapping** pane is accessible from the **Developer** tab (for more information, see [Show the Developer Tab on the Ribbon](http://go.microsoft.com/fwlink/?LinkID=389631)).  
  
 The elements in the **XML Mapping** pane appear in a structure that is similar to the XML source. Label fields are grouped under a common **Labels** element and data item and columns are arranged in a hierarchal structure that corresponds to the XML source, with columns listed in alphabetical order. Elements are identified by their name as defined by the Name property in Report Dataset Designer in ADD INCLUDE<!--[!INCLUDE[nav_dev_short](../../includes/nav_dev_short_md.md)]-->.  
  
 The following figure illustrates the simple custom XML part from the previous section in the **XML Mapping** pane of a Word document.  
  
 ![Clip of the XML Mapping pane in word](../FullExperience/media/nav_reportlayout_xmlmappingpane.png "NAV_ReportLayout_XMLMappingPane")  
  
-   To add a label or field to the layout, you insert a content control that maps to the element in the **XML Mapping** pane.  
  
-   To create repeating rows of columns, insert a **Repeating** content control for the parent data item element, and then add content control for the columns.  
  
-   For labels, the actual text that appears in the generated report is the value of the **Caption** property for the field in the data item table (if the label is related to the column in the report dataset) or a label in the Report Label Designer (if the label is not related to a column in the dataset).  
  
-   The language of the label that is displayed when you run the report depends on the language setting of the report object. For more information, see [Multiple Document Languages](../FullExperience/Viewing%20the%20Application%20in%20Different%20Languages.md).  
  
 For information about how to open the custom XML part in Word and add fields, see [Add Fields to a Word Report Layout](../FullExperience/how-to-add-fields-to-a-word-report-layout.md).  
  
## See Also  
 [Managing Report Layouts From the Microsoft Dynamics NAV Clients](../FullExperience/managing-report-layouts-from-the-microsoft-dynamics-nav-clients.md)   
 [About Report Layouts](../FullExperience/about-report-layouts.md)   
 [Create a Custom Report Layout](../FullExperience/how-to-create-a-custom-report-layout.md)   
 [Add Fields to a Word Report Layout](../FullExperience/how-to-add-fields-to-a-word-report-layout.md)   
 [Modify a Custom Report Layout](../FullExperience/how-to-modify-a-custom-report-layout.md)