---
author: brentholtorf
ms.topic: include
ms.date: 03/17/2026
ms.author: bholtorf
ms.reviewer: bholtorf
---

Report authors can specify the status of financial reports, row definitions, and column definitions in the report lifecycle. For example, [!INCLUDE [prod_short](../includes/prod_short.md)] provides the following statuses. If these statuses don't fit your needs, you can create your own.

- **Active**, to indicate that a report is current and ready-to-use.
- **Draft**, to indicate that a report is being developed and you shouldn't use it.
- **Retired**, to indicate that a report isn't current and you shouldn't use it.

You can block a report or definition to prevent people from using it. For example, because it's in a draft or retired status. 

To create or view financial report statuses, [!INCLUDE [open-search-lowercase](../includes/open-search-lowercase.md)], enter **Financial Report Statuses**, and choose the related link. You assign a status to your reports and definitions in the **Status** field on the **Financial Reports** page, and the pages for row and column definitions from each report. 

To block a status, on the **Financial Reports** page, choose the status, and then select the **Blocked** checkbox.

> [!TIP]
> If a financial report has a definition with a blocked status, when you view the report [!INCLUDE [prod_short](../includes/prod_short.md)] lets you know by:
>
> - Displaying a notification at the top of the page.
> - Showing a message on the **Options** FastTab.