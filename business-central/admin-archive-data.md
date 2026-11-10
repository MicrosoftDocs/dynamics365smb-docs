---
title: The Data Archive Extension
description: Preserve records before date compression deletes them. Learn how to view data archives, export them to Excel or CSV, and manage archived data.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.date: 11/10/2026
ms.custom: bap-template
ms.search.form: 630
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# The Data Archive extension

Over time, your business will accumulate a substantial amount of data, and as an administrator, it's probably a good idea to have a strategy for archiving data. Having lots of data can slow things down, for example, it might take slightly longer to generate reports, or even lock records. Additionally, large amounts of data can lead to increased storage costs.

The Data Archive extension lets you keep a copy of entries that date compression deletes. Date compression consolidates related entries into a single entry and deletes the originals. Learn more at [Compress Data with Date Compression](admin-manage-documents.md#compress-data-with-date-compression). The entries are still deleted from their original tables. The archive stores a separate copy for later inspection or export.

## Start archiving data

The extension is pre-installed and available on the **Extension Management**, so you don't need to do anything to get started. The extension is also available on Marketplace.

Your data archives are listed on the **Data Archive List** page. Each archive can contain data from multiple tables. Records from a table are stored in batches of up to 1,000 records, so the same table can have multiple entries in one archive. These batches don't create separate archives.

After you archive data, you can explore it using Microsoft Excel or as a CSV file.

* If you use **Save as Excel**, the workbook contains one worksheet for each data archive table entry.
* If you use **Save as CSV**, you'll get a ZIP file that contains one CSV file for each data archive table entry.

Exports skip tables for which you don't have read permission and show a message.

> [!TIP]
> The Excel and CSV options make it easier to use another app or service to move the data to another location, such as Azure Blob storage, or an analysis tool, such as Microsoft Power BI.

The Data Archive extension is used by the following batch jobs for date compression.

|Batch jobs  |
|---------|
|Date Compr. Item Budget Entries |
|Date Compress Bank Account Ledger |
|Date Compress Customer Ledger |
|Date Compress FA Ledger |
|Date Compress General Ledger |
|Date Compress Insurance Ledger |
|Date Compress Maint. Ledger |
|Date Compress Resource Ledger |
|Date Compress VAT Entries |
|Date Compress Vendor Ledger |
|Date Compress Whse. Entries |
|Date Compr. G/L Budget Entries |

To start archiving data when you run one of the batch jobs, turn on the **Archive Deleted Entries** toggle. The toggle is available only when the Data Archive extension is installed.

## Storage considerations for archives

The archived data is stored in the **Tenant Media** table. We recommend that you export old archives to, for example, a CSV file and then delete the old archive records.

## Related information

[Manage Storage by Deleting Documents or Compressing Data](admin-manage-documents.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
