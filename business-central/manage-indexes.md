---
title: Manage database index usage
description: Learn how to manage database indexes in Business Central to optimize performance, reduce storage costs, and improve write operations with enhanced tools.
author: phduck
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: article
ms.collection:
ms.date: 03/25/2026
ms.custom: bap-template
ms.search.form: 8705_Primary, 8700, 9521,
---

# Manage database index usage

[!INCLUDE [applies-to-2026-releasewave1-later](includes/applies-to-2026-releasewave1-later.md)]

As an admin, you can view and manage database indexes per company to optimize performance and reduce storage costs. Selectively disable nonessential indexes to improve write performance and storage, while protecting unique indexes and SIFT indexes from being disabled.

## About indexes

An *index* is a database structure that makes it faster to find, filter, sort, or aggregate data in a table. An index organizes one or more fields in a table so that SQL Server (for Business Central on‑premises) or Azure SQL (for online) can efficiently locate rows. Without an index, the database might need to scan the entire table to find matching records. With a suitable index, it can seek directly to the relevant rows, which is dramatically faster for large tables.

On the other hand, indexes have a maintenance cost: they require more storage and can slow down create, update, and delete (CRUD) operations because the index must be kept up to date.

In AL code, indexes are created based on the defined keys in both table objects and table extension objects. When you add a key, you get an index in the table in the database. A single table object and table extension object can have multiple secondary keys. Learn more in [Table keys](/dynamics365/business-central/dev-itpro/developer/devenv-table-keys).

Tables in Business Central can be either per-company, like the **Items** table, or shared across companies, like the **Tenant Media** table. For per-company tables, a complete SQL table definition exists for each company, including all indexes. For a per-company table like **Item**, each index exists independently within each company's dataset, allowing you to view and manage it on a per-company basis. This capability enables you to define an index as 'enable=false' and then selectively enable it for only a subset of companies, without negatively impacting other companies. This flexibility is useful for indexes that are only needed for certain functional areas used by specific companies.

## View indexes on a table

You view table indexes from the **Table Information** page:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Table Information**, then choose the related link.
1. On the **Table Information** page, locate the table and select its ID in the **Table No.** column.
1. On the **Table Data Management** page, set the **Company Name** field to the company for which you want to view indexes. If the **Company Name** field is empty, the table is used by all companies.
1. The **Indexes** section displays details of each index on table for the selected company, including index storage size, index usage statistics, and index type (AL-defined or system-generated). Use the values in the columns to determine underused indexes in a specific company or environment, and then turn them off as appropriate.

> [!NOTE]
> The index information is sourced from a virtual table called [Database Index](/dynamics365/business-central/application/system/table/system.diagnostics.database-index). This table exposes data from the corresponding [SQL dynamic management view (DMV)](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-usage-stats-transact-sql), providing two sets of usage metrics: user* and last_user*.

## Turn off or on indexes

You can turn off nonunique indexes with low usage to reduce storage costs and improve write performance. Unique indexes, primary keys, SIFT, and $systemid indexes are protected and can't be turned off.

**Turn off an index:**

1. On the **Table Data Management** page for the table as described in the previous section, select the index in the list.
1. Select **Turn index off** to disable the index for the specified company only, or select **Turn index off (all companies)** to disable the index for all companies in the environment.

Disabling an index takes effect immediately.

**Turn on an index:**

1. On the **Table Data Management** page, select the disabled index in the list.
1. Select **Turn index on** to enable the index for the specified company only, or select **Turn index on (all companies)** to enable the index for all companies in the environment.

Enabling an index is queued for the next scheduled midnight process.

## Related information

[View table information](admin-view-table-information.md)  
[Database missing indexes](database-missing-indexes.md)  