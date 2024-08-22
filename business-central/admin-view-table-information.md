---
title: View table information
description: Learn how you can view information about the database tables in Business Central.
author: jswymer
ms.topic: conceptual
ms.devlang: al
ms.search.form: 8700
ms.date: 10/11/2023
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Viewing table information

The **8700 Table Information** page provides information about the number of records in all system and business tables in [!INCLUDE[prod_short](includes/prod_short.md)], and how much data each table contains.

This information is useful for troubleshooting performance problems, because let's you see the distribution of data size across tables.

## View table information

To open this page, select the ![Search for Page or Report.](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Table Information**, and then choose the related link.

The following table describes the information provided for each table:

|Column|Description|
|------|-----------|
|Company Name|The name of the company, if any, that the table belongs to.|
|Table Name|The name of the table.|
|Table No.|The ID of the table.|
|No. of Records|The total number of records stored in the table.|
|Record Size|The average record size in KB/record. The value is calculated using the following formula: 1024(Size)/(No. of Records). |
|Size (KB)|The total amount of space the table occupies in the database. This value is the sum of the values in the Data Size and Index Size fields.|
|Data Size (KB)|How much space the data in the table occupies in the database.|
|Index Size (KB)|How much space the table indexes (keys) occupy in the database.|
|Compression|The type of compression, **Row**, **Page**, or **None** that is applied to the table in the database. For more information, see [Data compression](/sql/relational-databases/data-compression/data-compression?).|

> [!NOTE]
> If you delete data in a table, [!INCLUDE[prod_short](includes/prod_short.md)] starts several processes behind the scenes to make sure that everything is cleaned up in your database. The values on the Table Information page will not update until those processes are complete, which can take a while. The amount of time you'll have to wait can vary, depending on the size of your database.

> [!IMPORTANT]  
> The **Table Information** page shows data and index sizes, and the sum of table sizes will not match the total capacity used, because it displays the data size, not the actual allocated size. Allocated space is always larger than used space to avoid having to allocate space on every insert, which would limit performance significantly


## See Also

[Inspecting Pages](across-inspect-page.md)  
[Performance Articles For Developers](/dynamics365/business-central/dev-itpro/performance/performance-developer)  


[!INCLUDE[footer-include](includes/footer-banner.md)]