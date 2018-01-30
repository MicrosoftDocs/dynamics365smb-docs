---
    title: Enter Criteria in Filters | Microsoft Docs
    description: When you enter criteria, you can use all the numbers and letters that you can normally use in the field. In addition, you can use special symbols to further filter the results. For information on how to use the Quick Filter, see [Use Quick Filter on Pages](../FullExperience/how-to-use-quick-filter-on-pages.md).
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Enter Criteria in Filters
When you enter criteria, you can use all the numbers and letters that you can normally use in the field. In addition, you can use special symbols to further filter the results. For information on how to use the Quick Filter, see [Use Quick Filter on Pages](../FullExperience/how-to-use-quick-filter-on-pages.md).  
  
## Symbols  
 The following tables show the symbols which can be used in filters in ADD INCLUDE<!--[!INCLUDE[d365fin](../../includes/d365fin_md.md)]-->.  
  
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
|*Co*|Text that contains "Co"|  
|*Co|Text that ends with "Co"|  
|Co*|Text that begins with "Co"|  
  
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
 [Set Filters](../FullExperience/how-to-set-filters.md)   
 [Sorting](../FullExperience/sorting.md)   
 [Keyboard Shortcuts](../FullExperience/keyboard-shortcuts.md)