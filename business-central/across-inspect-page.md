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
# Inspecting Pages in in Business Central

The page inspection feature enables you to get details about a page, providing insight into the page design, the different elements that comprise the page, and the source behind the data it displays.

Page inspection is especially designed for administrators, power users, support personnel, and developers. Page inspection helps you:

- Learn the data model behind a page.

- Discover pages and parts that can be reused in you application design.

- Troubleshoot data issues without having to perform tasks like copying the production database, viewing the entire source table, or digging into SQL.

- Debug the application, complementing [Designer](https://docs.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/devenv-inclient-designer).


## Working with Page Inspection

To inspect a page, in the top right corner, choose ![Settings icon](media/ui-experience/settings_icon_small.png), then choose **Inspect**. Or, you can use the keyboard shortcut Crtl+Alt+F1.

The **Inspect Page** pane opens on the right side. The following figure illustrates the **Page Inspection** pane on the **Sales Order** page.

![Page Inspection](media/page-inspection-example.png)

When the **Page Inspection** pane first opens, it shows information that pertains to the main page object.

Use the keyboard or pointing device to move focus to different elements on the page. When you select a sub-page in a part or FactBox on the page, the related area is highlighted by an orange border, and the **Page Inspection** pane shows information about the selected element. For example, the previous figure shows information about the list part in the **Sales Order** page.

As you navigate to other pages in the application, the **Page Inspection** pane will automatically update with page information as you move along.

## What Page Inspection Shows

Page inspection shows the following information for any page or sub-page in a part or FactBox:

- Page name and ID.
- Source table of page, including the table's name and ID.

  For most tables, there is also a link that allows you to open the full table in a separate browser window.
- Table fields for the current record. Each field is shown with its name, number, data type, value, and a primary key indicator.
- Filters on the current page. This includes those that are set by code, Views, or user-defined.
- Extensions that affect the page. "Ext. page, Ext. table" or "New page, new table" (when it was added by the extension)

**Elements shown with limited information**  

- System parts, such as links and notes
- Reports request pages
- Role Center page types
- Pages that do not have a source table.


### [Table Fields](#tab/tablefields)

Table Fields tab displays information about all fields in the the current record. Each field is shown with its name, number, data type, value, and an indicator if the field is a primary key.

Page fields that are not bound to the source table field in their source expression are not shown.
Fields in temporary tables are not shown.
The value of fields that have a data type of blob, byte, media, or mediaset are not shown. 


Only extensions extending the page or source table are shown. Any other extensions are ignored.
We cannot show the value for some Field data types  (blob, byte, media/mediaset

### [Extensions](#tab/extensions)

The **Extensions** tab displays extensions that affect the page. "Ext. page, Ext. table" or "New page, new table" (when it was added by the extension)

Only extensions that add or extend the page or source table are shown. Any other extensions are ignored.

### [Page Filters](#tab/pagefilters)

The **Page Filters** tab displays the current filters used on the current page. This includes those that are set by code, Views, or user-defined.

### Elements shown with limited information**  

- System parts, such as links and notes
- Reports request pages
- Role Center page types
- Pages that do not have a source table.

## See Also  