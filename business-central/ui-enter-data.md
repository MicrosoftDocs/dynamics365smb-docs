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
ms.date: 01/27/2020
ms.author: sgroespe
---

# Entering Data

There are many general features that help you enter data easier, faster, and more accurate. The general features for entering data are described in this article.  

The examples in this article use the demonstration data.

## Keyboard Shortcuts

There are several keyboard shortcuts that let you to work "mouse-free" and speed up your data entry, especially with large scale entries and repetitive typing tasks.

For more information about shortcuts, see [Keyboard Shortcuts](keyboard-shortcuts.md). A few of the shortcuts are discussed in this article.

## <a name="QuickEntry"></a>Accelerating Data Entry Using Quick Entry

Quick Entry is a feature designed for data entry when using the keyboard. Quick Entry works on fields (like on card pages) and in lists (rows and columns). It is beneficial when performing repetitive typing tasks that require creating multiple records in sequence, such as a batch of sales orders or registering new items.

You might already be familiar with using the Tab key to navigate from one field on a page to the next editable field. A disadvantage of using Tab is that it always goes sequentially to the next field. <!-- even if the field is non-editable or seldom filled it in.-->Quick Entry lets you change this path. With Quick Entry, you use the Enter key to navigate through only those fields that you are interested in, skipping non-editable fields and fields that you typically do not fill in. You might have already noticed this behavior on some pages. This is because the application already designates which fields to include when pressing Enter and which ones to skip. You can customize Quick Entry by personalizing your workspace and optimizing how you enter data on each page.

### How Quick Entry Works

Every field can be marked as either being *included in Quick Entry* or *excluded from Quick Entry*. Fields that are included in Quick Entry, will be included in the path when you press Enter; fields that are excluded from Quick Entry, will not.

When you are finished entering data in a field, you simply press Enter to confirm the changes and go to the next field. If you want to reverse direction, and go the previous field, press Shift+Enter. For more information about shortcuts, see [Quick Entry Shortcuts for Fields](keyboard-shortcuts.md#QuickEntry).

#### Tips and Tricks
The following provides some useful information about using Quick Entry.

- It is available for any editable fields.
- It also works across columns and rows.
- It does not prevent accessing other elements of a page, such as actions. These are still accessible by using Tab and Shift+Tab.  
- FastTabs do not have to be expanded for Quick Entry to work. If the next Quick Entry field is located in a collapsed FastTab, that FastTab will automatically expand and focus on the designated field.
- Quick Entry works irrespective of whether fields are mandatory. So it is a good idea to ensure that mandatory fields are included in Quick Entry.
- By default, most fields are automatically included in Quick Entry. So initially your task will most likely be excluding fields from Quick Entry.

### To change Quick Entry fields

To change which fields are included in or excluded from Quick Entry on a page, you use personalization.

1. Start personalization by selecting the ![Settings](media/ui-experience/settings_icon_small.png "Settings icon for role center") icon, and then the **Personalize** action.
2. Select a field that you want change, or in lists, select the corresponding column heading, and then choose either **Include in Quick Entry** or **Exclude from Quick Entry**.

For more information about personalization, see [Personalize Your Workspace](ui-personalization-user.md).

## Mandatory Fields

When you enter data on pages, certain fields are marked with a red asterisk. The red asterisk means that the field must be filled to complete a certain process that uses the field, such as posting a transaction that uses the value in the field.  

Even though the field contains a red asterisk, you are not forced to fill the field before you continue to other fields or close the page. The red asterisk only serves as a reminder that you will be blocked from completing a certain process.  

## Finding Data As You Type

 When you start to type characters in a field, a drop-down list is displayed and shows possible field values. The list changes as you type more characters, and you can select the correct value when it is displayed.  

 Many fields have a down arrow button that you can choose. You choose the arrow to get a list of data that is available to enter in the field. The button has two functions depending on the type of field:  

-   Lookup - Displays information from another table that you can enter in the field. You can select one piece of data at a time.  

-   Drop-down - Displays the set of options that exist for the field. You can select only one of the options.  

## Copying and Pasting FAQ Fields and Lines

You can copy one or more rows from a list or a single field on a page, and then paste what you copied into the same page, another page, or an external document (like Microsoft Excel and Outlook email). In short, to copy, you press CTRL+C (cmd+C in macOS) on your keyboard. To paste, you press CTRL+V (cmd+V in macOS).

In a list, to copy the field in the same column of the row above, and paste it into the current row, just press F8.

For more information, see [Copying and Pasting FAQ](ui-copy-paste.md).

## Filtering Line Items

To start filtering, select ![Filter pane icon](media/open-filter-pane-icon.png "Filter pane icon") at the top of the list or press Shift+F3 to open the filter pane. You work with the filter pane as you do on any other list. For more information, see [Filtering](ui-enter-criteria-filters.md#Filtering).

Filtering is especially helpful when viewing and analysing longer documents. For example, imagine you open a posted sales invoice and filter the line items to display all line items that have an individual discount above 5%, or filter to display only bike accessories with 'pro' in the name.

## <a name="Focus"></a>Focusing on Line Items

When working on documents that include a line items part, such as a sales order or invoice page, you can switch your view to focus only on the line items. The line items part then expands so that it occupies pretty much the entire workspace, hiding other parts of the page except the actions area at the top. This gives you a better overview of the lines items, and provides more room to work on them.

This is particularly beneficial when working with large line item lists and when fast data entry is desired. Another advantage is that it also provides advanced filtering capability, like on other lists, so browsing and searching through line items becomes even easier.

### Switching the Focus On and Off

To focus on lines items, select anywhere in the line item part, and then choose ![Focus Mode icon](media/focus-mode.png "Focus mode icon") in the upper right corner, or press Ctrl+Shift+F12.

To switch back to the normal view, choose ![Focus Mode icon](media/focus-mode.png "Focus mode icon") or press Ctrl+Shift+F12 again.

## Multitasking Across Multiple Pages
When working on multiple tasks at a time or when managing interruptions to the current task, such as taking an incoming call, you can open a card or document page in a new window. This allows you to keep a window open for an ongoing task while you start or complete another task in one or more other windows.

To open the current card or document in a new window, choose ![Open New Window](media/open-new-window-icon.png "Open new window icon") in the upper right corner, or press Alt+Shift+W.

> [!NOTE]
> When you open other pages from a card or document that is opened in a new window, those pages will open in a new window even though you do not choose ![Open New Window](media/open-new-window-icon.png "Open new window icon").

> [!NOTE]
> If you work in the Safari browser, a pop-up blocker may cause the new window to not open. If this is the case, specify the product URL as an allowed website. For information see, [Change preferences in Safari](https://go.microsoft.com/fwlink/?LinkId=2102965).<br /><br />
> The same may happen in other browsers, such as Firefox. For more information, see [Pop-up blocker settings in Firefox](https://go.microsoft.com/fwlink/?LinkId=2116400).  

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

You can enter dates and times in all the fields that are specifically assigned to dates (date fields). You can enter dates with or without separators.

> [!NOTE]  
> How you enter dates and times depends on your **Region** settings. For more information, see [Change Basic Settings](ui-change-basic-settings.md).  

### Entering Dates

For date fields, you can either use the data picker, which lets you select a date from a calender, or you can enter dates manually. This section provides a brief overview of how to enter dates. For more details, see [Working with Calendar Dates and Times](ui-enter-date-ranges.md).

For manually date entry, you can enter two, four, six, or eight digits:  

-   If you enter only two digits, this is interpreted as the day, and it will add the month and the year of the work date.  

-   If you enter four digits, this is interpreted as the day and the month, and it will add the year of the work date.  

-   If the date you want to enter is in the range 01/01/1930 through 12/31/2029, you can enter the year with two digits; otherwise, enter the year with four digits.  

You can also enter a date as a weekday followed by a week number and, optionally, a year (for example, Mon25 or mon25 means Monday in week 25).  

Instead of entering a specific date, you can enter one of these codes.  

|Code|Result|  
|--------------|----------------|  
|t|This specifies today's date (the system date for the computer).|  
|p|This specifies an accounting period, where p means the first accounting period, p2 means the second accounting period, and so on. |
|w|This specifies the work date that is setup in the application. To change the work date, see [Changing Basic Settings](ui-change-basic-settings.md). You may want to use a work date if you have many transactions with a date other than today's date.|
|c|This specifies that the date after c is a closing date, for example C123101.|  

## Entering Times

When you enter times, you can insert any separator sign that you want between the units, but it is not required. You do not have to write minutes, seconds, or AM/PM.  

The following table lists the various ways in which times can be entered and how they are interpreted.  

|Entry|Interpretation|  
|---------------|------------------------|  
|5|05:00:00|  
|5:30|05:30:00|  
|0530|05:30:00|  
|5:30:5|05:30:05|  
|053005|05:30:05|  
|5:30:5,50|05:30:05.5|  
|053005050|05:30:05.05|  

 You must enter two digits for each unit of time if you do not enter a separator.  

## Entering Datetimes

When you enter datetimes you must enter a space between the date and the time.  

The following table lists the various ways in which you can enter datetimes and how they are interpreted.  

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

 You can also enter a number and it is automatically converted to a duration. The number you enter is converted according to the default unit of measure that has been specified for the duration field.  

 To see what unit of measure is being used in a duration field, enter a number and see which unit of measure it is converted to.  

 The number 5 is converted to 5 hrs, if the unit of measure is hours.  

## See Also  
 [Sorting, Searching, and Filtering Lists](ui-enter-criteria-filters.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
