---
title: The Data Archive Extension
description: Archiving data creates a low-cost backup of your records.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.date: 01/30/2023
ms.custom: bap-template
ms.search.form: 630
ms.service: dynamics-365-business-central
---

# The Data Archive Extension

Over time, your business will accumulate a substantial amount of data, and as an administrator, it's probably a good idea to have a strategy for archiving data. Having lots of data can slow things down, for example, it might take slightly longer to generate reports, or even lock records. Additionally, large amounts of data can lead to increased storage costs.

The Data Archive extension provides a basic framework for archiving and backing up data as part of date compression. Date compression consolidates related entries into a single entry and deletes the originals. Learn more at [Compress Data with Date Compression](admin-manage-documents.md#compress-data-with-date-compression). However, there might be value in keeping that data, so rather than deleting it, you can archive it for later use.

## Start Archiving Data

The extension is pre-installed and available on the **Extension Management**, so you don't need to do anything to get started. The extension is also available on Marketplace.

Your data archives are listed on the **Data Archive List** page. Each archive can contain data from multiple tables, and can hold up to 10,000 records. If there are more than 10,000 records in a table, a second archive will be created for the next 10,000 records, and so on. For example, if you archive 10,100 G/L entries, Business Central creates one "G/L Entry" archive for the first 10,000 entries, and then a second archive for the remaining 100 entries.

After you archive data, you can explore it using Microsoft Excel or as a CSV file.

* If you use the Excel option, the workbook will contain one worksheet for each data archive table.
* If you use the CSV option, you'll get a ZIP file that contains one CSV file for each data archive table.

> [!TIP]
> The Excel and CSV options make it easier to use another app or service to move the data to another location, such as Azure Blob storage, or an analysis tool, such as Microsoft Power BI.

The Data Archive extension is used by the following batch jobs for date compression.

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

The archived data is stored in the **Tenant Media** table. We recommend that you export old archives to, for example, a CSV file and then delete the old archive records.

## Related information

[Manage Storage by Deleting Documents or Compressing Data](admin-manage-documents.md)
