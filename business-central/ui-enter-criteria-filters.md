---
title: Sorting, Searching, and Filtering Lists
description: Work efficiently in lists by searching across your data, sorting columns, and refining results using filter symbols and keyboard shortcuts.
author: jswymer
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: delimit, FlowFilter, totals, limit, advanced
ms.search.form:
ms.date: 10/30/2023
ms.author: jswymer
---
# Sorting, Searching, and Filtering

There are a few things that you can do that will help you scan, find, and limit records on a list or in a report or XMLport. These include sorting, searching, and filtering. You can apply some or all of these simultaneously to quickly find or analyze your data.

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

For reports and XMLports, as on lists, you can set filters to delimit which data to include in the report or XMLport, but you can't sort and search.

> [!TIP]
> When viewing your data as tiles, you can search and use filtering. To use the full set of powerful features for sorting, searching, and filtering, choose the ![Show as list.](media/ui_show_as_list_icon.png "Show as list arrow left") icon to view the records as a list.

<!--
When you want to search for data, such as customer names, addresses, or product groups, you enter criteria. In search criteria, you can use all the numbers and letters that you normally use in the specific field. In addition, you can use special symbols to further filter the results. There are two ways to search: using the Quick Filter or column filters.
-->

## Sorting

Sorting makes it easy for you to get a quick overview of your data. For example, if you have many customers,  you could sort them by **Customer No.**, **Currency Code**, or **Country Region Code** to get the overview you need.

To sort a list, you can either:

- Choose a column heading text to toggle between ascending and descending order, or
- Choose the drop-down arrow in the column heading, then choose the **Ascending** or **Descending** action.  

> [!NOTE]  
> Sorting isn't supported on images, BLOB fields, FlowFilters, and fields that do not belong to a table.  

## Searching

<!--## Searching by using the Quick Filter -->
At the top of each list page, there's a ![Search list.](media/ui-search/search-list.png "Search list icon") **Search** action that provides a quick and easy way to reduce the records in a list and display only those records that contain the data that you're interested in seeing.

To search, just choose the **Search** action, and then in the box, type the text that you're looking for. You can enter letters, numbers, and other symbols.

In general, search will attempt to match text across all fields. It doesn't distinguish between uppercase and lowercase characters (case insensitive) and will match text placed anywhere in the field, at the beginning, end, or in the middle.

> [!TIP]
> You can select <kbd>F3</kbd> to activate and deactivate the search box. For more information, see [Keyboard Shortcuts](keyboard-shortcuts.md#KeyboardFilter).

> [!NOTE]  
> Search won't match values in images, BLOB fields, FlowFilters, FlowFields, and other fields that aren't part of a table.


### Fine-tuning the Search with Filter criteria

You can make a more exact search by using filter operators, expressions, and filter tokens. Unlike filtering, these are applied across all fields when used in the search box, making them less efficient than filtering.

- To find only field values that match the entire text and case exactly, place the search text between single quotes `''` (for example, `'man'`).

- To find field values that start with a certain text and match the case, place `*` after the search text (for example `man*`).

- To find field values that end with a certain text and match the case, place `*` before the search text (for example `*man`).

- When using  `''` or `*`, the search is case-sensitive. If you want to make the search case insensitive, place `@` before the search text (for example `@man*`).

The following table provides some examples to explain how you can use the search.

|Search Criteria|Finds...|
|---------------|----------|
|`man`<br />or <br />`Man`|All records with fields that contain the text **man**, regardless of the case. For example, **Manchester**, **manual**, or **Sportsman**. |
|`'Man'`|All records with fields that contain only **Man**, matching the case.|
|`Man*`|All records with fields that start with the text <b>Man</b>, matching the case. For example, **Manchester** but not **manual** or **Sportsman**.|
|`@Man*`|All records with fields that start with **man**, regardless of the case. For example, **Manchester** and **manual**, but not **Sportsman**.|
|`@*man`|All records that end with **man**, regardless of the case. For example **Sportsman**, but not **Manchester** or **manual**.|


## <a name="filtering"></a>Filtering

Filtering provides a more advanced and versatile way to control which records are included in a list, report, or XMLport. There are two major differences between searching and filtering, as described in the table below.

|| **Searching** | **Filtering** |
|--|----------|------------|
| **Applicable Fields** | Searches across all fields that are visible on the page. | Filters one or more fields individually, selecting from any field on the table, including fields that aren't visible on the page. |
| **Matching** | Displays records with fields that match the search text, no matter the text's case or placement in the field. | Displays records where the field exactly matches the filter, including the text's case, unless special filter symbols are entered.

Filtering enables you to display records for specific accounts or customers, dates, amounts, and other information by specifying filter criteria. Only records that match the criteria are displayed on the list or included in the report, batch job, or XMLport. If you specify criteria for multiple fields, then only records that match all criteria will be displayed.

For lists, the filters are displayed on a filter pane that appears to the left of the list when you activate it. For reports, batch jobs, and XMLports, the filters are visible directly on the request page.

### Filtering with Option Fields

For "ordinary" fields that hold data, setup date, or business data, you can set filters both by selecting data and by typing filter values, and you can use symbols to define advanced filter criteria. For more information, see [Entering Filter Criteria](ui-enter-criteria-filters.md#entering-filter-criteria).

For fields of type **Option**, however, you can only set a filter by selecting one or more options from a drop-down list of the available options. An example of an option field is the **Status** field on the **Sales Orders** page.

> [!NOTE]
> When you select multiple options as a filter value, the relationship between the options is defined as *OR*. For example, if you select both the **Open** and the **Released** check box in the **Status** filter field on the **Sales Orders** page, it means that sales orders that are either open or released are displayed.

### Setting Filters on Lists

On lists, you set filters by using the filter pane. To display the filter pane for a list, choose the drop-down arrow next to the name of the page, and then choose the **Show filter pane** action. Alternatively, select <kbd>Shift</kbd>+<kbd>F3</kbd>.

To display the filter pane for a column on a list, choose the drop-down arrow, and then choose the **Filter** action. Alternatively, select <kbd>Shift</kbd>+<kbd>F3</kbd>. The filter pane opens with the selected column shown as a filter field in the **Filter list by** section.

The filter pane displays the current filters for a list, and enables you to set your own custom filters on one or more fields by choosing the **+ Filter** action.

 A filter pane is divided in three sections: **Views**, **Filter list by**, and **Filter totals by**:

- **Views**

  Some lists include the **Views** section. Views are variations of the list that have been preconfigured with filters. You can define and save as many views as you want per list. The views will be available to you on any device you sign into. For more information, see [Save and Personalize List Views](ui-views.md).

- **Filter list by**

  This section is where you add filters on specific fields to reduce the number of displayed records. To add a filter, choose the **+ Filter** action. Then, type the name of the field that you want to filter the list by or pick a field from the drop-down list.

- **Filter totals by**

  Some lists that display calculated fields, such as amounts and quantities, will include the **Filter totals by** section where you can adjust various dimensions that influence calculations. To add a filter, choose the **+ Filter** action. Then, type the name of the field that you want to filter the list by or pick a field from the drop-down list.

  > [!NOTE]
  > Filters in the **Filter totals by** section are controlled by FlowFilters on the page design. For technical information, see [FlowFilters](/dynamics365/business-central/dev-itpro/developer/devenv-flowfilter-overview).

You can set a simple filter directly on a list within using the filter pane, namely a filter that displays only records with the same value as in the selected cell. Select a cell on the list, choose the drop-down arrow, and then choose the **Filter to This Value** action. Alternatively, select <kbd>Alt</kbd>+<kbd>F3</kbd>.

### Setting Filters in Reports, Batch Jobs, and XMLports

For reports and XMLports, the filters are visible directly on the request page. The request page displays the last used filters according to your selection in the **Use default values from** field. For more information, see [Use Saved Settings](ui-work-report.md#SavedSettings).

The main **Filter** section shows the default filter fields that you use to delimit which records to include in the report or XMLport. To add a filter, choose the **+ Filter** action. Then, type the name of the field that you want to filter by, or pick a field from the drop-down list.

In the **Filter totals by** section, you can adjust various dimensions that influence calculations in the report or XMLport. To add a filter, choose the **+ Filter** action. Then, type the name of the field that you want to filter by, or pick a field from the drop-down list.

## Entering Filter Criteria

Both in the filter pane and on a request page, you enter your filter criteria in the box under the filter field.

The type of the filter field determines which criteria you can enter. For example, filtering a field that has fixed values will only let you choose from those values. For more information about special filter symbols, see [Filter criteria](#FilterCriteria) and [Filter tokens](#FilterTokens).

Columns that already have filters are indicated by the ![Filter icon.](media/ui-search/filter-icon.png "Filter icon") icon in the column heading. To remove a filter, choose the drop-down arrow, and then choose the **Clear Filter** action.

> [!TIP]
> Accelerate finding and analyzing your data by using combinations of keyboard shortcuts. For example, select a field, use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>F3</kbd> to add that field to the filter pane, type the filter criteria, use <kbd>Ctrl</kbd>+<kbd>Enter</kbd> to return to the rows, select another field, and use <kbd>Alt</kbd>+<kbd>F3</kbd> to filter to that value. For more information, see [Keyboard Shortcuts](keyboard-shortcuts.md#KeyboardFilter).

### <a name="FilterCriteria"> </a>Filter Criteria and Operators

When you enter criteria, you can use all the numbers and letters that you normally use in the field. But there's also a set of special symbols that you can use as operators to further filter the results. The following sections describe these symbols and how to use them as operators in filters.

> [!TIP]
> For more information about filtering dates and times, see [Work with Calendar Dates and Times](ui-enter-date-ranges.md).

> [!IMPORTANT]
> - There may be situations where the value that you want to filter on contains a symbol that's an operator. For more information about handling these situtions, see [Filtering on Values That Contain Symbols](#symbols) for more instructions about handling this situation.
>
> - If there are more than 200 operators in a single filter, the system will automatically group some expressions in parentheses `()` for the purpose of processing. This has no effect on the filter or the results.  

#### (..) Interval

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`1100..2100`|Numbers 1100 through 2100|  
|`..2500`|Up to and including 2500|  
|`..12 31 00`|Dates up to and including 12 31 00|  
|`P8..`|Information for accounting period 8 and after|  
|`..23`|From the beginning date until 23-current month-current year 23:59:59|  
|`23..`|From 23-current month-current year 0:00:00 until the end of time|  
|`22..23`|From 22-current month-current year 0:00:00 until 23-current month-current year 23:59:59| 

> [!TIP]
> If you're using a numeric keypad, the decimal separator key may output a character other than a period (.). To switch to a period, select the <kbd>Alt</kbd>+<kbd>Decimal Separator</kbd> keys on the numeric keypad. When you want to switch back, select <kbd>Alt</kbd>+<kbd>Decimal Separator</kbd> again. For more information, see [Setting the decimal separator used by numeric keyboards](ui-enter-data.md#decimal).

#### (&#124;) Either/or

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`1200|1300`|Numbers with 1200 or 1300|  

#### (<>) Not equal to  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`<>0`|All numbers except 0<br /><br /> The SQL Server Option allows you to combine this symbol with a wild-card expression. For example, <>A* meaning not equal to any text that starts with A.|  

#### (>) Greater than  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`>1200`|Numbers greater than 1200|  

#### (>=) Greater than or equal to  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`>=1200`|Numbers greater than or equal to 1200|  

#### (<) Less than  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`<1200`|Numbers less than 1200|  

#### (<=) Less than or equal to  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`<=1200`|Numbers less than or equal to 1200|  

#### (&) And  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`>200&<1200`|Numbers greater than 200 and less than 1200|  

#### ('') An exact character match  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`'man'`|Text that matches **man** exactly and is case-sensitive.|  
|`''`|Text that is empty.|  

#### (@) Case insensitive  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`@man*`|Text that starts with **man** and is case insensitive.|  

#### (*) An indefinite number of unknown characters

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`*Co*`|Text that contains **Co** and is case-sensitive.|  
|`*Co`|Text that ends with **Co"** and is case-sensitive.|  
|`Co*`|Text that begins with **Co** and is case-sensitive.|  

#### (?) One unknown character  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`Hans?n`|Text such as **Hansen** or **Hanson**|  

#### Combined Format Expressions  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`5999|8100..8490`|Include any records with the number 5999 or a number from the interval 8100 through 8490.|  
|`..1299|1400..`|Include records with a number less than or equal to 1299 or a number equal to 1400 or greater (all numbers except 1300 through 1399).|  
|`>50&<100`|Include records with numbers that are greater than 50 and less than 100 (numbers 51 through 99).|  

### <a name="symbols"></a>Filtering on Values That Contain Symbols

There may be cases where field values contain the one of the following symbols:

- &
- (
- )
- =
- &#124;

If you want to filter on any of these symbols, place the filter expression in single quotes (`'<expression with symbol>'`). For example, if you wanted to filter on records that start with the text *J & V*, the filter expression would be `'J & V*'`.

This requirement isn't necessary for other symbols.

### <a name="FilterTokens"> </a>Filter Tokens

When entering filter criteria, you can also type words that have special meaning, called filter tokens. After entering the token word, the word is replaced by the value or values that it represents. Filter tokens make filtering easier by reducing the need to navigate to other pages to look up values you want to add to your filter. The tables below describe some of the tokens you can type as filter criteria.

> [!TIP]
> Your organization may use custom tokens. To learn about the complete set of tokens available to you or to add more custom tokens, talk to your administrator. For technical information see [Adding Filter Tokens](/dynamics365/business-central/dev-itpro/developer/devenv-adding-filter-tokens).

#### (%me or %userid) Records Assigned to You

Use `%me` or `%userid` when filtering fields that contain the user ID, such as **Assigned to User ID** field, to display all records that are assigned to you.

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`%me`<br />or<br />`%userid`|Records that are assigned to your user account. |  

#### (%mycustomers) Customers in My Customers

Use `%mycustomers` in the customer **No** field to display all records for customers that are included in the **My Customers** list on your Role Center.

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`%mycustomers`|Customers in the **My Customers** on your Role Center. |  

#### (%myitems) Items in My Items

Use `%myitems` in the item **No** field to display all records for items that are included in the **My Items** list on your Role Center.

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`%myitems`|Items in the **My Items** on your Role Center. |  

#### (%myvendors) Vendors in My Vendors

Use `%myvendors` in the vendor **No** field to display all records for vendors that are included in the **My Vendors** list on your Role Center.

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`%myvendors`|Vendors in the **My Vendors** on your Role Center. |  

## See also

[Searching and Filtering FAQ](ui-search-filter-faq.yml)  
[Save and Personalize List Views](ui-views.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
