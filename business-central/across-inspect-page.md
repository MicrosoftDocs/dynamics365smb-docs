---
title: "Inspecting Pages in Business Central"
description: Use the page inspection feature to get details about the page design and data source. 
ms.custom: na
ms.date: 17/12/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.service: dynamics365-business-central
author: jswymer
---
# Inspecting Pages

The page inspection feature enables you to get details about a page, providing insight into the page design, the different elements that comprise the page, and the source behind the data it displays.

Page inspection is especially designed for administrators, power users, support personnel and developers. Page inspection can help you:

- Learn the data model behind a page.

- Discover pages and parts that can be reused in you application design.

- Troubleshoot data issues without having to perform tasks like copying the production database, viewing the entire source table, or digging into SQL.

- Debug the application, complementing [Designer](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-inclient-designer).


## Start Page Inspection

To inspect a page, in the top right corner, choose ![Settings icon](media/ui-experience/settings_icon_small.png), then choose **Inspect**. Or, you can press Crtl+Alt+F1. The **Inspect Page** pane opens on the right. The following figure illustrates the **Page Inspection** pane on the **Sales Order** page. 

![Page Inspection](media/page-inspection-example.png)

You can move focus to different areas on the page by using a mouse or keyboard. If you select a page part or FactBox on the page, the area is highlighted with an orange border, and the **Page Inspection** pane shows information about the selected element. For example, the figure shows information about the list part in the Sales Order page. 

Once you start page inspection, you can navigate to other pages in the application and the **Page Inspection** pane will then update to show the information for the page that is shown.


## What Page Inspection Shows

Page inspections shows the following information for any page, page part, or FactBoxes:

- Page name and ID
- Source table of page, including the name and ID.
- Table fields of the current record, including name, number, data type, and value.

    There is also a link that allows you to open the full table in the client.
- Filters on the current page, including those that are set by code, Views, or user-defined.
- Extensions that are used on the page.


<!-- MUST show source table caption, source table ID
MUST show all field captions+values of current record.
MUST respect security features such as masking, field/row-level security etc.
SHOULD show field ID (or any better non-language-specific identifier)
COULD show field data type
MUST show a summary of the filters on the page (programmatically-set, via Views, user-specified)
SHOULD show list of extensions affecting page
SHOULD show originating extension (or base application) of page
Features
SHOULD be able to navigate to view the contents of the entire table (ie. generate a Url with ?table=<id>), preferably only show this IF the user has the system permission to use that feature.
UX
MUST be able to activate page inspector while any page is active, even if modal.
MUST be able to focus page inspector on any page or page part (subpage).
MUST be able to keep page information side-by-side with the page to facilitate usage and prevent having to "re-enter" inspector as the user navigates and inspects different pages.
SHOULD be able to immediately update page information in page inspector with a single click on the page. The click may also change current record.
SHOULD be able to select a field in page inspector and keep that field in view while the user clicks within the page canvas to change record.
  
- Page Information  
  
- Table Fields, sorted first by key fields, then alphabetically  
  
- Source Expressions  
  
- FlowFilter Fields  
  
- Filters  
  
- URLs that open the page clients and in SOAP and OData web services.  
  
  
> [!NOTE]  
>  To see more information about a subpage, such as a Factbox or a Line page, you must use the shortcut for About This Page, CTRL+ALT+F1.  
  
  
> [!NOTE]  
>  The About This Report feature remains active during the client session. When the feature is active, the size of the data that is sent to the client when you run a report is about twice the size of the data when the feature is not active. To deactivate the feature, restart the client.  
  
## URLs for the Page or Report  
 The About This Page window includes a FastTab where you can see the URLs for opening the page. For example, if you want to save the hyperlink to open a page in the client, you can copy the URL from the About This Page window. Similarly, you can get the URL for a report from the request page for the report. For more information, see [How to: Copy the URL to Open a Page or Report](How-to--Copy-the-URL-to-Open-a-Page-or-Report.md).  
  
 The URLs are generated based on the current [!INCLUDE[nav_server](includes/nav_server_md.md)] configuration.  
  
## Troubleshooting with About This Page and About This Report  
 You can use the About This Page and About This Report features to help you troubleshoot and debug issues. For example, if you create a new page and need to troubleshoot the data that is displayed on the page, then you can use the About This Page feature to view all the fields for the current record, including filters that were set by the user and FlowFilter fields.  
  
## Exporting About This Page Information
  
 You can export the About This Page information to the following formats:  
  
- HTML attachment in a new e-mail message  
  
- Microsoft Word document  
  
- Microsoft Excel spreadsheet  
  
  You can also print the About This Page information directly from the **About This Page** window.  -->
  
## See Also  