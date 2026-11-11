---
title: (Obsolete) Import and Export Custom Report Layouts
description: Export and import Word or RDLC layout files in versions of Business Central that still provide the legacy Custom Report Layouts page and its actions.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 9652, 9650
ms.date: 11/11/2026
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# (Obsolete) Import and export custom report layouts

[!INCLUDE[legacy-custom-layouts](includes/legacy-custom-layouts.md)]

These procedures apply only to versions that still include the legacy pages. For the current workflow, learn more in [Get started creating report layouts](ui-get-started-layouts.md).

You can import and export an existing custom report layout as a file to and from a location on your computer and network. For example, you can export a report layout, and then send the file to another person to modify. That person can then modify the layout and return the file to you so that you can import it back.

> [!IMPORTANT]  
> You can't import a file to overwrite a built-in layout. Create a custom layout before importing a modified file.

## Export a report layout to a file

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Report Layout Selection**, and then choose the related link.  

1.  Select the row for the report that contains the custom report layout that you want to export, and then choose the **Custom Layouts** action.

1.  On the **Custom Report Layouts** page, select the report layout that you want to export to a file, and then choose **Export Layout**.

1.  Save the downloaded file to a location on your computer or network.

## Import a report layout file

1.  Make sure that the relevant file that defines the report layout is available on your computer or network.  

     A Word report layout file must have the .docx file type extension. An RDLC report layout file must have the .rdlc or .rdl file type extension.  

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Report Layout Selection**, and then choose the related link.

1.  Select the row for the report to which you want to import the report layout, and then choose the **Custom Layouts** action.

1.  On the **Custom Report Layouts** page, select the report layout to which you want to import the file, and then choose **Import Layout**.

1.  In the **Import** dialog box, select the document that defines the report layout, and then choose **Open**.

 The original custom report layout is replaced with the imported report layout.  

## Related information

[Create and Modify a Custom Report Layout](ui-how-create-custom-report-layout.md)   
[Managing Report and Document Layouts](ui-manage-report-layouts.md)  
[Work with Reports, Batch Jobs, and XMLports](ui-work-report.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
