---
title: "View Table Information"
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/20/2020
ms.author: jswymer
---

# Viewing Table Information

The page **8700 Table Information** provides information about all system and business tables in a Business Central solution. In particular, the page displays information about the amount of data the tables contain.

This information is useful for troubleshooting performance problems, because let's you see the distribution of data size across tables.

## Viewing table information

To open this page, select the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Table Information**, and then choose the related link.

The following table describes the information provided for each table:

|Column|Description|
|------|-----------|
|Company Name|The name of the company, if any, that the table belongs to.|
|Table Name|The name of the table.|
|Table No.|The ID of the table|
|No. of Records|The total number of records stored in the table.|
|Record Size|The average record size in KB/record. The value is calculated using the following formula: 1024(Size)/(No. of Records)`. |

## See Also

[Inspecting Pages](across-inspect-page.md)  
[Performance Articles For Developers](/dynamics365/business-central/a/dev-itpro/performance/performance-developer)  
