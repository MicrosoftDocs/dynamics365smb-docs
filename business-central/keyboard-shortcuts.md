---
title: "Keyboard Shortcuts"
description: "The complete list of keyboard shortcut combinations to work efficiently with your data."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accessibility, shortcuts, keyboarding, keys
ms.date: 04/03/2020
ms.author: sgroespe
---

# Keyboard Shortcuts
This article provides an overview of some of the shortcut key combinations that you can use when you're working with [!INCLUDE[prodshort](includes/prodshort.md)].

For an overview of the most popular keyboard shortcuts, see [Keyboard Shortcuts (PC only)](keyboard-shortcuts-cheatsheet.md).

> [!TIP]
> For a graphical view of the most used shortcuts, choose the following image and download the PDF file.
>
> [ ![](media/keyboard_shortcut_inline.png) ](media/keyboard_shortcuts.pdf)

## Overview
Keyboard shortcuts aid accessibility and can make it easier and more efficient to navigate to different areas and elements on a page. They're supported by most web browsers, however, the behavior may vary slightly.

> [!NOTE]
> The keyboard shortcuts described here refer to the U.S. keyboard layout. The layout of the keys on other keyboards may not correspond exactly to the keys on a U.S. keyboard.

Most of the shortcuts are the same whether the operating system is Windows or macOS. However, some shortcuts differ for macOS. These shortcuts are indicated with brackets in the following sections.

> [!NOTE]
> In addition to the global keyboard shortcuts described in this topic, a number of business-specific shortcuts are available. For example, in the generic version of [!INCLUDE[prodshort](includes/prodshort.md)], F9 posts a document and Ctrl+F7 shows the financial entries for a record. (These may be different in you solution.) The keyboard shortcut is shown in the tooltip for the action in question.

##  <a name="Keyboard"></a> General Keyboard Shortcuts
The following table describes keyboard shortcuts for navigating and accessing different elements of a page. Elements include things like actions, drop-down lists, lookups, and more. For details about keyboard shortcuts for navigating records once you get inside a list, see the next section.

|Press these keys<br />(in macOS)|To do this|
|----------------|-----------|
|Alt+Down Arrow|Open a drop-down list or look up a value for a field.|    
|Alt+Up Arrow|Show tooltip for a field or a column header of a table. If the field has validation errors, press Alt+Up Arrow to show the validation error. Press Esc or Alt+Up Arrow to close the tooltip.|
|F2|Toggle between selecting the entire field value or placing the cursor at the end of the field value.|
|Alt+F2|Show and hide the FactBox pane.|
|Alt+Shift+F2|Shift between **Details** and **Attachments** in the FactBox pane.|
|Alt+O|Add a new note for the selected record, even if the FactBox pane isn't open.|
|Alt+Q<br />(Ctrl+Option+Q)|Open the **Tell Me** window. For more information, see [Finding Pages and Information with Tell Me](ui-search.md).|
|Alt+N |Open a page to create a new record. (Similar to choosing the **New** and **+** actions.)|
|Alt+Shift+N |Close a newly created page and open a new one to create a new record. Similarly, Alt+F9 posts a document and creates a new one.|
|Alt+T|Open the **My Settings** page.|
|Alt+Right Arrow|Look up additional information or underlying values for a field that contains the ![AssistEdit](media/assist-edit-icon.png "AssistEdit button") button. This is used when the usual drop-down button (Alt+Down Arrow) in the same field is used for another purpose.|
|Shift+F12|Open the role explorer, a feature overview. For more information, see [Finding Pages with the Role Explorer](ui-role-explorer.md).|
|Ctrl+Alt+Shift+C|Display information in the company badge.|
|Ctrl+Alt+F1|Open and close the page inspection pane. The page inspection pane shows information about the page, like its source table, fields, filters, extensions, and more.<br /><br />For more information, see [Inspecting Pages](across-inspect-page.md).|
|Ctrl+C |Copy the value of field. If the field is in focus, and you haven't selected any text in the field, this will copy the entire value. If you've selected any text in the field, then it will copy the selected text only.|
|Ctrl+F1|Open the Business Central help for the page.|
|Ctrl+F12|Switch between wide and narrow layout view.|
|Ctrl+Click|Navigate during personalizing or customizing when the action is highlighted with an arrowhead. For more information, see [Personalize Your Workspace](ui-personalization-user.md).|  
|Ctrl+F5|Reload the [!INCLUDE[prodshort](includes/prodshort.md)] application. (Similar to selecting refresh/reload in the browser.)|
|F5|Refresh the data on the current page.<br /><br />Use this key to ensure that the data on the page is up to date with any changes that others have made while you're working.|
|Enter|Enable or access the element or control that is in focus.|
|Esc|Close the current page or drop-down list.|
|Tab|Move focus to the next control or element on a page, such as actions, buttons, fields, or list headings.|
|Shift+Tab|Move focus to the previous control or element on a page, such as actions, buttons, fields, or list headings.|
|Y and N|Activate **Yes** and **No** buttons in dialog boxes. Actual keys will vary based on your current language specified in **My Settings**. For example, press J to activate the **Ja** button when using German language.|

## Keyboard Shortcuts in Lists

The following table describes the keyboard shortcuts that you can use on a list page. The shortcut action is slightly different depending on whether the page is shown in the list view or tile view.
<!--
> [!Note]
> In the table that follows, the term *actionable field* refers to a field on which you can do something, like change a value or link to another page. In general, the shortcuts will skip over fields that display information that you cannot change from the list (in other words, fields that are read-only).
-->
### General

|Press these keys<br />(in macOS)|To do this in a list view|To do this in a tile view |
|-----------------|-------|-------|
|Alt+F7 |Sort the selected column in ascending or descending order.|Not applicable.|
|Alt+N|Insert a new line in an editable list, such as the **G/L Budgets** page.|Same.|
|Shift+F10 |Open a menu of options that are available for the selected row.|Same.|

### <a name="navigateshortcuts"></a>Navigating Between Rows and Columns
Grids containing rows and columns exist on many page types in [!INCLUDE[prodshort](includes/prodshort.md)], such as list pages and **Lines** parts on documents. Moving from one cell to another across a grid is fully keyboard-enabled.

|Press these keys<br />(in macOS)|To do this in a list view |To do this in a tile view |
|-----------------|-------|-------|
|Ctrl+Home<br />(Fn+Ctrl+Left Arrow)|Select the first row in the list; focus remains in the same column.|Move to the first tile in the first row. |
|Ctrl+End<br />(Fn+Ctrl+Right Arrow)|Select the last row in the list; focus remains in the same column.|Move to the last tile in the last row.|
|Home<br />(Fn+Left Arrow)|Move to the first field in the row.|Move to the first tile in the row.|
|End<br />(Fn+right Arrow)|Move to the last field in the row.|Move to the last tile in the row.|
|Enter|Open the record that is associated with the field.<br /><br />Only relevant if a card page is associated with the record.|Opens the record.<br /><br />Only relevant if a card page is associated with the record.|
|Ctrl+Enter|Move focus to the next element outside the list.|Move focus to the next element outside the list.|
|Page Up<br />(Fn+Up Arrow)|Scroll to display the set rows above the current rows in view. |Scrolls to display the set of tiles above the current tiles in view. |
|Page Down<br />(Fn+Down Arrow)|Scroll to display the set rows below the current rows in view.|Scroll to display the set of tiles below the current tiles in view.|
|Down Arrow|Move in the same column to the field in the row below. |Move in the same column to the tile in the row below. |
|Up Arrow|Move in the same column to the field in the row above.| Move in the same column to the tile in the row above.  |
|Right Arrow|In a view-only list, move in the same row to the next field to the right.<br /><br />In an editable list, move to the right within the current field.| Move in the same row to the next tile to the right. |
|Left Arrow|In a view-only list, move in the same row to the previous field to the left. <br /><br />In an editable list, move to the left within the current field.| Move in the same row to the previous tile to the left. |
|Tab|In editable list, move in the same row to the next field to the right.|Not applicable.||
|Shift+Tab|In editable list, move in the same row to the previous field to the left. | Not applicable. |


### <a name="CopyRows"></a>Selecting, Copying, and Pasting

|Press these keys<br />(in macOS)|To do this in a list view |To do this in a tile view |
|-----------------|-------|-------|
|Ctrl+Click<br />(Cmd+Click)|Extend the selection of rows to include the row that you click.|Not applicable.|
|Shift+Click|Extend the selection of rows to include the row that you click and all the rows in between.<br /><br />You can use this after using Ctrl+Up Arrow or Ctrl+Up Down to expand your selection.|Not applicable.|
|Ctrl+Up Arrow<br />(Ctrl+Cmd+Up Arrow)|Move focus to the row above and keep the current row selected.|Not applicable.|
|Ctrl+Down Arrow<br />(Ctrl+Cmd+Down Arrow)|Move focus to the row below and keep the current row selected.|Not applicable.|
|Ctrl+Space Bar<br />(Ctrl+Cmd+Space)|Extend the selection of rows to include the focused row.<br /><br />You can use this after using Ctrl+Up Arrow or Ctrl+Down Arrow to expand your selection.|Not applicable.|
|Ctrl+A|Select all rows.|Not applicable.|
|Ctrl+C<br />(Cmd+C)|Copy the selected rows to the Clipboard.|Yes, but only for a single selected tile.|
|Ctrl+V<br />(Cmd+V)|Paste the selected rows from the Clipboard into the current page or external document, like Microsoft Excel or Outlook email. You can only do this in editable lists.|Not applicable.|
|Shift+Up Arrow|Extend the selection of rows to include the row above.|Not applicable.|
|Shift+Down Arrow|Extend the selection of rows to include the row below.|Not applicable.|
|Shift+Page Up<br />(Shift+Fn+Up Arrow)|Extend the selection of rows to include all visible rows above the current selection of rows.|Not applicable.|
|Shift+Page Down<br />(Shift+Fn+Down Arrow)|Extend the selection of rows to include all visible rows below the current selection of rows.|Not applicable.|
|F8|Copy the field in the same column of the row above, and paste it into the current row. You can only do this in editable lists. Using this shortcut followed by a Tab lets you quickly fill out fields in line items that you want to have the same value as the row above.|Not applicable.|

### <a name="KeyboardFilter"></a>Searching and Filtering Lists

|Press these keys<br />(in macOS)|To do this|
|-----------------|-------|
|F3|Toggles the search box.<ul><li>Activate the search box, so you can start typing your search text.</li><li>If the search box is already activated, F3 returns to the list without clearing the search text.</li><ul>|
|Shift+F3|Open and close the filter pane.<ul><li> If the filter pane isn't open, Shift+F3 opens it and focuses on the **+ Filter** action under **Filter list by**. You can then just hit Enter to start adding a field filter.</li><li>If the filter pane is already open, Shift+F3 closes it but doesn't clear any filters that you've added.</li></ul>|
|Ctrl+Shift+F3|Open and close the filter pane.<ul><li> If the filter pane isn't open, Ctrl+Shift+F3 opens it and focuses on the **+ Filter** action under **Filter total by**. You can then just hit Enter to start adding a totals filter.</li><li>If the filter pane is already open, Ctrl+Shift+F3 closes it but doesn't clear any filters that you've added.</li></ul>  |
|Alt+F3|Toggle filtering to the selected value.<ul><li>Applies a column filter on the selected field value in the list. This does the same as choosing **Filter to this value** from a column heading. It opens the filter pane, sets filter to the selected value, while focus remains on cell in the list.</li><li>If the column is already filtered, Alt+F3 clears the filter on that column.</li></ul> |
|Shift+Alt+F3|Open the filter pane and add a filter on the selected column in the list. Focus is on the new filter field, which lets you start typing the filter criteria right away.<br /><br /> This does the same as selecting **Filter** from the column heading.<br /><br />If there is already a filter on the field, a new filter is added. |
|Ctrl+Shift+Alt+F3|Reset filters. This does the same as choosing **Reset filters** in the filter pane, and it applies to field and totals filters.<br /><br /> Filters return to the default filters for the current view. If the current view is **All**, then this is the same as returning to an unfiltered view with all records. |
|Ctrl+Enter|Change focus from the filter pane back to the list.|

## Keyboard Shortcuts in Cards and Documents

The following shortcuts are available on card pages, such as **Customer Card**, and document pages, such as **Sales Order**, to display and modify records.

|Press these keys<br />(in macOS)|To do this|
|----------------|-----------|
|Alt+F6|Toggle collapse/expand for the current FastTab or part (subpage).|
|Alt+N |Open a page to create a new record; the same way as choosing the **New** action. |
|Alt+Shift+N |Close a page and open a new one to create a new record; the same way as selecting the **OK & New** action. |
|Alt+Shift+W |Open the current card or document in a new window. For more information, see [Multitasking Across Multiple Pages](ui-enter-data.md#multitasking-across-multiple-pages).|
|Ctrl+Enter|Save and close the page.|
|Ctrl+Down Arrow|Open the next record for an entity.|
|Ctrl+Up Arrow |Open the previous record for an entity.|
|Ctrl+Insert |Insert a new line in documents.|
|Ctrl+Delete |Delete the line, in documents, journals, and worksheets.|
|Ctrl+Shift+F12 |Maximize the line items part on a document page. Press the keys again to return to the normal display. For more information, see [Focusing on Line Items](ui-enter-data.md#Focus).|
|F6|Move to the next FastTab or part (subpage).|
|Shift+F6|Move to previous FastTab or part (subpage).|

## <a name="QuickEntry"></a>Quick Entry Shortcuts for Fields

The following shortcuts pertain to the Quick Entry feature on cards, documents, and list pages. On lists, the shortcuts cannot be used when the list is in the tile view. For more information about Quick Entry, see [Accelerating Data Entry Using Quick Entry](ui-enter-data.md#QuickEntry).

|Press these keys<br />(in macOS)|To do this|Remarks|
|-----------------|-------|-------|
|Enter|Confirm the value in the current field and go to the next Quick Entry field.||
|Shift+Enter|Confirm the value in the current field and go to the previous Quick Entry field.||
|Ctrl+Shift+Enter|Confirm the value in the current column and go to next Quick Entry field outside the list.<br /><br />This shortcut applies to embedded lists on a page, such as line items on a sales order. It enables you to quickly get out of the list and continue entering data in other fields on the page.|

## <a name="calendarshortcuts"/> Keyboard Shortcuts in the Calendar (Date Picker)

When setting a date field, you can either enter the date manually or open a calendar (date picker) that lets you select the date you want. The following table describes the keyboard shortcuts for the calendar.

|Press these keys<br />(in macOS)|To do this|
|-----------------|-------|
|Ctrl+Home|Open the calendar if closed. **Note**: This doesn't work if the date field is in a grid, where Ctrl+Home jumps to the first row.|
|Ctrl+Home<br />(Cmd+Home)|Move to the current month, current day.|
|Ctrl+Left Arrow<br />(Cmd+Left Arrow)|Move to the previous day.|
|Ctrl+Right Arrow<br />(Cmd+Right Arrow)|Move to the next day.|
|Ctrl+Up Arrow<br />(Cmd+Up Arrow)|Move to the previous week, same day of the week.|
|Ctrl+Down Arrow<br />(Cmd+Down Arrow)|Move to the next week, same day of the week.|
|Enter|Select the focused date.|
|Ctrl+End<br />(Cmd+End)|Close the calendar and delete the current date.|
|Esc|Close the calendar without a selection, keep the current date.|
|Page Down|Move to the next month.|
|Page Up|Move to the previous month.|  

## Keyboard Shortcuts in Date Fields
|Press these keys<br />(in macOS)|To do this|
|-----------------|-------|
|t|Enter the current date. "T" stands for "today".|
|w|Enter the work date. For more information, see [Work Date](ui-change-basic-settings.md#work-date)|

## <a name="reportpreviewshortcuts"/>Keyboard Shortcuts in the Report Preview

|Press these keys<br />(in macOS)|To do this|
|-----------------|-------|
|Down Arrow|Scroll down the page.|  
|Up Arrow|Scroll up the page.|
|Ctrl+0 (zero)<br />(Cmd+0)|Fits the entire page on the page. |
|Ctrl+Home<br />(Cmd+Home)|Go to the first page of the report.|
|Ctrl+End<br />(Cmd+Home)|Go to the last page of the report.|
|Left Arrow|Scroll to the left when the page is zoomed in so that it isn't entirely in view. |
|Right Arrow|Scroll to the right when the page is zoomed in so that it isn't entirely in view. |
|Page Down<br />(Fn+Down Arrow)|Go to the next page of the report.|
|Page Up<br />(Fn+Up Arrow)|Go to the previous page of the report.|

## See also
[Keyboard Quick Reference - PC Only](keyboard-shortcuts-cheatsheet.md)  
[Assistive Features](ui-accessibility.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Frequently Asked Questions](across-faq.md)  
