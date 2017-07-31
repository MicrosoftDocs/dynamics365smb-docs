---
    title: How to: Add Fields to a Word Report Layout | Microsoft Docs
    description: A report dataset can consist of fields that display labels, data, and images. This topic describes the procedure for adding fields of a report dataset to an existing Word report layout for a report. You add fields by using the Word custom XML part for the report and adding content controls that map to the fields of the report dataset. Adding fields requires that you have some knowledge of the report's dataset so that you can identify the fields that you want to add to the layout. For more information about custom XML parts, see [Custom XML Part Overview for Word Report Layouts](../FullExperience/custom-xml-part-overview-for-word-report-layouts.md).
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
# How to: Add Fields to a Word Report Layout
A report dataset can consist of fields that display labels, data, and images. This topic describes the procedure for adding fields of a report dataset to an existing Word report layout for a report. You add fields by using the Word custom XML part for the report and adding content controls that map to the fields of the report dataset. Adding fields requires that you have some knowledge of the report's dataset so that you can identify the fields that you want to add to the layout. For more information about custom XML parts, see [Custom XML Part Overview for Word Report Layouts](../FullExperience/custom-xml-part-overview-for-word-report-layouts.md).  
  
> [!NOTE]  
>  You cannot modify built-in report layouts from a ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/nav_dev_long_md.md)]--> only.  
  
##  <a name="OpenXMLPart"></a> To open the Custom XML part for the Report in Word  
  
1.  If not already open, then open the Word report layout document in Word.  
  
     For more information, see [How to: Modify a Custom Report Layout](../FullExperience/how-to-modify-a-custom-report-layout.md).  
  
2.  Show the **Developer** tab in the ribbon of Microsoft Word.  
  
     By default, the **Developer** tab is not shown in the ribbon. For more information, see [How to: Show the Developer Tab on the Ribbon](http://go.microsoft.com/fwlink/?LinkID=389631).  
  
3.  On the **Developer** tab, choose **XML Mapping Pane**.  
  
4.  In the **XML Mapping** pane, in the **Custom XML Part** dropdown list, choose the custom XML part for ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> report, which is typically last in the list. The name of the custom XML part has the following format:  
  
     urn:microsoft-dynamics-nav/reports/*report_name*/*ID*  
  
     *report_name* is the name that is assigned to the report as specified by the report's [Name Property-duplicate](../FullExperience/nav_dev_long_md.md)]-->.  
  
     *ID* is the identification number of the report.  
  
     After you select the custom XML part, the XML Mapping pane displays the labels and field controls that are available for the report.  
  
### To add a label or data field  
  
1.  Place your cursor in the document where you want to add the control.  
  
2.  In the **XML Mapping** pane, right-click the control that you want to add, choose **Insert Content Control**, and then choose **Plain Text**.  
  
    > [!NOTE]  
    >  You cannot add a field by manually typing the dataset field name in the content control. You must use the **XML Mapping** pane to map the fields.  
  
### To add repeating rows of data fields to create a list  
  
1.  In a table, add a table row that includes a column for each field that you want repeated.  
  
     This row will act as a placeholder for the repeating fields.  
  
2.  Select the entire row.  
  
3.  In the **XML Mapping** pane, right-click the control that corresponds to the report data item that contains the fields that you want repeated, choose **Insert Content Control**, and then choose **Repeating**.  
  
4.  Add the repeating fields to the row as follows:  
  
    1.  Place your pointer in a column.  
  
    2.  In the **XML Mapping** pane, right-click the control that you want to add, choose **Insert Content Control**, and then choose **Plain Text**.  
  
    3.  For each field, repeat steps a and b.  
  
## Adding Image Fields  
 A report dataset can include a field that contains an image, such as a company logo or a picture of an item. To add an image from the report dataset, you insert a **Picture** content control.  
  
 Images align in the top-left corner of the content control and resize automatically in proportion to fit the boundary of the content control.  
  
> [!IMPORTANT]  
>  You can only add images that have a format that is supported by Word, such as .bmp, .jpeg, and .png file types. If you add an image that has a format that is not supported by Word, you will get an error when you run the report from the ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> client.  
  
#### To add an image  
  
1.  Place your pointer in the document where you want to add the control.  
  
2.  In the **XML Mapping** pane, right-click the control that you want to add, choose **Insert Content Control**, and then choose **Picture**.  
  
3.  To increase or decrease the image size, drag a sizing handle away from or towards the center of the content control.  
  
## See Also  
 [Custom XML Part Overview for Word Report Layouts](../FullExperience/custom-xml-part-overview-for-word-report-layouts.md)   
 [Managing Report Layouts From the Microsoft Dynamics NAV Clients](../FullExperience/managing-report-layouts-from-the-microsoft-dynamics-nav-clients.md)   
 [About Report Layouts](../FullExperience/about-report-layouts.md)   
 [How to: Create a Custom Report Layout](../FullExperience/how-to-create-a-custom-report-layout.md)   
 [How to: Add Fields to a Word Layout](../FullExperience/how-to-add-fields-to-a-word-report-layout.md)   
 [How to: Modify a Custom Report Layout](../FullExperience/how-to-modify-a-custom-report-layout.md)