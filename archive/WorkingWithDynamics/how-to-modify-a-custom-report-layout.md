---
    title: How to Modify a Custom Report Layout | Microsoft Docs
    description: This topic describes how to modify a custom layout that is available for a ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/nav_web_md.md)]--> client, you can only modify a report layout by exporting and importing the report layout as a file.
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
# Modify a Custom Report Layout
This topic describes how to modify a custom layout that is available for a ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/nav_web_md.md)]--> client, you can only modify a report layout by exporting and importing the report layout as a file.  
  
 There two different report layout types: Word report layouts and RDLC report layouts. You modify Word report layouts by using Microsoft Word and RDLC report layouts by using SQL Server Report Builder.  
  
> [!NOTE]  
>  You cannot modify built-in report layouts.  
  
##  <a name="ModFromWindowsCli"></a> Modifying a Custom Report Layout Directly From the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]-->  
 From the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]-->, you can open a custom layout directly in Word or SQL Server Report Builder, depending on the report layout type.  
  
###  <a name="EditLayoutFromWindowsClient"></a> To modify a report layout from the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]-->  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Report Layout Selection**, and then choose the related link.  
  
     The **Report Layout Selection** window lists all the reports that are available in the company that is specified in the **Company** field at the top of the window.  
  
2.  Set the **Company** field to the company that contains the report layout that you want to modify.  
  
3.  In the **Report Layout Selection** window, select the report that has the layout that you want to modify, and then on the **Home** tab, in the **Process** group, choose **Custom Layouts**.  
  
     The **Report Layouts** window appears and lists all the custom layouts that are available for the selected report.  
  
4.  Select the report layout that you want to modify, and then on the **Home** tab, choose **Edit Layout**.  
  
     A message appears and the report layout document opens in Word, if it is a Word report layout type, or SQL Server Report Builder, if it is a RDLC report layout type.  
  
    > [!IMPORTANT]  
    >  Do not close the message at this time.  
  
5.  Go to the document that opened and make changes to the report layout. For more information see, [Making Changes to the Report Layout](../WorkingWithDynamics/how-to-modify-a-custom-report-layout.md#MakeChangesToLayout) section that follows.  
  
6.  Save your changes, and then close the Word document.  
  
7.  Return the message in the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]-->, and then choose **Yes** to import the modified report layout.  
  
##  <a name="ModifyLayoutWeb"></a> Modifying a Custom Report Layout by Exporting and Importing the Layout File  
 Unlike the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_windows_md.md)]-->.  
  
###  <a name="EditLayoutFromWebClient"></a> To modify a report layout  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Report Layout Selection**, and then choose the related link.  
  
     The **Report Layout Selection** window lists all the reports that are available in the company that is specified in the **Company** field at the top of the window.  
  
2.  Set the **Company** field to the company that contains the report layout that you want to modify.  
  
3.  In the **Report Layout Selection** window, select the row for the report that has the layout that you want to modify, and then on the **Home** tab, in the **Process** group, choose **Custom Layouts**.  
  
     The **Report Layouts** window appears and lists all the custom layouts that are available for the selected report.  
  
4.  In the **Report Layouts** window, select the layout that you want to modify, and then on the **Home** tab, choose **Export Layout**.  
  
5.  Choose **Save** or **Save As** to save the report layout document to a location on your computer or network.  
  
6.  Open the report layout document that you saved, and then make changes. For more information see, [Making Changes to the Report Layout](../WorkingWithDynamics/how-to-modify-a-custom-report-layout.md#MakeChangesToLayout) section that follows.  
  
7.  Save the changes to the report layout document.  
  
8.  Return to the **Report Layouts** window, select the report layout that you exported, and then choose **Import Layout**.  
  
9. On the **Home** tab, choose **Import Layout**.  
  
10. In the **Import Microsoft Office Template** dialog box, select the report layout document that you modified, and then choose **Open**.  
  
##  <a name="MakeChangesToLayout"></a> Making Changes to the Report Layout  
 When modifying Word report layouts, you can make general formatting and layout changes, such as changing text font, adding and modifying a table, or removing a data field, by using the basic editing features of Word, like you do with any Word document. However, adding data fields from a ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]--> report dataset is a more advanced and requires some knowledge of the report dataset.  
  
 Making changes to RDLC report layouts is more advanced than Word report layouts. For more information about modifying an RDLC report layout, see [Designing RDLC Report Layouts](../FullExperience/Designing%20RDLC%20Report%20Layouts.md).  
  
#### To make changes to a Word Report Layout  
  
-   Use the following guidelines to make changes to a Word report layout.  
  
    -   For basic layout changes, use the editing features of Word.  
  
         If you are designing a Word report layout from scratch or adding new data fields, then start by adding a table that includes rows and columns that will eventually hold the data fields.  
  
    -   For information about adding fields for data, labels, data, and images, see [Add Fields to a Word Report Layout](../FullExperience/how-to-add-fields-to-a-word-report-layout.md).  
  
    -   For information about removing a label or data field, see [Removing Label and Data Fields in Word Layouts](../WorkingWithDynamics/how-to-modify-a-custom-report-layout.md#RemoveField).  
  
    > [!TIP]  
    >  Show the table gridlines so that you see the boundaries of table cells. Remember to hide the gridlines when you are done editing. To show or hide table gridlines, select the table, and then under **Layout** on the **Table** tab, choose **View Gridlines**.  
  
###  <a name="RemoveField"></a> Removing Label and Data Fields in Word Layouts  
 Label and data fields of a report are contained in content controls in Word. The following figure illustrates a content control when it is selected in the Word document.  
  
 ![Content control for field in Word report layout](../FullExperience/media/nav_wordreportlayouts_contentcontrol.png "NAV_WordReportLayouts_ContentControl")  
  
 The name of the label or data field name displays in the content control. In the example, the field name is CompanyAddr1.  
  
##### To remove a label or data field  
  
1.  Right-click the field that you want to delete, and then choose **Remove Content Control**.  
  
     The content control is removed, but the field name remains as text.  
  
2.  Delete the remaining text as needed.  
  
## See Also  
 [Managing Report Layouts From the Microsoft Dynamics NAV Clients](../FullExperience/managing-report-layouts-from-the-microsoft-dynamics-nav-clients.md)   
 [About Report Layouts](../FullExperience/about-report-layouts.md)   
 [Create a Custom Report Layout](../FullExperience/how-to-create-a-custom-report-layout.md)   
 [Add Fields to a Word Report Layout](../FullExperience/how-to-add-fields-to-a-word-report-layout.md)   
 [Create a Custom Report Layout](../FullExperience/how-to-create-a-custom-report-layout.md)