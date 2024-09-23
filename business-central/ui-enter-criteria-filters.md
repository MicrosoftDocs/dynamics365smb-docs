---
title: Sorting, Searching, and Filtering Lists
description: Work efficiently in lists by searching across your data, sorting columns, and refining results using filter symbols and keyboard shortcuts.
author: jswymer
ms.author: jswymer
ms.topic: conceptual
ms.search.keywords: delimit, FlowFilter, totals, limit, advanced
ms.search.form:
ms.date: 02/20/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
ms.reviewer: jswymer
---
# Sorting, searching, and filtering data in lists, reports, or XMLports

There are a few things that you can do that help you scan, find, and limit records on a list or in a report or XMLport. These things include operations like sorting, searching, and filtering. You can apply some or all of these operations simultaneously to quickly find or analyze your data.

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

At the top of each list page, there's a ![Search list.](media/ui-search/search-list.png "Search list icon") **Search** icon that provides a quick and easy way to reduce the records in a list and display only those records that contain the data that you're interested in.

To search, select the **Search** icon or <kbd>F3</kbd> on your keyboard. In the box, type the text that you're looking for. You can enter letters, numbers, and other symbols.

![Shows search box](media/ui-search/search-list-box.png)

In general, search attempts to match text across all fields. It doesn't distinguish between uppercase and lowercase characters (case insensitive) and matches text placed anywhere in the field, at the beginning, end, or in the middle.

> [!NOTE]  
> Search won't match values in images, BLOB fields, FlowFilters, FlowFields, and other fields that aren't part of a table.

### Choose between modern search or legacy search

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner-section.md)]

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

On the most common pages, like **Customers**, **Contacts**, and **Items**, you can select  the down arrow in the **Search** box to choose between two search methods: **Use modern search** and **Use legacy search**:

![Show search box options for modern and legacy search](media/ui-search/search-modern-legacy-options.png)

*Legacy search* is the older search method, which is the only method available in Business Central 2024 release wave 1 and earlier. *Modern search* is a newer, faster, and more flexible search method.

A main difference between the two methods is that the legacy search finds only records that contain the exact search words in order you enter them. The modern search finds any records that contain the exact or approximate search words, regardless of the order you enter them.

For example, consider the item named **LONDON Swivel Chair, blue** in the CRONUS demonstration company. If you use the legacy search to search for `London chair`, it won't find anything, because `London chair` doesn't match any part of the actual name **LONDON Swivel Chair**. However, if you do the same search using modern search, it finds the item because it matched the word "London" and "chair".

As another example, suppose you want to find all blue chairs. With modern search, you can use `blue chair` or `chair blue`, which returns both **LONDON Swivel Chair, blue** and **TOKYO Guest Chair, blue** in the CRONUS demonstration company. Using the legacy search, you have to search for `chairs, blue`.  

Modern search also lets you enclose search word in quotes to narrow the results, similar to popular search engines. The search words `"blue chair"` returns no results because the item descriptions in the demonstration data are listed as "chair, blue", which is similar to the legacy search experience.

> [!NOTE]
> - Modern search only searches columns that are designed for modern search, which is determined by a developer. If you're having trouble finding data that you know exists, try using the legacy search.
>
>    Learn more about designing columns for modern search as a devloper at [Enable text search on table fields](/dynamics365/business-central/dev-itpro/developer/devenv-table-field-text-search).
>  
> - If the **Use modern search** option isn't available on a page, there are two possible reasons:
>   - Modern search isn't enabled for your enviroment. As an administrator, enable the **Use optimized text search in lists** feature in the **Feature Management** page. Learn more in [Enabling new and upcoming features ahead of time](admin-feature-management.md).
>   - The list doesn't include any columns that are designed for the modern search.
> - Modern search is the default method if it's enabled.

### Fine-tuning the search with filter criteria (legacy search only)

You can make a more exact search by using filter operators, expressions, and filter tokens. Unlike filtering, these are applied across all fields when used in the search box, making them less efficient than filtering.

- To find only field values that match the entire text and case exactly, place the search text between single quotes `''` (for example, `'man'`).

- To find field values that start with a certain text and match the case, place `*` after the search text (for example `man*`).

- To find field values that end with a certain text and match the case, place `*` before the search text (for example `*man`).

- When you use `''` or `*`, the search is case-sensitive. If you want to make the search case insensitive, place `@` before the search text (for example `@man*`).

The following table provides some examples to explain how you can use the search.

|Search Criteria|Finds...|
|---------------|----------|
|`man`<br />or <br />`Man`|All records with fields that contain the text **man**, regardless of the case. For example, **Manchester**, **manual**, or **Sportsman**. |
|`'Man'`|All records with fields that contain only **Man**, matching the case.|
|`Man*`|All records with fields that start with the text <b>Man</b>, matching the case. For example, **Manchester** but not **manual** or **Sportsman**.|
|`@Man*`|All records with fields that start with **man**, regardless of the case. For example, **Manchester** and **manual**, but not **Sportsman**.|
|`@*man`|All records that end with **man**, regardless of the case. For example **Sportsman**, but not **Manchester** or **manual**.|

## <a name="filtering"></a>Filtering

Filtering provides a more advanced and versatile way to control which records are included in a list, report, or XMLport. There are two major differences between searching and filtering, as described in the following table.

|| **Searching** | **Filtering** |
|--|----------|------------|
| **Applicable Fields** | Searches across all fields that are visible on the page. | Filters one or more fields individually, selecting from any field on the table, including fields that aren't visible on the page. |
| **Matching** | Displays records with fields that match the search text, no matter the text's case or placement in the field. | Displays records where the field exactly matches the filter, including the text's case, unless special filter symbols are entered.

Filtering enables you to display records for specific accounts or customers, dates, amounts, and other information by specifying filter criteria. Only records that match the criteria are displayed on the list or included in the report, batch job, or XMLport. If you specify criteria for multiple fields, then only records that match all criteria are displayed.

For lists, the filters are displayed on a filter pane that appears to the left of the list when you activate it. For reports, batch jobs, and XMLports, the filters are visible directly on the request page.

### Filtering with option fields

For "ordinary" fields that hold data, setup date, or business data, you can set filters both by selecting data and by typing filter values, and you can use symbols to define advanced filter criteria. Learn more in [Entering Filter Criteria](ui-enter-criteria-filters.md#entering-filter-criteria).

For fields of type **Option**, however, you can only set a filter by selecting one or more options from a drop-down list of the available options. An example of an option field is the **Status** field on the **Sales Orders** page.

> [!NOTE]
> When you select multiple options as a filter value, the relationship between the options is defined as *OR*. For example, if you select both the **Open** and the **Released** check box in the **Status** filter field on the **Sales Orders** page, it means that sales orders that are either open or released are displayed.

### Setting filters on lists

On lists, you set filters by using the filter pane. To display the filter pane for a list, choose the drop-down arrow next to the name of the page, and then choose the **Show filter pane** action. Alternatively, select <kbd>Shift</kbd>+<kbd>F3</kbd>.

To display the filter pane for a column on a list, choose the drop-down arrow, and then choose the **Filter** action. Alternatively, select <kbd>Shift</kbd>+<kbd>F3</kbd>. The filter pane opens with the selected column shown as a filter field in the **Filter list by** section.

The filter pane displays the current filters for a list, and enables you to set your own custom filters on one or more fields by choosing the **+ Filter** action.

 A filter pane is divided in three sections: **Views**, **Filter list by**, and **Filter totals by**:

- **Views**

  Some lists include the **Views** section. Views are variations of the list that are preconfigured with filters. You can define and save as many views as you want per list. The views are available to you on any device you sign into. Learn more in [Save and Personalize List Views](ui-views.md).

- **Filter list by**

  This section is where you add filters on specific fields to reduce the number of displayed records. To add a filter, choose the **+ Filter** action. Then, type the name of the field that you want to filter the list by or pick a field from the drop-down list.

- **Filter totals by**

  Some lists that display calculated fields, such as amounts and quantities, include the **Filter totals by** section where you can adjust various dimensions that influence calculations. To add a filter, choose the **+ Filter** action. Then, type the name of the field that you want to filter the list by or pick a field from the drop-down list.

  > [!NOTE]
  > Filters in the **Filter totals by** section are controlled by FlowFilters on the page design. Learn the technical aspect of FlowFilters at [FlowFilters](/dynamics365/business-central/dev-itpro/developer/devenv-flowfilter-overview).

You can set a simple filter directly on a list within using the filter pane, namely a filter that displays only records with the same value as in the selected cell. Select a cell on the list, choose the drop-down arrow, and then choose the **Filter to This Value** action. Alternatively, select <kbd>Alt</kbd>+<kbd>F3</kbd>.

### Setting filters in reports, batch jobs, and XMLports

For reports and XMLports, the filters are visible directly on the request page. The request page displays the last used filters according to your selection in the **Use default values from** field. Learn more in [Use Saved Settings](ui-work-report.md#SavedSettings).

The main **Filter** section shows the default filter fields that you use to delimit which records to include in the report or XMLport. To add a filter, choose the **+ Filter** action. Then, type the name of the field that you want to filter by, or pick a field from the drop-down list.

In the **Filter totals by** section, you can adjust various dimensions that influence calculations in the report or XMLport. To add a filter, choose the **+ Filter** action. Then, type the name of the field that you want to filter by, or pick a field from the drop-down list.

## Entering filter criteria

Both in the filter pane and on a request page, you enter your filter criteria in the box under the filter field.

The type of the filter field determines which criteria you can enter. For example, filtering a field with fixed values only lets you choose from those values. Learn more information about special filter symbols in [Filter criteria](#FilterCriteria) and [Filter tokens](#FilterTokens).

Columns that already have filters are indicated by the ![Filter icon.](media/ui-search/filter-icon.png "Filter icon") icon in the column heading. To remove a filter, choose the drop-down arrow, and then choose the **Clear Filter** action.

> [!TIP]
> Accelerate finding and analyzing your data by using combinations of keyboard shortcuts. For example, select a field, use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>F3</kbd> to add that field to the filter pane, type the filter criteria, use <kbd>Ctrl</kbd>+<kbd>Enter</kbd> to return to the rows, select another field, and use <kbd>Alt</kbd>+<kbd>F3</kbd> to filter to that value. Learn more in [Keyboard Shortcuts](keyboard-shortcuts.md#KeyboardFilter).

### <a name="FilterCriteria"> </a>Filter criteria and operators

When you enter criteria, you can use all the numbers and letters that you normally use in the field. But there's also a set of special symbols that you can use as operators to further filter the results. The following sections describe these symbols and how to use them as operators in filters.

> [!TIP]
> Learn more about filtering dates and times in [Work with Calendar Dates and Times](ui-enter-date-ranges.md).

> [!IMPORTANT]
> - There may be situations where the value that you want to filter on contains a symbol that's an operator. Learn more about handling these situations in [Filtering on Values That Contain Symbols](#symbols).
>
> - If there are more than 200 operators in a single filter, the system will automatically group some expressions in parentheses `()` for the purpose of processing. This has no effect on the filter or the results.  

#### (..) Interval

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`1100..2100`|Numbers 1100 through 2100|  
|`..2500`|Up to and including 2500|  
|`..12 31 00`|Dates up to and including 12 31 00|  
|`Bicycle..Car`| Strings Bicycle through Car when ordered lexiographically|  
|`P8..`|Information for accounting period 8 and after|  
|`..23`|From the beginning date until 23-current month-current year 23:59:59|  
|`23..`|From 23-current month-current year 0:00:00 until the end of time|  
|`22..23`|From 22-current month-current year 0:00:00 until 23-current month-current year 23:59:59| 

> [!TIP]
> If you're using a numeric keypad, the decimal separator key may output a character other than a period (.). To switch to a period, select the <kbd>Alt</kbd>+<kbd>Decimal Separator</kbd> keys on the numeric keypad. When you want to switch back, select <kbd>Alt</kbd>+<kbd>Decimal Separator</kbd> again. Learn more in [Setting the decimal separator used by numeric keyboards](ui-enter-data.md#decimal).

> [!NOTE]  
> If the field that you filter on is of type Text, then lexiographic ordering is used to determine what's included in the interval. For such fields that are used to store integers, this can lead to the (unexpected) result that a filter on 10000..10042 also includes values 100000 and 1000042.

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

#### Combined format expressions  

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`5999|8100..8490`|Include any records with the number 5999 or a number from the interval 8100 through 8490.|  
|`..1299|1400..`|Include records with a number less than or equal to 1299 or a number equal to 1400 or greater (all numbers except 1300 through 1399).|  
|`>50&<100`|Include records with numbers that are greater than 50 and less than 100 (numbers 51 through 99).|  

### <a name="symbols"></a>Filtering on values that contain symbols

There might be cases where field values contain the one of the following symbols:

- &
- (
- )
- =
- &#124;

If you want to filter on any of these symbols, place the filter expression in single quotes (`'<expression with symbol>'`). For example, if you wanted to filter on records that start with the text *J & V*, the filter expression would be `'J & V*'`.

This requirement isn't necessary for other symbols.

### <a name="FilterTokens"> </a>Filter tokens

When entering filter criteria, you can also type words that have special meaning, called filter tokens. After entering the token word, the word is replaced by the value or values that it represents. Filter tokens make filtering easier by reducing the need to navigate to other pages to look up values you want to add to your filter. The following tables describe some of the tokens you can type as filter criteria.

> [!TIP]
> Your organization may use custom tokens. To learn about the complete set of tokens available to you or to add more custom tokens, talk to your administrator. Learn the technical aspect of filter tokens at [Adding Filter Tokens](/dynamics365/business-central/dev-itpro/developer/devenv-adding-filter-tokens).

#### (%me or %user) Records assigned to you

Use `%me` or `%user` when filtering fields that contain the user ID, such as **Assigned to User ID** field, to display all records that are assigned to you.

|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|`%me`<br />or<br />`%user`|Records that are assigned to your user account. |  

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

## Related information

[Searching and Filtering FAQ](ui-search-filter-faq.yml)  
[Save and Personalize List Views](ui-views.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Keyboard Shortcuts](keyboard-shortcuts.md#KeyboardFilter)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
