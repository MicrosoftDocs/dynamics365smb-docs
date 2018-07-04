---
title: "Copy and paste data"
description: "Copy fields and rows from Business Central pages and paste somewhere else."
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accessibility, shortcuts, keyboarding
ms.date: 05/18/2018
ms.author: jswymer
---

# Copying and Pasting Data

## How do I copy data


## Exactly what can I copy and paste?
-   Copy one or more rows in Business Central to the same list, or to any list with identical columns.
-   Copy one or more rows in Business Central and paste into Excel or other applications.
-   Copy one or more rows in Excel and paste into Business Central list.
-   Copy the value of an individual field in Business Central and paste anywhere.
 
## Why did the Copy cell above shortcut not realign to Excel's equivalent Ctrl+Alt+'?
A. Unlike some shortcuts which activate a task such as bringing up the filter pane, "copy cell" is something the user may repeat quickly and often within the space of seconds. Logically, a 3-key shortcut will make this painful or impossible, drastically reducing the value of introducing the shortcut key. In this case, we therefore prefer to align with NAV and continue F8.
 
Q. Why did we drop Ctrl+Shift+C to copy rows?
A. The industry standard is Ctrl+C and having a Shift modifier for what is the most valuable copy operation is counterintuitive. We also now have the technology to determine context and infer whether the user is trying to copy a row or a cell. Partners have also given feedback that the old shortcut was confusing.
 
Q. Why is our ability to paste rows to eg. Outlook far superior than that of the Windows Client?
A. WinCli pasted plain text whereas Web can paste a high fidelity version of what you see in the browser, including table borders and styling, value colouring, indentation and correct alignment of values. The WinCli could only come close using the Print & Send >> Email as Attachment feature which was tabular but lacked awareness of the currently selected rows, couldn't display indentation, value colouring, etc..
 
## When do I get a message during a Paste operation?
You get a message when you try to paste in a list that is not editbale (view or read only), or when the list has blocked from pasting the developer via the PasteIsValid property.
 
## How many rows can be copied?
This depends on how much you have scrolled. The toast will indicate the number of copied rows. There is no cap on how much you can copy, and the limit is your client device memory. You can potentially copy thousands of rows. As a rough indicator, an average list of 100 rows and 10 columns consumes 0.5Mb
 
## Does copy and paste work with tiles?
No. This is primarily because tiles still do not have a good multiselection experience.

## Must I have the exact same columns when pasting?
Yes. Whether you are copying from NAV or from Excel or some other table, this must have the exact matching columns, no more no less.


## See also
[Assistive Features](ui-accessibility.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Frequently Asked Questions](across-faq.md)  
