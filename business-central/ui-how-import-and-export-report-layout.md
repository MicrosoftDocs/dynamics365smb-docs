---
    title: Importing and Exporting a Report and Document Layout | Microsoft Docs
    description: You can import and export an existing custom report layout as a file to and from a location on your computer and network.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Import and Export Custom Report Layouts
You can import and export an existing custom report layout as a file to and from a location on your computer and network. For example, you can export a report layout, and then send the file to another person to modify. That person can then make the modifications to layout and return the file to you so that you can import it back.  

> [!IMPORTANT]  
>  You cannot import or export built-in report layouts.  

### To export a report layout to a file  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layout Selection**, and then choose the related link.  

2.  Select the row for the report that contains the custom report layout that you want to export, and then choose the **Custom Layouts** action.  

3.  On the **Report Layouts** page, select the report layout that you want to export to a file, and then choose the **Export Layout** action.  

4.  In the **Export File** dialog box, choose the **Save** button, and then save the file to a location on your computer or network.  

### To import a report layout file  

1.  Make sure that the relevant file that defines the report layout is available on your computer or network.  

     A Word report layout file must have the .docx file type extension. An RDLC report layout file must have the .rdlc or .rdl file type extension.  

2.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layout Selection**, and then choose the related link.  

3.  Select the row for the report to which you want to import the report layout, and then choose the **Custom Layouts** action.  

4.  On the **Report Layouts** page, select the report layout to which you want to import the file, and then choose the **Import Layout** action.  

5.  In the **Import** dialog box, select the document that defines the report layout, and then choose the **Open** button.  

 The original custom report layout is replaced with the imported report layout.  

## See Related Training at [Microsoft Learn](/learn/modules/change-documents-dynamics-365-business-central/index)

## See Also  
 [Create and Modify a Custom Report Layout](ui-how-create-custom-report-layout.md)   
 [Managing Report and Document Layouts](ui-manage-report-layouts.md)  
 [Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)    
