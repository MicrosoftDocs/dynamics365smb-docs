---
title: Keyboard shortcuts
description: The complete list of keyboard shortcut combinations to work efficiently with your data.
author: jswymer
ms.topic: conceptual
ms.search.keywords: accessibility, shortcuts, keyboarding, keys
ms.date: 12/14/2023
ms.author: jswymer
ms.review: jswymer
ms.service: dynamics365-business-central
ms.custom: bap-template
---

# Keyboard shortcuts

This article provides an overview of some of the shortcut key combinations that you can use when you're working with [!INCLUDE[prod_short](includes/prod_short.md)].

For an overview of the most popular keyboard shortcuts, see [Keyboard shortcuts (PC only)](keyboard-shortcuts-cheatsheet.md).

> [!TIP]
> For a graphical view of the most used shortcuts, choose the following image and download the PDF file.  
> [ ![Icon for the PDF file.](media/keyboard_shortcut_inline.png) ](media/keyboard-shortcuts-2023.pdf "Icon that opens a PDF")



## Overview

Keyboard shortcuts aid accessibility and can make it easier and more efficient to navigate to different areas and elements on a page. Most web browsers support these shortcuts, however, the behavior might vary slightly.

> [!NOTE]
> The keyboard shortcuts described here refer to the U.S. keyboard layout. The layout of the keys on other keyboards can not correspond exactly to the keys on a U.S. keyboard.

Most of the shortcuts are the same whether the operating system is Windows or macOS. However, some shortcuts differ for macOS. These shortcuts are indicated with brackets in the following sections.

> [!NOTE]
> Business Central only supports a single character set for data. Therefore, some characters may not be supported in your environment, and you may experience problems when retrieving data that was entered using a different character set. This may also apply to keyboard shortcuts. For instance, your environment may support only English and Russian characters. In this case, if you enter data in a different language, it may not be stored correctly. You should contact your system administrator to make sure you understand which languages are supported by your Business Central. 

> [!NOTE]
> In addition to the global keyboard shortcuts described in this article, a number of business-specific shortcuts are available. For example, in the generic version of [!INCLUDE[prod_short](includes/prod_short.md)], <kbd>F9</kbd> posts a document and <kbd>Ctrl</kbd>+<kbd>F7</kbd> shows the ledger entries for a record when you open the record in a card. This article includes some of the more common business-specific shortcuts, which are shown in italics. Be aware that the actual shortcuts may be different in your solution. In the user interface, the keyboard shortcut is shown in the tooltip for the action in question.

##  <a name="Keyboard"></a> General keyboard shortcuts

The following table describes keyboard shortcuts for navigating and accessing different elements of a page. Elements include things like actions, drop-down lists, lookups, and more. For details about keyboard shortcuts for navigating records once you're inside a list, see the next section.

|Select these keys<br />(in macOS)|To do this|
|--------------------------------|----------|
|<kbd>Alt</kbd>|Show access keys for selecting actions in the action bar and navigation menu on the page. For more information, go to [Access keys](#access-keys-for-action-bar-and-navigation-menu).|
|<kbd>Alt</kbd>+<kbd>Down Arrow</kbd>|Open a drop-down list or look up a value for a field.|
|<kbd>Ctrl</kbd>+<kbd>Option</kbd>+<kbd>Down Arrow</kbd>|Open a related record's card or list page filtered to the value in the lookup or assist edit field.|
|<kbd>Alt</kbd>+<kbd>Up Arrow</kbd>|Show tooltip for a field or a column header of a table. If the field has validation errors, select <kbd>Alt</kbd>+<kbd>Up Arrow</kbd> to show the validation error. Select <kbd>Esc</kbd> or <kbd>Alt</kbd>+<kbd>Up Arrow</kbd> to close the tooltip.|
|<kbd>F2</kbd>|Toggle between selecting the entire field value or placing the cursor at the end of the field value.|
|<kbd>Alt</kbd>+<kbd>F2</kbd>|Show and hide the FactBox pane.|
|<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>F2</kbd>|<kbd>Shift</kbd> between **Details** and **Attachments** in the FactBox pane.|
|<kbd>Alt</kbd>+<kbd>O</kbd>|Add a new note for the selected record, even if the FactBox pane isn't open.|
|<kbd>Alt</kbd>+<kbd>Q</kbd><br /><br />(<kbd>Ctrl</kbd>+<kbd>Option</kbd>+<kbd>Q</kbd>)|Open the **Tell Me** window. For more information, see [Finding pages and information with Tell Me](ui-search.md).|
|<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Q</kbd><br /><br />(<kbd>Ctrl</kbd>+<kbd>Option</kbd>+<kbd>Cmd</kbd>+<kbd>Q</kbd>)|Open the **Find Entries** page to find documents and entries related to each other based on common information, like document number or posting date. For more information, see [Finding related entires for posted documents](ui-find-entries.md)|
|<kbd>Alt</kbd>+<kbd>N</kbd> |Open a page to create a new record. (Similar to choosing the **New** and **+** actions.)|
|<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>N</kbd> |Close a newly created page and open a new one to create a new record. Similarly, <kbd>Alt</kbd>+<kbd>F9</kbd> posts a document and creates a new one.|
|<kbd>Alt</kbd>+<kbd>T</kbd>|Open the **My Settings** page.|
|<kbd>Alt</kbd>+<kbd>Right Arrow</kbd>|Look up additional information or underlying values for a field that contains the ![AssistEdit.](media/assist-edit-icon.png "AssistEdit button") button. Used when the usual drop-down button (<kbd>Alt</kbd>+<kbd>Down Arrow</kbd>) in the same field is used for another purpose.|
|<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>C</kbd>|Display information in the company badge. As of the Business Central 2022 release wave 2 (version 21), this shortcut is no longer supported and replaced by <kbd>Ctrl</kbd>+<kbd>O</kbd>. |
|<kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>F1</kbd>|Open and close the page inspection pane. The page inspection pane shows information about the page, like its source table, fields, filters, extensions, and more.<br /><br />For more information, see [Inspecting pages](across-inspect-page.md).|
|<kbd>Ctrl</kbd>+<kbd>C</kbd> |Copy the value of field. If the field is in focus, and the text isn't selected in the field, then the entire value is copied. If you select any text in the field, then the selected text is copied.|
|<kbd>Ctrl</kbd>+<kbd>F1</kbd>|Open the [help pane](product-help-and-support.md#help-pane) or a Business Central help article on [Microsoft Learn](/dynamics365/business-central/), depending on your Business Central version.|
|<kbd>Ctrl</kbd>+<kbd>F12</kbd>|Switch between wide and narrow layout view.|
|<kbd>Ctrl</kbd>+select|Navigate during personalizing or customizing when the action is highlighted with an arrowhead. For more information, see [Personalize your workspace](ui-personalization-user.md).|  
|<kbd>Ctrl</kbd>+<kbd>F5</kbd>|Reload the [!INCLUDE[prod_short](includes/prod_short.md)] application. (Similar to selecting refresh/reload in the browser.)|
|<kbd>F5</kbd>|Refresh the data on the current page.<br /><br />Use this key to ensure that the data on the page is updated with any changes made by others while you're working.|
|<kbd>Ctrl</kbd>+<kbd>O</kbd>|Open the **Available Companies** pane for switching to another company or environment. For more information, see [Switching to another company or environment](ui-organization-switch.md).|
|<kbd>Enter</kbd>|Enable or access the element or control that is in focus.|
|<kbd>Esc</kbd>|Close the current page or drop-down list.|
|<kbd>Tab</kbd>|Move focus to the next control or element on a page, such as actions, buttons, fields, or list headings.|
|<kbd>Shift</kbd>+<kbd>Tab</kbd>|Move focus to the previous control or element on a page, such as actions, buttons, fields, or list headings.|
|<kbd>Y</kbd> and <kbd>N</kbd>|Activate the **Yes** and **No** buttons in dialog boxes. Actual keys vary based on your current language specified in **My Settings**. For example, select <kbd>J</kbd> to activate the **Ja** button when using German language.|

## Keyboard shortcuts in lists

The following table describes the keyboard shortcuts that you can use on a list page. The shortcut action is slightly different depending on whether the page is shown in the list view or tile view.
<!--
> [!Note]
> In the table that follows, the term *actionable field* refers to a field on which you can do something, like change a value or link to another page. In general, the shortcuts will skip over fields that display information that you cannot change from the list (in other words, fields that are read-only).
-->
### General

|Select these keys<br />(in macOS)|To do this in a list view|To do this in a tile view |
|--------------------------------|-------------------------|--------------------------|
|<kbd>Alt</kbd>+<kbd>F7</kbd> |Sort the selected column in ascending or descending order.|Not applicable.|
|<kbd>Alt</kbd>+<kbd>N</kbd>|Insert a new line in an editable list, such as the **G/L Budgets** page.|Same.|
|<kbd>Shift</kbd>+<kbd>F9</kbd>|Post and print a document.|Same.|
|<kbd>Shift</kbd>+<kbd>F10</kbd> |Open a menu of options that are available for the selected row.|Same.|
|<kbd>Alt</kbd>+<kbd>D</kbd>|Open the dimension set entries.|Same.|
|<kbd>Ctrl</kbd>+<kbd>F7</kbd>|Open ledger entries, logs entries, cost entries, and so on.|
|<kbd>Ctrl</kbd>+<kbd>F9</kbd>|Release document.|Same.|
|<kbd>F7</kbd>|Open statistics.|Same.|
|<kbd>F9</kbd>|Post, issue, register, or reverse document.|Same.|
|<kbd>Shift</kbd>+<kbd>Ctrl</kbd>+<kbd>F</kbd>|Send suggested lines on the **Cash Flow Worksheet** page.|Not applicable.|
|<kbd>Shift</kbd>+<kbd>Ctrl</kbd>+<kbd>I</kbd>|View serial and lot numbers assigned to the line item on the document or journal.|Not applicable.|

### <a name="navigateshortcuts"></a>Navigate between rows and columns

Grids containing rows and columns exist on many page types in [!INCLUDE[prod_short](includes/prod_short.md)], such as list pages and **Lines** parts on documents. Moving from one cell to another across a grid is fully keyboard-enabled.

| Select these keys<br />(in macOS) | To do this in a list view | To do this in a tile view |
|--|--|--|
| <kbd>Ctrl</kbd>+<kbd>Home</kbd><br /><br />(<kbd>Fn</kbd>+<kbd>Ctrl</kbd>+<kbd>Left Arrow</kbd>) | Select the first row in the list; focus remains in the same column. | Move to the first tile in the first row. |
| <kbd>Ctrl</kbd>+<kbd>End</kbd><br /><br />(<kbd>Fn</kbd>+<kbd>Ctrl</kbd>+<kbd>Right Arrow</kbd>) | Select the last row in the list; focus remains in the same column. | Move to the last tile in the last row. |
| <kbd>Home</kbd><br /><br />(<kbd>Fn</kbd>+<kbd>Left Arrow</kbd>) | Move to the first field in the row. | Move to the first tile in the row. |
| <kbd>End</kbd><br /><br />(<kbd>Fn</kbd>+<kbd>Right Arrow</kbd>) | Move to the last field in the row. | Move to the last tile in the row. |
| <kbd>Enter</kbd> | Open the record that is associated with the field.<br /><br />Only relevant if a card page is associated with the record. | Opens the record.<br /><br />Only relevant if a card page is associated with the record. |
| <kbd>Ctrl</kbd>+<kbd>Enter</kbd> | Move focus to the next element outside the list. | Move focus to the next element outside the list. |
| <kbd>Page Up</kbd><br /><br />(<kbd>Fn</kbd>+<kbd>Up Arrow</kbd>) | Scroll to display the set rows above the current rows in view. | Scrolls to display the set of tiles above the current tiles in view. |
| <kbd>Page Down</kbd><br /><br />(<kbd>Fn</kbd>+<kbd>Down Arrow</kbd>) | Scroll to display the set rows below the current rows in view. | Scroll to display the set of tiles below the current tiles in view. |
| <kbd>Down Arrow</kbd> | Move in the same column to the field in the row below. | Move in the same column to the tile in the row below. |
| <kbd>Up Arrow</kbd> | Move in the same column to the field in the row above. | Move in the same column to the tile in the row above. |
| <kbd>Right Arrow</kbd> | In a view-only list, move in the same row to the next field to the right.<br /><br />In an editable list, move to the right within the current field. | Move in the same row to the next tile to the right. |
| <kbd>Left Arrow</kbd> | In a view-only list, move in the same row to the previous field to the left. <br /><br />In an editable list, move to the left within the current field. | Move in the same row to the previous tile to the left. |
| <kbd>Tab</kbd> | In editable list, move in the same row to the next field to the right. | Not applicable. | 
| <kbd>Shift</kbd>+<kbd>Tab</kbd> | In editable list, move in the same row to the previous field to the left. | Not applicable. |

### <a name="CopyRows"></a>Select, Copy, and Paste

|Select these keys<br />(in macOS)|To do this in a list view |To do this in a tile view |
|--------------------------------|--------------------------|--------------------------|
|<kbd>Ctrl</kbd>+select<br /><br />(<kbd>Cmd</kbd>+select)|Extend the selection of rows to include the row that you select.|Not applicable.|
|<kbd>Shift</kbd>+select|Extend the selection of rows to include the row that you select and all the rows in between.<br /><br />You can use this after using <kbd>Ctrl</kbd>+<kbd>Up Arrow</kbd> or <kbd>Ctrl</kbd>+<kbd> Down Arrow</kbd> to expand your selection.|Not applicable.|
|<kbd>Ctrl</kbd>+<kbd>Up Arrow</kbd><br /><br />(<kbd>Ctrl</kbd>+<kbd>Cmd</kbd>+<kbd>Up Arrow</kbd>)|Move focus to the row above and keep the current row selected.|Not applicable.|
|<kbd>Ctrl</kbd>+<kbd>Down Arrow</kbd><br /><br />(<kbd>Ctrl</kbd>+<kbd>Cmd</kbd>+<kbd>Down Arrow</kbd>)|Move focus to the row below and keep the current row selected.|Not applicable.|
|<kbd>Ctrl</kbd>+<kbd>Space Bar</kbd><br /><br />(<kbd>Ctrl</kbd>+<kbd>Cmd</kbd>+Space)|Extend the selection of rows to include the focused row.<br /><br />You can use this after using <kbd>Ctrl</kbd>+<kbd>Up Arrow</kbd> or <kbd>Ctrl</kbd>+<kbd>Down Arrow</kbd> to expand your selection.|Not applicable.|
|<kbd>Ctrl</kbd>+<kbd>A</kbd>|Select all rows.|Not applicable.|
|<kbd>Ctrl</kbd>+<kbd>C</kbd><br /><br />(<kbd>Cmd</kbd>+<kbd>C</kbd>)|Copy the selected rows to the Clipboard.|Yes, but only for a single selected tile.|
|<kbd>Ctrl</kbd>+<kbd>V</kbd><br /><br />(<kbd>Cmd</kbd>+<kbd>V</kbd>)|Paste the selected rows from the Clipboard into the current page or external document, like Microsoft Excel or Outlook email. You can only do this in editable lists.|Not applicable.|
|<kbd>Shift</kbd>+<kbd>Up Arrow</kbd>|Extend the selection of rows to include the row above.|Not applicable.|
|<kbd>Shift</kbd>+<kbd>Down Arrow</kbd>|Extend the selection of rows to include the row below.|Not applicable.|
|<kbd>Shift</kbd>+<kbd>Page Up</kbd><br /><br />(<kbd>Shift</kbd>+<kbd>Fn</kbd>+<kbd>Up Arrow</kbd>)|Extend the selection of rows to include all visible rows above the current selection of rows.|Not applicable.|
|<kbd>Shift</kbd>+<kbd>Page Down</kbd><br /><br />(<kbd>Shift</kbd>+<kbd>Fn</kbd>+<kbd>Down Arrow</kbd>)|Extend the selection of rows to include all visible rows below the current selection of rows.|Not applicable.|
|<kbd>F8</kbd>|Copy the field in the same column of the row above, and paste it into the current row. You can only do this in editable lists. Using this shortcut followed by a <kbd>Tab</kbd> lets you quickly fill out fields in line items that you want to have the same value as the row above.|Not applicable.|

### <a name="KeyboardFilter"></a>Search and filter lists

|Select these keys<br />(in macOS)|To do this|
|--------------------------------|----------|
|<kbd>F3</kbd>|Toggles the search box.<ul><li>Activate the search box, so you can start typing your search text.</li><li>If the search box is already activated, <kbd>F3</kbd> returns to the list without clearing the search text.</li><ul>|
|<kbd>Shift</kbd>+<kbd>F3</kbd>|Open and close the filter pane.<ul><li> If the filter pane isn't open, <kbd>Shift</kbd>+<kbd>F3</kbd> opens it and focuses on the **+ Filter** action under **Filter list by**. You can then just hit <kbd>Enter</kbd> to start adding a field filter.</li><li>If the filter pane is already open, <kbd>Shift</kbd>+<kbd>F3</kbd> closes it, but doesn't clear any filters that you added.</li></ul>|
|<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>F3</kbd>|Open and close the filter pane.<ul><li> If the filter pane isn't open, <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>F3</kbd> opens it and focuses on the **+ Filter** action under **Filter total by**. You can then just hit <kbd>Enter</kbd> to start adding a totals filter.</li><li>If the filter pane is already open, <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>F3</kbd> closes it, but doesn't clear any filters that you added.</li></ul>  |
|<kbd>Alt</kbd>+<kbd>F3</kbd>|Toggle filtering to the selected value.<ul><li>Applies a column filter on the selected field value in the list. This does the same as choosing **Filter to this value** from a column heading. It opens the filter pane, sets filter to the selected value, while focus remains on cell in the list.</li><li>If the column is already filtered, <kbd>Alt</kbd>+<kbd>F3</kbd> clears the filter on that column.</li></ul> |
|<kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>F3</kbd>|Open the filter pane and add a filter on the selected column in the list. Focus is on the new filter field, which lets you start typing the filter criteria right away.<br /><br /> This does the same as selecting **Filter** from the column heading.<br /><br />If there's already a filter on the field, a new filter is added. |
|<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>F3</kbd>|Reset filters. This does the same as choosing **Reset filters** in the filter pane, and it applies to field and totals filters.<br /><br /> Filters return to the default filters for the current view. If the current view is **All**, then this is the same as returning to an unfiltered view with all records. |
|<kbd>Ctrl</kbd>+<kbd>Enter</kbd>|Change focus from the filter pane back to the list.|

## Keyboard shortcuts in cards and documents

The following shortcuts are available on card pages, such as **Customer Card**, and document pages, such as **Sales Order**, to display and modify records.

|Select these keys<br />(in macOS)|To do this|
|--------------------------------|----------|
|<kbd>Alt</kbd>+<kbd>D</kbd>|Open the dimension set entries.|
|<kbd>Alt</kbd>+<kbd>F6</kbd>|Toggle collapse/expand for the current Fast<kbd>Tab</kbd> or part (subpage).|
|<kbd>Alt</kbd>+<kbd>F9</kbd>|Create new document and post it.|
|<kbd>Alt</kbd>+<kbd>G</kbd>|Open the **Find Entries** page for finding entries related to the posted document. Works on lists also.|
|<kbd>Alt</kbd>+<kbd>N</kbd> |Open a page to create a new record; the same way as choosing the **New** action. |
|<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>N</kbd> |Close a page and open a new one to create a new record; the same way as selecting the **OK & New** action. |
|<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>W</kbd> |Open the current card or document in a new window. For more information, see [Multitasking across multiple pages](ui-enter-data.md#multitasking-across-multiple-pages).|
|<kbd>Ctrl</kbd>+<kbd>Enter</kbd>|Save and close the page.|
|<kbd>Ctrl</kbd>+<kbd>Down Arrow</kbd>|Open the next record for an entity.|
|<kbd>Ctrl</kbd>+<kbd>Up Arrow</kbd> |Open the previous record for an entity.|
|<kbd>Ctrl</kbd>+<kbd>Insert</kbd> |Insert a new line in documents.|
|<kbd>Ctrl</kbd>+<kbd>Delete</kbd> |Delete the line, in documents, journals, and worksheets.|
|<kbd>Ctrl</kbd>+<kbd>F7</kbd>|Open ledger entries, logs entries, cost entries, and so on.|
|<kbd>Ctrl</kbd>+<kbd>F9</kbd>|Release document.|
|<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>F12</kbd> |Maximize the line items part on a document page. Select the keys again to return to the normal display. For more information, see [Focusing on Line Items](ui-enter-data.md#Focus).|
|<kbd>F6</kbd>|Move to the next Fast<kbd>Tab</kbd> or part (subpage).|
|<kbd>F7</kbd>|Open statistics.|
|<kbd>F9</kbd>|Post, issue, register, or reverse document.|
|<kbd>Shift</kbd>+<kbd>Ctrl</kbd>+<kbd>F9</kbd>|Post, print, and put away warehouse receipt.|
|<kbd>Shift</kbd>+<kbd>F6</kbd>|Move to previous Fast<kbd>Tab</kbd> or part (subpage).|
|<kbd>Shift</kbd>+<kbd>F9</kbd>|Post and print a document.|
|<kbd>Shift</kbd>+<kbd>F11</kbd>|Apply entries, get source documents, or get warehouse documents.|

## <a name="QuickEntry"></a>Quick entry shortcuts for fields

The following shortcuts pertain to the Quick Entry feature on cards, documents, and list pages. On lists, the shortcuts can't be used when the list is in the tile view. For more information about Quick Entry, see [Accelerating data entry using Quick Entry](ui-enter-data.md#QuickEntry).

|Select these keys<br />(in macOS)|To do this|Remarks|
|--------------------------------|----------|-------|
|<kbd>Enter</kbd>|Confirm the value in the current field and go to the next Quick Entry field.||
|<kbd>Shift</kbd>+<kbd>Enter</kbd>|Confirm the value in the current field and go to the previous Quick Entry field.||
|<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Enter</kbd>|Confirm the value in the current column and go to next Quick Entry field outside the list.<br /><br />This shortcut applies to embedded lists on a page, such as line items on a sales order. It enables you to quickly get out of the list and continue entering data in other fields on the page.|

## <a name="calendarshortcuts"></a> Keyboard shortcuts in the calendar (date picker)

When setting a date field, you can either enter the date manually or open a calendar (date picker) that lets you select the date you want. The following table describes the keyboard shortcuts for the calendar.

|Select these keys<br />(in macOS)|To do this|
|--------------------------------|----------|
|<kbd>Ctrl</kbd>+<kbd>Home</kbd>|Open the calendar if closed. **Note**: This doesn't work if the date field is in a grid, where <kbd>Ctrl</kbd>+<kbd>Home</kbd> jumps to the first row.|
|<kbd>Ctrl</kbd>+<kbd>Home</kbd><br /><br />(<kbd>Cmd</kbd>+<kbd>Home</kbd>)|Move to the current month, current day.|
|<kbd>Ctrl</kbd>+<kbd>Left Arrow</kbd><br /><br />(<kbd>Cmd</kbd>+<kbd>Left Arrow</kbd>)|Move to the previous day.|
|<kbd>Ctrl</kbd>+<kbd>Right Arrow</kbd><br /><br />(<kbd>Cmd</kbd>+<kbd>Right Arrow</kbd>)|Move to the next day.|
|<kbd>Ctrl</kbd>+<kbd>Up Arrow</kbd><br /><br />(<kbd>Cmd</kbd>+<kbd>Up Arrow</kbd>)|Move to the previous week, same day of the week.|
|<kbd>Ctrl</kbd>+<kbd>Down Arrow</kbd><br /><br />(<kbd>Cmd</kbd>+<kbd>Down Arrow</kbd>)|Move to the next week, same day of the week.|
|<kbd>Enter</kbd>|Select the focused date.|
|<kbd>Ctrl</kbd>+<kbd>End</kbd><br /><br />(<kbd>Cmd</kbd>+<kbd>End</kbd>)|Close the calendar and delete the current date.|
|<kbd>Esc</kbd>|Close the calendar without a selection, keep the current date.|
|<kbd>Page Down</kbd>|Move to the next month.|
|<kbd>Page Up</kbd>|Move to the previous month.|  

## Keyboard shortcuts in date fields

|Select these keys<br />(in macOS)|To do this|
|--------------------------------|----------|
|<kbd>t</kbd>|Enter the current date. "T" stands for "today".|
|<kbd>w</kbd>|Enter the work date. For more information, see [Work Date](ui-change-basic-settings.md#work-date)|

## <a name="reportpreviewshortcuts"></a>Keyboard shortcuts in the report preview

|Select these keys<br />(in macOS)|To do this|
|--------------------------------|----------|
|<kbd>Down Arrow</kbd>|Scroll down the page.|  
|<kbd>Up Arrow</kbd>|Scroll up the page.|
|<kbd>Ctrl</kbd>+<kbd>0</kbd> (zero)<br /><br />(<kbd>Cmd</kbd>+<kbd>0</kbd>)|Fits the entire page on the page. |
|<kbd>Ctrl</kbd>+<kbd>Home</kbd><br /><br />(<kbd>Cmd</kbd>+<kbd>Home</kbd>)|Go to the first page of the report.|
|<kbd>Ctrl</kbd>+<kbd>End</kbd><br /><br />(<kbd>Cmd</kbd>+<kbd>End</kbd>)|Go to the last page of the report.|
|<kbd><kbd>Left Arrow</kbd></kbd>|Scroll to the left when the page is zoomed in so that it isn't entirely in view. |
|<kbd>Right Arrow</kbd>|Scroll to the right when the page is zoomed in so that it isn't entirely in view. |
|<kbd>Page Down</kbd><br /><br />(<kbd>Fn</kbd>+<kbd>Down Arrow</kbd>)|Go to the next page of the report.|
|<kbd>Page Up</kbd><br /><br />(<kbd>Fn</kbd>+<kbd>Up Arrow</kbd>)|Go to the previous page of the report.|

## <a name="zoomshortcuts"></a>Keyboard shortcuts for zooming in and out

|Select these keys|To do this|
|--------------------------------|----------|
|<kbd>Ctrl</kbd>+<kbd>+</kbd>|Zoom in on the current page.|  
|<kbd>Ctrl</kbd>+<kbd>-</kbd>|Zoom out on the current page.|  
|<kbd>Ctrl</kbd>+<kbd>0</kbd>|Zoom in or out to 100% on the current page.|  

## <a name="roleexplorer"></a>Keyboard shortcuts for role explorer

Role explorer gives you an overview and quick access to all the business features that are available for your role. For more information, see [Finding pages with the Role Explorer](ui-role-explorer.md).

|Select these keys<br/>(in macOS)|To do this|
|--------------------------------|----------|
|<kbd>Shift</kbd>+<kbd>F12</kbd>|Open the role explorer.|
|<kbd>F3</kbd>|Open the **Find** box in role explorer for finding features based on a given search word or term.|
|<kbd>Shift</kbd> <kbd>F3</kbd> or <kbd>Ctrl</kbd>+<kbd>Down Arrow</kbd>|Moves focus to the next found feature in role explorer. <kbd>F3</kbd> will move focus to the **Find** box after the last found feature.|
|<kbd>Shift</kbd> <kbd>F3</kbd> or <kbd>Ctrl</kbd>+<kbd>Up Arrow</kbd>|Move focus to the previous found feature in role explorer.|
|<kbd>Ctrl</kbd>+<kbd>Shift</kbd>|Expand or collapse all subnodes, in addition to top-level nodes, when you choose the **Expand** or **Collapse** action.|

##  <a name="keypad"></a> Numeric keypad shortcuts

The following table describes the shortcuts on a numeric keypad.

|Select these keys<br/>(in macOS)|To do this|
|--------------------------------|----------|
|<kbd>Alt</kbd>+<kbd>Decimal Separator</kbd>|Switch the output of the decimal separator key to either a period (.) or the character determined by the **Region** setting of the **My Settings** page. For more information, see [Setting the decimal separator used by numeric keyboards](ui-enter-data.md#decimal).|


## Access keys for action bar and navigation menu

Access keys are keyboard shortcuts that can select specific actions on the action bar and navigation menu. It allows you to navigate through actions to get to the page you want. Access keys are available in the Business Central web client and are similar to access keys in Excel and Word Online.  

To use access keys on a page, first select the <kbd>Alt</kbd> key to display *key tips*, which are letters in small boxes next to the actions in the action bar and navigation menu. 

![Image that shows access keys on the customer list page.](media/access-keys.png) 

To select an action, select the key combination displayed in the key tip, for example <kbd>H</kbd> or <kbd>J</kbd>+<kbd>F</kbd>.
- If the action opens to a submenu of other actions, the keys tips for the submenu are shown, allowing you to continue using access keys if you like.
- If the action opens a different page, then key tips are turned off. To show them again, select <kbd>Alt</kbd> key. 
 
## See also

[Keyboard quick reference - PC Only](keyboard-shortcuts-cheatsheet.md)  
[Assistive features](ui-accessibility.md)  
[Getting ready for doing business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Frequently Asked Questions](across-faq.yml)  
[Find entries](ui-find-entries.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
