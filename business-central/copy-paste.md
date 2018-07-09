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

# Copying and Pasting in [!INCLUDE[d365fin](includes/d365fin_md.md)]
You can copy rows or field on a page, and paste them into the same page, another page, or even an external document like Microsoft Excel and Word. 
In short, to copy, you press CTRL+C (cmd+C in in macOS) on your keyboard, and to paste, you press the CTRL+V (cmd+V in macOS).

There are several other keyboard shortcuts for copying and pasting that help you save time when entering data. For more information about these. see [Keyboard Shortcuts](keyboard-shortcuts.md).

This article will try to answer some questions you might have about copying and pasting.  

## What can I copy and paste?
-   Copy One or more rows in [!INCLUDE[d365fin](includes/d365fin_md.md)] to the same list, or to any list with identical columns.
-   Copy One or more rows in [!INCLUDE[d365fin](includes/d365fin_md.md)] and paste into Excel or other applications.
-   Copy One or more rows in Excel and paste into a [!INCLUDE[d365fin](includes/d365fin_md.md)] list.
-   Copy the value of an individual field in [!INCLUDE[d365fin](includes/d365fin_md.md)] and paste it anywhere.

## How do I copy rows?
To copy a single row, simply select it, and press Ctrl+C.

If you want to copy more rows, you can two things:
-   Select another row and press Ctrl+Click or press Shift+Shift to select all rows in between.
-   Select in the first column of the list, choose **Select More**, and then set the check box next to each row that you want to copy. 

## Can I paste rows into an Outlook email or OneNote?
Yes. This is pasted as a nicely-formatted table that preserves indentation, numeric alignment and coloring, just as you would see in [!INCLUDE[d365fin](includes/d365fin_md.md)].

## Does copy and paste work with tiles?
No. The list must be viewed as rows (List View) for you to copy and paste.

## In which lists can I copy rows?
You can copy rows in any kind of list, including worksheets, FactBoxes, or list that are embedded on a page, like lines in a sales order. The list must be editable to paste any rows. In some pages, the application may prevent you from pasting of rows because of the way the underlying table setup. Contact your administrator or application developer to set the PasteIsValid property on the source table.

## On which clients is copy and paste available?
Copy and paste are available in the browser or Windows 10 desktop app for Business Central.

## What is the maximum rows that can be copied?
You can copy as many rows as you have scrolled into view. For example, to copy all 1000 rows in a page, you must first scroll to the bottom of the page and wait for the rows to appear before copying. The maximum number of rows you can copy is only limited by the memory of your device.

## Do I have the exact same number of columns when pasting rows in ?
Yes. Whether you are copying from [!INCLUDE[d365fin](includes/d365fin_md.md)], from Excel, or from some other table source, the rows that you paste must have the exact matching columns - no more no less.

## Where are rows pasted?
Rows are pasted directly where your cursor is located. If you paste into an empty line, any existing subsequent lines will be moved after the pasted lines. If you paste into an existing line or lines, this will be overwritten.

## Why do I get errors when pasting rows 
When pasting into [!INCLUDE[d365fin](includes/d365fin_md.md)], each row is checked to make sure that values in each column are valid. If a column contains a value that is not valid, the pasting is stopped, and an error message is displayed.

To avoid this, make sure that the columns have valid value before you paste them. ix the error and continue to paste in lines.


## See also
[Assistive Features](ui-accessibility.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Frequently Asked Questions](across-faq.md)  
