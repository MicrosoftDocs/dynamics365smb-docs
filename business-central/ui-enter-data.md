---
title: How to Enter Data in Business Central| Microsoft Docs
description: Learn about general features that help you enter data in fields.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 04/03/2020
ms.author: sgroespe
---

# Entering Data

There are many general features that help you enter data easier, faster, and more precise. The basic principles and advanced features for entering data are described in this article.  

The examples in this article use the demonstration data.

## Working with editable fields
Fields in [!INCLUDE[d365fin](includes/d365fin_md.md)] may contain different editable data, such as text or currency amounts. Editable fields typically display an input box where you can type or choose a value. Non-editable fields are typically displayed with a gray background.   

Some editable fields provide a picker to help you specify a value.  

<!-- TODO: Add illustrations or images of each picker -->
|**Picker**        |**How it helps you specify a value**|
|------------------|------------------------------------|
|Date picker       |This picker displays a calendar that is based on your current regional settings. It helps you choose a single date.|
|Dropdown          |Dropdowns provide a choice of fixed values or reference records from another table|
|Switch or Checkbox|Some fields provide a simple choice of *Yes* or *No* values. The switch is used to specify this value, and is always displayed as a checkbox in lists|
|Assist edit       |Some fields provide custom pickers that are suited to looking up and choosing the best value for that field, such as popup window|


### Modifying a field value

To modify the value of a field, you must first set focus to that field. You set focus by doing the following actions:

- Use the **Tab** key. The action selects the entire value.
- Left-click your mouse or similar input device. This action will only select the entire field value if the field is in a list.  

When you interact with fields in the user interface, [!INCLUDE[d365fin](includes/d365fin_md.md)] typically favors selecting the entire field value to make it easier for you to replace that value.

When the entire field value is selected:
- Replace the value by just typing to specify a new value. If the field offers a picker, you can activate it using the **Alt+Arrow-down** keyboard shortcut.
- Use the **Delete** or **Backspace** key to clear the value.

Press the **F2** key to toggle between selecting the entire field value or placing the cursor after the field's value. Placing the cursor at the end of the value makes it easier for you to append to the existing value.

When the cursor is shown at the end of the field value:
- Add to the value by just typing.
- Use the **Home**, **End**, **Left-arrow**, and **Right-arrow** keys to move the cursor within the value. If you're editing a field in a list, pressing the **Left-arrow** key again when the cursor is at the beginning of the value will set focus to the previous field. Similarly, pressing the **Right-arrow** key again when the cursor is at the end of the value will set focus to the next field.

> [!NOTE]
> After you specify a value, Business Central will only check that it's valid after you click outside the field or set focus to another element, such as the next field.  


## Keyboard Shortcuts

There are several keyboard shortcuts that let you work "mouse-free" and speed up your data entry. These keyboard shortcuts are especially useful with large-scale entries and repetitive typing tasks.

For more information about shortcuts, see [Keyboard Shortcuts](keyboard-shortcuts.md). A few of the keyboard shortcuts are discussed in this article.

## <a name="QuickEntry"></a>Accelerating Data Entry Using Quick Entry

Quick Entry is a feature designed for data entry when using the keyboard. Quick Entry works on fields (like on card pages) and in lists (rows and columns). It's beneficial when doing repetitive typing tasks that require creating multiple records in sequence. Examples include a batch of sales orders or registering new items.

You can use the Tab key to navigate from one field on a page to the next editable field. A disadvantage of using Tab is that it always goes sequentially to the next field. <!-- even if the field is non-editable or seldom filled it in.-->Quick Entry lets you change this path. With Quick Entry, you use the Enter key to navigate through only those fields that you're interested in. Quick Entry skips non-editable fields and fields that you typically don't fill in. You might have already noticed this behavior on some pages. This behavior is because the fields to include when pressing Enter and which ones to skip have been predefined. You can customize Quick Entry by personalizing your workspace and optimizing how you enter data on each page.

### How Quick Entry Works

Every field can be marked as either *included in Quick Entry* or *excluded from Quick Entry*. Fields that are included in Quick Entry will be included in the path when you press Enter. Fields that are excluded from Quick Entry won't.

When you're finished entering data in a field, you simply press Enter to confirm the changes and go to the next field. If you want to reverse direction, and go the previous field, press Shift+Enter. For more information about shortcuts, see [Quick Entry Shortcuts for Fields](keyboard-shortcuts.md#QuickEntry).

#### Tips and Tricks

The following list provides some useful information about using Quick Entry.

- It's available for any editable fields.
- It also works across columns and rows.
- It doesn't prevent accessing other elements of a page, such as actions. These elements are still accessible by using Tab and Shift+Tab.  
- It's not required that FastTabs are expanded for Quick Entry to work. If the next Quick Entry field is located in a collapsed FastTab, that FastTab will automatically expand and focus on the chosen field. [!INCLUDE[d365fin](includes/d365fin_md.md)] will remember that the FastTab should be expanded next time you visit the page.  
- Quick Entry works no matter whether fields are mandatory. So it's a good idea to ensure that mandatory fields are included in Quick Entry.
- By default, most fields are automatically included in Quick Entry. So initially your task will most likely be excluding fields from Quick Entry.

### To change Quick Entry fields

To set up Quick Entry on fields, you use personalization.

1. Start personalization by selecting the ![Settings](media/ui-experience/settings_icon_small.png "Settings icon for role center") icon, and then the **Personalize** action.
2. Select a field that you want change. In lists, select the corresponding column heading. Then, choose either **Include in Quick Entry** or **Exclude from Quick Entry**.

For more information about personalization, see [Personalize Your Workspace](ui-personalization-user.md).

## Mandatory Fields

When you enter data on pages, certain fields are marked with a red asterisk. The red asterisk means that the field must be filled to complete a certain process. An example is when you post a transaction that uses the value in the field.  

Although a field is mandatory, you aren't forced to fill the field before you continue to other fields or close the page. The red asterisk only serves as a reminder that you'll be blocked from completing a certain process.  

## Finding Data As You Type

 When you start to type characters in a field, a drop-down list is displayed and shows possible field values. The list changes as you type more characters, and you can select the correct value when it's displayed.  

 Many fields have a down arrow button that you can choose. You choose the arrow to get a list of data that is available to enter in the field. The button has two functions depending on the type of field:  

-   Lookup - Displays information from another table that you can enter in the field. You can select one piece of data at a time.  

-   Drop-down - Displays the set of options that exist for the field. You can select only one of the options.  

## Copying and Pasting FAQ Fields and Lines

You can copy one or more rows from a list or a single field on a page. Then paste what you copied into the same page, another page, or an external document. You could, for example, paste to Microsoft Excel or Outlook email. In short, to copy, press CTRL+C (cmd+C in macOS) on your keyboard. To paste, press CTRL+V or cmd+V in macOS.

In a list, to copy the field in the same column of the row above, and paste it into the current row, just press F8.

For more information, see [Copying and Pasting FAQ](ui-copy-paste.md).

## Filtering Line Items

To start filtering, select ![Filter pane icon](media/open-filter-pane-icon.png "Filter pane icon") at the top of the list or press Shift+F3 to open the filter pane. You work with the filter pane as you do on any other list. For more information, see [Filtering](ui-enter-criteria-filters.md#filtering).

Filtering is especially helpful when viewing and analyzing longer documents. Imagine you open a posted sales invoice. Then, you filter the line items to display all line items that have an individual discount above 5%. Or, you filter to display only bike accessories with 'pro' in the name.

## <a name="Focus"></a>Focusing on Line Items

When working on documents that include a line items part, you can switch your view to focus only on the line items. Example documents are sales order or invoice page. The line items part expands so that it occupies almost the entire workspace. It hides other parts of the page except the actions area at the top. This layout gives you a better overview of the lines items, and provides more room to work on them.

You'll benefit particularly when you work with large line item lists and you want to enter data fast. This feature also provides advanced filtering capability. Like on other lists, browsing and searching through line items becomes even easier.

### Switching the Focus On and Off

To focus on lines items, select anywhere in the line item part, and then choose ![Focus Mode icon](media/focus-mode.png "Focus mode icon") in the upper right corner, or press Ctrl+Shift+F12.

To switch back to the normal view, choose ![Focus Mode icon](media/focus-mode.png "Focus mode icon") or press Ctrl+Shift+F12 again.

## Multitasking Across Multiple Pages

You can open a card or document page in a new window. Opening a new window lets you:

- Work on multiple tasks at the same time
- Manage interruptions to the current task, such as taking an incoming call.
- Keep a window open for an ongoing task while you start or complete another task in windows.

To open the current card or document in a new window, choose ![Open New Window](media/open-new-window-icon.png "Open new window icon") in the upper right corner, or press Alt+Shift+W.

<!--
When working on multiple tasks at a time or when managing interruptions to the current task, such as taking an incoming call, you can open a card or document page in a new window. This allows you to keep a window open for an ongoing task while you start or complete another task in one or more other windows.
-->
To open the current card or document in a new window, choose ![Open New Window](media/open-new-window-icon.png "Open new window icon") in the upper right corner, or press Alt+Shift+W.

> [!NOTE]
> When you open other pages from a card or document that is opened in a new window, those pages will open in a new window even though you don't choose ![Open New Window](media/open-new-window-icon.png "Open new window icon").

> [!NOTE]
> If you work in the Safari browser, a pop-up blocker may cause the new window to not open. If this is the case, specify the product URL as an allowed website. For information see, [Change preferences in Safari](https://go.microsoft.com/fwlink/?LinkId=2102965).<br /><br />
> The same may happen in other browsers, such as Firefox. For more information, see [Pop-up blocker settings in Firefox](https://go.microsoft.com/fwlink/?LinkId=2116400).  

Another way to multitask, is to open [!INCLUDE[d365fin](includes/d365fin_md.md)] on two or more browser tabs. When you do it this way, you should create a new tab and then copy/paste the URL of the original tab into the new tab. This way creates a new session.   

> [!NOTE]
> Don't use the **Duplicate** function of the browser to create the new tab as this may cause actions on one tab to block actions on other tabs because they are part of the same session.

## Entering Quantities by Calculation

When entering numbers into quantity fields, such as the **Quantity** field on an item journal line, you can enter the formula instead of the sum quantity.  

### Examples  

-   If you enter 19+19, the field is calculated to 38.  

-   If you enter 41-9, the field is calculated to 32.  

-   If you enter 12*4, the field is calculated to 48.  

-   If you enter 12/4, the field is calculated to 3.  

## Entering Negative Numbers

You can enter negative numbers in two ways. The number -20.5 can be entered as:  

-   -20.5  

    or
-   20.5-  

 In both cases, the amount will be recorded in as -20.5.  

 If the last character of the expression is a **+** or a **-**, the entire expression will be recorded with that sign. An example, **10-20+** will result in 10 and not -10.  

## Entering Dates and Times

You can enter dates and times in all the fields that are assigned to dates (date fields). You can enter dates with or without separators.

> [!NOTE]  
> How you enter dates and times depends on your **Region** settings. For more information, see [Change Basic Settings](ui-change-basic-settings.md).  

### Entering Dates

You can either use the data picker to select a date from a calendar, or you can enter dates manually. This section provides a brief overview of how to enter dates. For more information, see [Working with Calendar Dates and Times](ui-enter-date-ranges.md).

For manually date entry, you can enter two, four, six, or eight digits:  

-   Two digits are interpreted as the day. It will add the month and the year of the work date.  

-   Four digits are interpreted as the day and the month. It will add the year of the work date.  

-   If the date you want is in the range 01/01/1930 through 12/31/2029, enter the year with two digits. Otherwise, enter the year with four digits.  

You can also enter a date as a weekday followed by a week number. Or, you can enter a year. For example, Mon25 or mon25 means Monday in week 25.  

Instead of entering a specific date, you can enter one of these codes.  

|Code|Result|  
|--------------|----------------|  
|t|Specifies today's date (the system date for the computer).|  
|p|Specifies an accounting period, where p means the first accounting period, p2 means the second accounting period, and so on. |
|w|Specifies the work date that is set up in the application. To change the work date, see [Changing Basic Settings](ui-change-basic-settings.md). You may want to use a work date if you have many transactions with a date other than today's date.|
|c|Specifies that the date after c is a closing date, for example C123101.|  

## Entering Times

When you enter times, you can insert any separator sign that you want between the units, but it isn't required. You don't have to write minutes, seconds, or AM/PM.  

The following table lists the various ways in which times can be entered and how they're interpreted.  

|Entry|Interpretation|  
|---------------|------------------------|  
|5|05:00:00|  
|5:30|05:30:00|  
|0530|05:30:00|  
|5:30:5|05:30:05|  
|053005|05:30:05|  
|5:30:5,50|05:30:05.5|  
|053005050|05:30:05.05|  

 You enter two digits for each unit of time if you don't enter a separator.  

## Entering Datetimes

When you enter datetimes, you must enter a space between the date and the time.  

The following table lists the various ways in which you can enter datetimes and how they're interpreted.  

|Entry|Interpretation|  
|---------------|------------------------|  
|`131202` 132455|13-12-02 13:24:55|  
|1-12-02 10|01-12-02 10:00:00|  
|1.12.02 5|01-12-02 05:00:00|  
|1.12.02|01-12-02 00:00:00|  
|11 12|11-current month-current year 12:00:00|  
|1112 12|11-12-current year 12:00:00|  
|t or today|today's date 00:00:00|  
|t time|today's date actual time|  
|t 10:30|today's date 10:30:00|  
|t 3:3:3|today's date 03:03:03|  
|w or workdate|the working date 00:00:00|  
|m or Monday|Monday of the current week 00:00:00|  
|tu or Tuesday|Tuesday of the current week 00:00:00|  
|we or Wednesday|Wednesday of the current week 00:00:00|  
|th or Thursday|Thursday of the current week 00:00:00|  
|f or Friday|Friday of the current week 00:00:00|  
|s or Saturday|Saturday of the current week 00:00:00|  
|su or Sunday|Sunday of the current week 00:00:00|  
|tu 10:30|Tuesday of the current week 10:30:00|  
|tu 3:3:3|Tuesday of the current week 03:03:03|  

## Entering Duration

You enter a duration as a number followed by its unit of measure.  

Here are some examples.  

|Duration|Unit of measure**|  
|------------------|-------------------------|  
|2h|2 hrs|  
|6h 30 m|6 hrs 30 mins|  
|6.5h|6 hrs 30 mins|  
|90m|1 hr 30 mins|  
|2d 6h 30m|2 days 6 hrs 30 mins|  
|2d 6h 30m 56s 600ms|2 days 6 hrs 30 mins 56 secs 600 msecs|  

 You can also enter a number and it's automatically converted to a duration. The number you enter is converted according to the default unit of measure that has been specified for the duration field.  

 To see the unit of measure used in a duration field, enter a number and see which unit of measure it's converted to.  

 The number 5 is converted to 5 hrs, if the unit of measure is hours.  

## See Also  
 [Sorting, Searching, and Filtering Lists](ui-enter-criteria-filters.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
