---
title: Tax Engine - Script Activity
description: Tax Engine - Script Activity
author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Tax Engine - Script Activity


Script extension contains UI elements and tables which are used in scripting of Business logics within a use case.

### String / Text

- **Concatenate**: Concatenates list values and outputs to a variable.

- **String Expression**: It is used to compose string. Names that are enclosed within curly braces are treated as tokens. Values can be assigned to tokens using lookups, whereas on the Value tab,  source of that token can be defined.

- **Length of String**: Calculates the length of the string and assigns it to the output variable.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the name of variable in which value of the length is stored.|
  |String|Specifies the string for which length is to be calculated, hard coded text or/and expression can be entered.|

- **Convert Case of String**: Converts the case of the string and assigns to the output variable.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the name of variable in which value of converted case will be stored.|
  |String|Specifies the string for which case will be converted, hard coded text or/and expression can be entered.|
  |Convert to Case|Converts case of the string, it can be either Upper Case or Lower Case.|

- **Find Substring in String**: Finds the substring in string and assigns the position of the substring to output variable.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the name of variable in which value of substring will be stored.|
  |String|This will be the string for which value of substring will be searched, hard coded text or/and expression can be entered.|
  |Substring|Specifies the string or expression which needs to be identified from String value.|

- **Replace Substring in String**: Replace substring in a string with a new string and assigns to output variable.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the name of variable in which the value of Replaced String will be stored.|
  |Sub String|This will be the string content which will be replaced from 'In String', hard coded text or/and expression can be entered.|
  |With String|This will be the string content which will be replaced with 'Sub String', hard coded text or/and expression can be entered.|
  |In String|This will be the string on which replacement of character will happen.|

- **Extract Substring**: Extracts substring of a length from a string from start/ end and assigns to output variable.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the name of variable in which value of Extracted Sub String will be stored.|
  |String|This will be the string for which value of Substring will be extracted, hard coded text or/and expression can be entered.|
  |From|Starting point of extraction, it can be either start or end.|
  |Length|Length of the character to extract.|

- **Extract Substring from Index of String**: Extracts substring of a length from a string with an index and assigns to output variable.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the variable name in which value of Extracted Sub String will be stored.|
  |In String|This will be the string for which value of Substring will be extracted, hard coded text or/and expression can be entered.|
  |From Index|Starting point of extraction as Index.|
  |Length|Length of the character to extract.|

### Number

- **Number Calculation**: Calculates the number based on values and the operator. It is assigned to output variable.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the variable name in which value of Calculated Number will be stored.|
  |Value|This will be the Left-Hand Side (LHS) of the Number Calculation.| 
  |Operator|Operator to be used for calculation, it can be Addition, Subtraction, Division, Multiplication.|
  |Value 2|This will be the Right-Hand Side (RHS) of the Number Calculation.|

- **Numeric Expression**: Numeric Expression is to evaluate expression into number and assign it to output variable. Text token will be extracted and replaced with values from Lookups, whereas on the value tab source of that token can be defined.

- **Round Number**: Round Number is used to round decimal places to a precision and direction could be nearest, up or down.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the variable name in which value of Rounded Number will be stored.|
  |Number|Value that will be rounded.|
  |Precision|Rounding precision.|
  |Direction|Direction of rounding, it can be Nearest, Up or Down.|

### Date

- **Date Calculation**: ‘Date Calculation’ is used to manipulate dates by adding or subtracting number of days / months / years and it is assigned to output variable.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the name of variable in which value of ‘Calculated Date’ will be stored.|
  |Date|This will be the date on which calculation will be done.|
  |Operator|This will be the operator that will be applied on ‘Date for calculation’.|
  |Number|This will be the number that will added or subtracted to date.|
  |Period|This will be the type that will be added or subtracted to date as Number. It can be Days, Week, Months, Year.|

- **Extract Date Part**: ‘Extract Date Part’ is used to extract day / month / year from a date and assign it to output variable.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the variable name in which value of Extracted Date will be stored.|
  |Date|This will be the Date on which extraction will be done.|
  |Part|Type of extraction, it can be Year, Month, Day.|

- **Find Interval between Dates**: Find Interval between dates is used to find number of days / hours / minutes between dates and assign it to output variable.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the variable name in which value of Interval will be stored.|
  |From Date|This will be starting date of date range.|
  |To Date|This will be ending date of date range.|

- **Extract Date Time Part**: Extracts the date or time from a 'date time value'.

  |Type|Description|
  |--------------------|-----------------------| 
  |Output Variable|Specifies the name of variable in which value of date or time will be stored.|
  |Date Time|This will be the date time value from which extraction will be done.|
  |Part|Part that will be extracted, it can be either date or time.|

- **Date to Date Time**: Converts a ‘Date’ value to ‘Date Time’

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|Specifies the name of variable in which value of ‘date time’ will be stored.|
  |Date|This will be the date value which will be part of 'date time'.|
  |Time|This will be the time value which will be part of ‘date time’.|

#### Condition

- **If Statement**: Activities within the "If" statement will be executed when the defined conditions are evaluated to be true. If the conditions are evaluated to false, activities in the “Else” branch will be executed. Conditions can be specified in “Else” branch. There can be more than one else branch for an “If Statement”.

### Loops

- **Loop n Times**: Executes activities in the loop block for n number of times. "N" can be a constant value, or it can be a variable.

- **Loop with Condition**: Executes activities in the loop block until condition is evaluated to be false.

- **Loop through Records**: Loop through all records and execute activities in the Loop block.

  |Type|Description|
  |--------------------|-----------------------|
  |Table Name|Name of table whose records need to be iterated.| 
  |Sorting|Sorting order of the records.|
  |Order|Ascending or Descending.|
  |Distinct|To skip duplicate records.|
  |Table Filters|Filters to be applied on the table records.| 
  |Record Value|Variable that holds the current record of the table.|
  |Index Variable|Loop index starts from 1.|
  |Count Variable|Count of records after applying filters.| 
  |Set Variables|To assign field values to a variable.|


- **Exit Loop**: Breaks loop and executes activates after the loop block.

- **Skip Next Activities**: Skips next activities in the loop block and continues execution of the next iteration.

### Misc.

- **Set Variable**: To assign Variable value.

  |Type|Description|
  |--------------------|-----------------------|
  |Output Variable|The variable which will be assigned with value.
  |Value|The value of variable, this can be constant or lookup.

- **Alert Message**: Message dialog will be displayed while execution rule. This is helpful to debug, and this can also be used for throwing errors.

  |Type|Description|
  |--------------------|-----------------------|
  |Message|Message that is to be displayed.
  |Throw Error|Check this flag to throw error message.



## Related information 
[Tax Engine Design Consideration](TaxEngine-006-Design-Consideration.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
