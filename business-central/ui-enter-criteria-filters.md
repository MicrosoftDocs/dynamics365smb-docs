---
title: Searching Data and Entering Filter Criteria | Microsoft Docs
description: Describes how to work with filters, such as the Quick Filter, to refine the results you get when you search for data.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: delimit, FlowFilter
ms.date: 07/17/2018
ms.author: jswymer

---
# Sorting, Searching, and Filtering Lists
There are a few things that you can do that will help you scan, find, and limit records in a list. These include sorting, searching and filtering.

<!-- 
When you want to search for data, such as customer names, addresses, or product groups, you enter criteria. In search criteria you can use all the numbers and letters that you normally use in the specific field. In addition, you can use special symbols to further filter the results. There are two ways to search: using the Quick Filter or column filters.
-->

## Sorting
Sorting makes it easy for you to get a quick overview of your data. If you have many customers, for example, you can choose to sort them by **Customer No.**, **Customer Posting Group**, **Currency Code**, **Country Region Code**, or **Sales Tax Registration No.** to get the overview you need.

To sort a list, you can either choose a column heading text to toggle between ascending and descending order, or choose the small down arrow in the column heading, and then choose **Ascending** or **Descending**.  

> [!NOTE]  
>   Sorting is not supported images, BLOB fields, FlowFilters, and fields that do not belong to a table.  

## Searching
<!--## Searching by using the Quick Filter -->
At the top of each list page, there is a ![Search list](media/ui-search/search-list.png "Search list icon") **Search** icon that provides a quick and easy way to reduce the records in a list and display only those records that contain the data that you are interested in seeing.

To search, simply select the search icon, and then in the box, type the text that you are looking for. You can enter letters, numbers, and characters.

### Fine-tune the search
In general, search goes across all columns in all rows to find fields that include the text that you provide. It does not distinguish between uppercase and lowercase characters (in other words, case insensitive). 

But there are a few special characters that you can use to make a more exact search: 

- To find only field values that match the entire text and case exactly, place the search text between single quotes `''` (for example, `'man'`).  
- To find field values that start with a certain text and match the case, place `*` after the search text (for example `man*`). 
- To find field values that end with a certain text and match the case, place `*` before the search text (for example `*man`). 
- When using these special characters, if you want to make the search case insensitive, place **@** before the search text (for example `@man*`). 

The following table explains the search by giving you examples.
   

<!--
In search criteria you can use all the numbers and letters that you normally use in the specific field. In addition, you can use special symbols to further filter the results. There are two ways to search: using the Quick Filter or column filters.-->

<!--
The Quick Filter provides an easy access to filter data by entering plain text, but does also provide a lot of search criteria options. Depending on whether you enter plain text or text including symbols, the Quick Filter behaves differently.  

* If you enter plain text in the search criteria, the search criteria is interpreted as a case insensitive search that contains certain text.  
* If you enter text including symbols in the search criteria, the search criteria is interpreted exactly as you entered it, and the search is case sensitive.
-->
<!--

|Search Criteria|Interpreted as...|Finds...|
|---------------|----------------|----------|
|`man`<br />or <br />`Man`|Contains the text; case insensitive|All records with fields that contain the text **man**, regardless of the case.|
|`'Man'`|Entire text match; case sensitive.|All records with fields that only contain **Man** exactly.|
|`Man*`|Starts with the text; case sensitive.|All records with fields that start with the text <b>Man</b> exactly.|
|`@Man*`|Starts with the text; case insensitive.|All records with fields that start with **man**, regardless of the case.|
|`@*man`|Ends with the text; case insensitive.|All records that end with **man**, regardless of the case.|
-->

|Search Criteria|Finds...|
|---------------|----------|
|`man`<br />or <br />`Man`|All records with fields that contain the text **man**, regardless of the case. For example, **Manchester**, **manual**, or **Sportsman**. |
|`'Man'`|All records with fields that contain only **Man**, matching the case.|
|`Man*`|All records with fields that start with the text <b>Man</b>, matching the case. For example, **Manchester** but not **manual** or **Sportsman**.|
|`@Man*`|All records with fields that start with **man**, regardless of the case. For example, **Manchester** and **manual**, but not **Sportsman**.|
|`@*man`|All records that end with **man**, regardless of the case. For example **Sportsman**, but not **Manchester** or **manual**.|

## Filtering
Filtering provides an more advanced and versatile way of controlling which records display in a list. Unlike search, which works across columns, filtering is column-based. It enables you to display records for specific accounts or customers, dates, amounts, and other information by specifying criteria for fields of a column. Only records that match the criteria are displayed. If you specify criteria for multiple fields, then records must match all criteria will be displayed.

### Add filters on fields

1.  Before you add filters, choose ![Show as list](media/ui_show_as_list_icon.png "Show as list arrow left") icon to change to the list view.
2. To add a filter, do one of the following:
    - Move focus to a field that contains a value that you want to filter on. Go to the column heading, choose the down arrow, and then **Filter on This Value**.

      This will display only records that have the same value as the focused field. 

    - In a column heading, choose the down arrow, and then choose **Filter...**.

      This will open the filter pane on the left, where you can add the filter criteria for the field associated with the column. For more information, see [Filter citeria](#FilterCriteria).

    - If the list is displayed with the Role Center, choose the down arrow near the page title in the navigation bar above the list, and then choose **Show filter pane**.

      ![Show filter pane](media/open-filter-pane.png "Show filter pane")

3. In the filter pane, enter the filter criteria the field box that displays or choose **Filter...** to add a new filter on a field. 

> [!TIP]
> Columns that aready have filters are indicated by the ![Filter icon](media/ui-search/filter-icon.png "Filter icon") in the column heading. To remove a filter, select the columns heading, then choose **Clear Filter**.

### Working in the filter pane
The filter pane enables you to set filters on one or more fields. The following figure shows an example filter pane for a Sales Quotes lis

![Filter pane overview ](media/filter-pane-overview.png "Filter icon")

A filter pane is divided in three areas: **Views**, **Filter list by**, and Filter total by.

- **Views**

  Views are variations of the list that have been preconfigured with filters. To switch the view, simply select another link. You can temporarily change the filters on a view, but the changes will not be saved.

- **Filter list by**

  The **Filter list by** section is where you add filters on specific fields. To add a filter, select **+ Filter...**, select the field that you want to filter, and then add the filter criteria in the box.

- **Filter totals by**

  The **Filter totals by** section enables you to filter on 





<!-- 
### Tips for improving filter results

To improve your filter results, consider the following strategies:

- Understand where and how filters persist. Filters are page dependent. If you apply a filter on one list and switch to a different list, then the filter is not applied there. The filter persists on the list where you set it until you clear it or specify new criteria.

- Only enter meaningful filters. For example, you can specify an interval that does not exist and cannot be verified. To enter meaningful filters, you must know the sorting rules that are used.

- Check your filters by occasionally opening the filter pane. In the Application menu, choose Customize, and then choose Filter Pane to see an overview of all filters that have been applied. To remove all filters on a page, choose the page title drop-down arrow, and then choose Clear Filter. Note that this also cancels a default list view, such as that set for Sales Orders - Open.

The following procedures show the different filtering methods for filtering data that uses the CRONUS International Ltd. demonstration database.
-->

<!--
You can add a filter on one or more columns in a list. Filtering on columns is more flexible and enhanced than the Quick Filter. 


### To add a filter on a column
1. To open the filter pane, 
2. Choose the downwards arrow in the column heading, and then choose **Filter**.
3. Do one of the following: 
  -  Choose *...* next to the box to select a value from a list.
  -  Enter filter criteria in the box. See the next section for details.
4. Choose the **OK** button.

-->

## <a name="FilterCriteria"> </a>Filter criteria and symbols
When you enter criteria, you can use all the numbers and letters that you can normally use in the field. In addition, you can use special symbols to further filter the results. The following tables show the symbols which can be used in filters.  

> [!NOTE]  
>   You cannot use a wildcard when filtering on enumeration fields, such as the **Status** field on sales orders. To enter a filter for this type of field, you can enter the numeric value as a filtering parameter. For example, in the **Status** field on a sales order that has the values **Open**, **Released**, **Pending Approval**, and **Pending Prepayment**, use the values **0**, **1**, **2**, and **3** to filter for these options. 

> [!IMPORTANT]  
>  There may be instances where field values contain these symbols and you want to filter on them. To do this, you must include the filter expression that contains the symbol in quotation marks (''). For example, if you want to filter on records that start with the text *S&R*, the filter expression is **'S&R*'**.  
  
### (..) Interval  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|1100..2100|Numbers 1100 through 2100|  
|..2500|Up to and including 2500|  
|..12 31 00|Dates up to and including 12 31 00|  
|P8..|Information for accounting period 8 and thereafter|  
|..23|From the beginning date until 23-current month-current year 23:59:59|  
|23..|From 23-current month-current year 0:00:00 until the end of time|  
|22..23|From 22-current month-current year 0:00:00 until 23-current month-current year 23:59:59|  
  
### (&#124;) Either/or  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|1200&#124;1300|Numbers with 1200 or 1300|  
  
### (<>) Not equal to  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|<>0|All numbers except 0<br /><br /> The SQL Server Option allows you to combine this symbol with a wild card expression. For example, <>A* meaning not equal to any text that starts with A.|  
  
### (>) Greater than  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|>1200|Numbers greater than 1200|  
  
### (>=) Greater than or equal to  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|>=1200|Numbers greater than or equal to 1200|  
  
### (<) Less than  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|<1200|Numbers less than 1200|  
  
### (<=) Less than or equal to  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|<=1200|Numbers less than or equal to 1200|  
  
### (&) And  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|>200&<1200|Numbers greater than 200 and less than 1200|  
  
### ('') An exact character match  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|'man'|Text that matches man exactly and is case sensitive.|  
  
### (@) Case insensitive  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|@man*|Text that starts with man and is case insensitive.|  
  
### (*) An indefinite number of unknown characters 
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|*Co*|Text that contains "Co" and is case sensitive.|  
|*Co|Text that ends with "Co" and is case sensitive.|  
|Co*|Text that begins with "Co" and is case sensitive.|  
  
### (?) One unknown character  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|Hans?n|Text such as Hansen or Hanson|  
  
### Combined format expressions  
  
|Sample Expression|Records Displayed|  
|-----------------------|-----------------------|  
|5999&#124;8100..8490|Include any records with the number 5999 or a number from the interval 8100 through 8490.|  
|..1299&#124;1400..|Include records with a number less than or equal to 1299 or a number equal to 1400 or greater (all numbers except 1300 through 1399).|  
|>50&<100|Include records with numbers that are greater than 50 and less than 100 (numbers 51 through 99).|  
 
 
## See Also
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
