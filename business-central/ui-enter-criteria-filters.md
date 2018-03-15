---
title: Searching Data and Entering Filter Criteria | Microsoft Docs
description: Describes how to work with filters, such as the Quick Filter, to refine the results you get when you search for data.
services: project-madeira
documentationcenter: ''
author: jswymer

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: delimit, FlowFilter
ms.date: 03/29/2017
ms.author: solsen

---
# Searching, Filtering, and Sorting Data
There are a few things that you can do that will help you find, pinpoint, and scan records in a list. These include sorting, searching and filtering.

When you want to search for data, such as customer names, addresses, or product groups, you enter criteria. In search criteria you can use all the numbers and letters that you normally use in the specific field. In addition, you can use special symbols to further filter the results. There are two ways to search: using the Quick Filter or column filters.

## Sorting
Sorting makes it easy for you to get a quick overview of your data. If you have many customers, for example, you can choose to sort them by **Customer No.**, **Customer Posting Group**, **Currency Code**, **Country Region Code**, or **Sales Tax Registration No.** to get the overview you need.

To sort a list, you can either choose a column heading text to toggle between ascending and descending order, or choose the small downs arrow in the column heading, and then choose **Ascending** or **Descending**.  

> [!NOTE]  
>   Sorting is not supported images, BLOB fields, FlowFilters, and fields that do not belong to a table.  

## Searching by using the Quick Filter
You can add filters to all pages by using the Quick Filter. The Quick Filter is enabled by choosing the magnifier icon in the top right corner of a page. This filtering type is used for a fast entry of criteria.

> [!IMPORTANT]  
>   The Quick Filter provides an easy access to filter data by entering plain text, but does also provide a lot of search criteria options. Depending on whether you enter plain text or text including symbols, the Quick Filter behaves differently.  

* If you enter plain text in the search criteria, the search criteria is interpreted as a case insensitive search that contains certain text.  
* If you enter text including symbols in the search criteria, the search criteria is interpreted exactly as you entered it, and the search is case sensitive.

### Quick filter criteria
<!-- html syntax because symbols conflict with MarkDown syntax -->
<TABLE>
  <TR>
    <TH>Search Criteria</TH>
    <TH>Interpreted as...</TH>
    <TH>Returns...</TH>
  </TR>
  <TR>
    <TD>man</TD>
    <TD>@&#42;man&#42;</TD>
    <TD>All records that contain the text <b>man</b> and case insensitive.</TD>
  </TR>
  <TR>
    <TD>se</TD>
    <TD>@&#42;se&#42;</TD>
    <TD>All records that contain the text <b>se</b> and case insensitive.</TD>
  </TR>
  <TR>
    <TD>Man&#42;</TD>
    <TD>Starts with <b>Man</b> and case sensitive.</TD>
    <TD>All records that start with the text <b>Man</b>.</TD>
  </TR>
  <TR>
    <TD>'man'</TD>
    <TD>An exact text and case sensitive.</TD>
    <TD>All records that match <b>man</b> exactly.</TD>
  </TR>
  <TR>
    <TD>@man* </TD>
    <TD>Starts with and case insensitive.</TD>
    <TD>All records that start with <b>man</b>.</TD>
  </TR>
    <TR>
    <TD>@&#42;man</TD>
    <TD>Ends with and case insensitive.</TD>
    <TD>All records that end with <b>man</b>.</TD>
  </TR>
</TABLE>

> [!NOTE]  
>   You cannot use a wildcard when filtering on enumeration fields, such as the **Status** field on sales orders. To enter a filter for this type of field, you can enter the numeric value as a filtering parameter. For example, in the **Status** field on a sales order that has the values **Open**, **Released**, **Pending Approval**, and **Pending Prepayment**, use the values **0**, **1**, **2**, and **3** to filter for these options. 

## Searching by using column Filters
You can add a filter on one or more columns in a list. Filtering on columns is more flexible and enhanced than the Quick Filter. 

### To add a filter on a column
1.  Before you add a filter, choose ![Show as list](media/ui_show_as_list_icon.png "Show as list arrow left") icon to change to the list view.
2. Choose the downwards arrow in the column heading, and then choose **Filter**.
3. Do one of the following: 
  -  Choose *...* next to the box to select a value from a list.
  -  Enter filter criteria in the box. See the next section for details.
4. Choose the **OK** button.

## Filter criteria and symbols
When you enter criteria, you can use all the numbers and letters that you can normally use in the field. In addition, you can use special symbols to further filter the results. The following tables show the symbols which can be used in filters.  
  
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
