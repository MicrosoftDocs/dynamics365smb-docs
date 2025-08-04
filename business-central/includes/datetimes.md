---
author: brentholtorf
ms.topic: include
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
When you enter datetimes, which are a date and time combined into one field, you must enter a space between the date and the time. The date part can only contain spaces in the form of the official date separator of your region settings. The time can contain spaces around the AM/PM indicator in relevant regional settings.

<!--It is also possible to enter only a date in a datetime field, but it is not possible to enter only a time.-->

The following table lists the various ways in which you can enter datetimes and how they're interpreted.  

|Entry|Interpretation|
|---------------|------------------------|
|08-01-2022 05:48:12 PM|08\-01\-2022 05:48:12 PM|
|131222 132455|13-12-22 13:24:55|
|1-12-22 10|01-12-22 10:00:00|
|1.12.22 5|01-12-22 05:00:00|
|1.12.22|01-12-22 00:00:00|
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
|t23 t|Tuesday of week 23 of the work date year, current time of day|
|t23|Tuesday of week 23 of the work date year|
|t 23|Today 23:00:00|
|t-1|Tuesday of week 1 of the work date year|


