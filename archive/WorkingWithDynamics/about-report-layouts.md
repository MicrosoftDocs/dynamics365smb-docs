---
    title: About Report Layouts | Microsoft Docs
    description: A report layout is a document that acts as a template that defines the appearance of a ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> report when viewing, printing, or saving the report. In particular, a report layout sets up the following:
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
# About Report Layouts
A report layout is a document that acts as a template that defines the appearance of a ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> report when viewing, printing, or saving the report. In particular, a report layout sets up the following:  
  
-   The label and data fields to include from the dataset of the ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> report.  
  
-   The text format, such as font type, size and color.  
  
-   The company logo and its position.  
  
-   General page settings, such as margins and background images.  
  
 A ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> report can be set up with multiple report layouts, which you can switch among as required. You can use one of the built-in report layouts or you can create custom report layouts and assign them to your reports as needed.  
  
 There are two types of report layouts that you can use on reports, *Word* and *RDLC*.  
  
 For more information, see the following sections on this topic.  
  
-   [Word Report Layout Overview](../WorkingWithDynamics/about-report-layouts.md#WordLayout)  
  
-   [RDLC Layout Overview](../WorkingWithDynamics/about-report-layouts.md#RDLCLayout)  
  
-   [Built-in and Custom Report Layouts](../WorkingWithDynamics/about-report-layouts.md#BuiltinLayout)  
  
##  <a name="WordLayout"></a> Word Report Layout Overview  
 A Word report layout is a based on Word document (.docx file type). Word report layouts enable you to design report layouts by using Microsoft Word 2013. A Word report layout determines the report's content - controlling how that content elements are arranged and how they look. A Word report layout document will typically use tables to arrange content, where the cells can contain data fields, text, or pictures. For example, the following figure illustrates the Word report layout document that is used on sales invoice report as it appears when opened in Word for editing.  
  
 ![Example of a word report layout document for NAV](../FullExperience/media/nav_wordreportlayout_edit_in_word_example.png "NAV_WordReportLayout_Edit_In_Word_Example")  
  
 In the example, the tables are set up to show the gridlines. Showing the gridlines is useful when you are editing the Word report layout so that you can see table cell boundaries. However, you should hide the gridlines when you are finished editing. To show or hide table gridlines, select the table, and then under **Layout** on the **Table** tab, choose **View Gridlines**.  
  
> [!NOTE]  
>  Images that are based on a field in the report dataset, which means they are defined in a content control, cannot be displayed when you edit the layout in Word. They will appear in the report when it is run.  
  
 The following figure illustrates the previous sales invoice report as it appears when you preview it from the ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> client.  
  
 ![Shows report 1306 run from the client](../FullExperience/media/nav_wordreportlayout_example_from_client.png "NAV_WordReportLayout_Example_From_Client")  
  
 Notice that the label and data fields have been replaced with actual data for the customer.  
  
### Label and Data Fields  
 The label and data fields are defined by *content controls*. Content controls act as placeholders for the actual report data. In the Word report layout document, the content controls only include a reference to a field in the report dataset, as shown in the following figure.  
  
 ![Content control for field in Word report layout](../FullExperience/media/nav_wordreportlayouts_contentcontrol.png "NAV_WordReportLayouts_ContentControl")  
  
 It is only when the report is run from the ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> client that actual data appears.  
  
 Label and data fields are added to the Word report layout by using custom XML parts. For more information, see [Custom XML Part Overview for Word Report Layouts](../FullExperience/how-to-add-fields-to-a-word-report-layout.md).  
  
##  <a name="RDLCLayout"></a> RDLC Layout Overview  
 RDLC layouts are based on client report definition layouts (.rdlc or .rdl file types). These layouts are created and modified by using SQL Server Report Builder. The design concept for RDLC layouts is similar to Word layouts, where the layout defines the general format of the report and determines the fields from the dataset to include. Designing RDLC layouts is more advanced than Word layouts. For more information about RDLC layout design, see [Designing RDLC Report Layouts](../FullExperience/Designing%20RDLC%20Report%20Layouts.md).  
  
##  <a name="BuiltinLayout"></a> Built-in and Custom Report Layouts  
 Your ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> client but you use them as a starting point for building your own custom report layouts.  
  
 *Custom layouts* are report layouts that you design to change the appearance of a report. You typically create a custom layout based on a built-in layout, but you can create them from scratch or from a copy of an existing custom layout. Custom layouts enable you to have multiple layouts for the same report, which you switch among as needed. For example, you can have different layouts for each ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> company, or you can have different layouts for the same company for specific occasions or events, like a special campaign or holiday season.  
  
## See Also  
 [Deciding Whether to use a Word or RDLC Report Layout](../FullExperience/deciding-whether-to-use-a-word-or-rdlc-report-layout.md)   
 [Managing Report Layouts From the Microsoft Dynamics NAV Clients](../FullExperience/managing-report-layouts-from-the-microsoft-dynamics-nav-clients.md)   
 [Create a Custom Report Layout](../FullExperience/how-to-create-a-custom-report-layout.md)   
 [Modify a Custom Report Layout](../FullExperience/how-to-modify-a-custom-report-layout.md)