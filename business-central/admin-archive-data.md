---
title: The Data Archive Extension
description: Archiving data creates a low-cost backup of your records.
author: brentholtorf


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 630
ms.date: 06/14/2021
ms.author: bholtorf

---

# The Data Archive Extension
Over time, your business will accumulate a substantial amount of data, and as an administrator, it's probably a good idea to have a strategy for archiving data. Having lots of data can slow things down, for example, it might take slightly longer to generate reports, or even lock records. Additionally, large amounts of data can lead to increased storage costs.

The Data Archive extension provides a basic framework for archiving and backing up data as part of date compression. When you use date compression, related entries are consolidated into a single entry, and the originals are deleted. For more information, see [Compress Data with Date Compression](admin-manage-documents.md#compress-data-with-date-compression). However, there might be value in keeping that data, so rather than deleting it, you can archive it for later use.

## Start Archiving Data
The extension is pre-installed and available on the **Extension Management**, so you don't need to do anything to get started. The extension is also available on Microsoft AppSource. 

Your data archives are listed on the **Data Archive List** page. Each archive can contain data from multiple tables, and can hold up to 10,000 records. If there are more than 10,000 records in a table, a second archive will be created for the next 10,000 records, and so on. For example, if you archive 10,100 G/L entries, Business Central creates one "G/L Entry" archive for the first 10,000 entries, and then a second archive for the remaining 100 entries. 

After you archive data, you can explore it using Microsoft Excel or as a CSV file.

* If you use the Excel option, the workbook will contain one worksheet for each data archive table.
* If you use the CSV option you'll get a ZIP file with one CSV file for each data archive table.

> [!TIP]
> The Excel and CSV options make it easier to use another app or service to move the data to another location, such as Azure Blob storage, or analysis tool, such as Microsoft Power BI.

The Data Archive extensions is used by the following batch jobs for date compression.

|Batch jobs  |
|---------|
|Date Comp. Item Budget Entries |
|Date Compress Bank Acc. Ledger |
|Date Compress Customer Ledger |
|Date Compress FA Ledger |
|Date Compress General Ledger |
|Date Compress Insurance Ledger |
|Date Compress Maint. Ledger |
|Date Compress Maint. Ledger |
|Date Compress Resource Ledger |
|Date Compress VAT Entries |
|Date Compress Vendor Ledger |
|Date Compress Whse. Entries |
|Date Compr. G/L Budget Entries |

To start archiving data when you run one of the batch jobs, turn on the **Archive Deleted Entries** toggle.

## Storage Considerations
The archived data is stored in the **Tenant Media** table. This table is not included when database size is calculated, according to your license terms. Instead, it counts as file storage. However, we recommend that you export old archives to, for example, a CSV file and then delete the old archive records.

## See Also
[Manage Storage by Deleting Documents or Compressing Data](admin-manage-documents.md)
