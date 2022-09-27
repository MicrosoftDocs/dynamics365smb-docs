---
title: Search for Specific Data
description: You can use search when you want to find a specific record.
author: brentholtorf

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: data, search, record
ms.search.form: 
ms.date: 09/20/2022
ms.author: bholtorf
---

# Search for a Record in Your Data

When you want to find a particular record or value, use the **Search for Data** feature to look for it. Start a search on your Role Center in the following ways:

* Use the **Search for Data** action
* Use the Ctrl+Alt+F shortcut key combination.

## How search works

After you enter your keywords, [!INCLUDE[prod_short](includes/prod_short.md)] starts your search in the background and goes through each table one at a time. Search results begin to appear after it finished each table. 

If you enter more than one keyword, the results will include only records that have all of the words in any of the selected fields.

The results page shows the three most recently updated records. If there are more than three, you can choose **Show All** to display them.

Each time you choose a search result you increase the popularity of the table, and it will appear higher in the results. Additionally, the record will be found more quickly if you search for it in the future.

> [!NOTE]
> Headers on sales, purchase, and service documents actually represent different document types, such as quotes, invoices, and orders. Headers are treated as if they were tables. If your keyword was found in a line on one of these documents, when you choose the search result the page for the document displays, and not just the line.

## Getting started

You can speed up results by choosing the fields on the tables that you want to include in your searches. The tables and fields that you can choose from vary, depending on your Role Center. By default, all tables and fields are chosen, which can slow down the search. We recommend that you exclude as many tables and fields as you can.

## See Also

[Finding Pages and Information with Tell Me](ui-search.md)  
[Entering Data](ui-enter-data.md)  
