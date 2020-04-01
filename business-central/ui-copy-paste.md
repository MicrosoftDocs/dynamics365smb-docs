---
title: "Copy and paste data"
description: "Copy fields and rows from Business Central pages and paste somewhere else."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accessibility, shortcuts, keyboarding
ms.date: 04/01/2020
ms.author: sgroespe
---

# Copy and Paste FAQ
You can copy one or more rows (records) from a list or a single field on a page, and then paste what you copied into the same page, another page, or an external document (like Microsoft Excel and Outlook email). In short, to copy, you press CTRL+C (cmd+C in macOS) on your keyboard. To paste, you press CTRL+V (cmd+V in macOS).

There are several other keyboard shortcuts for copying and pasting that help you save time when entering data. For more information about these, see [Keyboard Shortcuts](keyboard-shortcuts.md#CopyRows).

This article answers common questions you might have about copying and pasting.  

## What can I copy and paste?
- Copy one or more rows in [!INCLUDE[d365fin](includes/d365fin_md.md)] to the same list, or to any list with identical columns.
- Copy one or more rows in [!INCLUDE[d365fin](includes/d365fin_md.md)] and paste into Excel or other applications.
- Copy one or more rows in Excel and paste into a [!INCLUDE[d365fin](includes/d365fin_md.md)] list.
- Copy the value of an individual field in [!INCLUDE[d365fin](includes/d365fin_md.md)] and paste it anywhere.

## Does copy and paste work with tiles?
Yes, but only for a single selected tile.

## How do I copy a row?
To copy a single row, select it, and then press Ctrl+C.

If you want to copy more rows, you can:
- Press Ctrl+Click on another row or press Shift+Click to select the row and all rows in between. See [Keyboard Shortcuts](keyboard-shortcuts.md#CopyRows) for more mouse and keyboard combinations for selecting rows.
- Select ![Show more options](media/show-more-options-icon.png "Show more options icon") in the first column, choose **Select More**, select the check box next to each row that you want to copy, and then press Ctrl+C.

## How do I paste rows?
Select an empty row, with focus in any cell, and then press Crtl+V.

If you want to replace existing rows, select the rows, and then press Crtl+V. In this case, you can only paste the same number of rows that you selected.

> [!NOTE]
> The list that you are pasting into must be editable.

<!-- Rows are pasted directly where your cursor is located. If you paste into an empty line, any existing subsequent lines will be moved after the pasted lines. If you paste into an existing line or lines, this will be overwritten.-->

## Can I paste rows into an Outlook email?
Yes. This is pasted as a nicely-formatted table that preserves indentation, numeric alignment and coloring, just as you would see in [!INCLUDE[d365fin](includes/d365fin_md.md)].

## In which lists can I copy and paste rows?
You can copy rows in any kind of list, including worksheets, FactBoxes, or list that are embedded on a page (like lines of a sales order). However, to paste rows, the list must be editable.

On some pages, the application design may prevent you from pasting rows. Contact your administrator or application developer to change the [Editable property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-editable-property) on the page or [PasteIsValid property](/dynamics365/business-central/dev-itpro/developer/properties/devenv-pasteisvalid-property) on the source table.

## On which clients is copy and paste available?
Copy and paste are available in the browser or the [!INCLUDE[d365fin](includes/d365fin_md.md)] app for Windows 10.

## What is the maximum number of rows that can be copied?
You can copy as many rows as you have scrolled into view. For example, to copy all 1000 rows on a page, you must first scroll to the bottom of the page and wait for the rows to appear before copying. The maximum number of rows you can copy is only limited by the memory of your device.

## Must I have the exact same number of columns when pasting rows?
Yes. Whether you are copying from [!INCLUDE[d365fin](includes/d365fin_md.md)], from Excel, or from some other table source, the rows that you paste into [!INCLUDE[d365fin](includes/d365fin_md.md)] must have the exact matching columns - no more no less.

## Why do I get errors when pasting rows?
When pasting into [!INCLUDE[d365fin](includes/d365fin_md.md)], each row is checked to make sure that values in each column are valid. If a column contains a value that is not valid, the pasting is stopped, and an error message is displayed. To avoid this, make sure that the columns have valid values before you paste them.


## See also
[Assistive Features](ui-accessibility.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Frequently Asked Questions](across-faq.md)  
