---
title: Export entries for tax audits
description: This article describes how to prepare and export audit files to comply with the specified tax regulations in France.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: export audit files, French tax regulations, French version, tax audits
ms.search.form: 
ms.date: 10/08/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Export general ledger entries for tax audits

In France, companies must provide corporate tax and VAT information, such as transactions and general ledger postings, for audits. The information must be provided in a file format that's specified by tax authorities. In [!INCLUDE[prod_short](../../includes/prod_short.md)], this information is recorded in a standard audit file that is designed to provide information about account types that include posted entries.

> [!NOTE]
> This feature was introduced in release 22.1. To use this feature, run the **Audit File Export Documents** page.

## Export the audit file

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Audit File Export Documents**, and then select the related link.
1. Select **New** to create a new exporting process.
1. In the **Audit File Export Format** field, select **FEC** to specify the format that's used to export the audit file.  
1. On the **FEC** FastTab, mark the **Include Opening Balances** field to include opening balances in the audit report file. The balances are calculated as of the date before the first date of the period covered by the report.
1. Enter the **Default Source Code** to specify the source code to be used if there's no code specified in the G/L entry.
1. Enter information in the remaining fields as described in [Export data for auditing](../../finance-how-to-export-audit-files.md).

## Numbering in the "EcritureNum" tag

The numbering in the "EcritureNum" tag must increase over time and not contain any breaks. This transaction numbering must be unique for the whole file or specific to each journal code. Using the **No.** field in the **G/L Registers** table provides unique numbering. However, if you post multiple invoices through one journal, all of the invoices have one common **No.**. French regulation requires a unique number for each invoice.

To fulfill this requirement, [!INCLUDE[prod_short](../../includes/prod_short.md)] uses the transaction number as the progressive number in the audit file by default.

## Related information

- [France local functionality](france-local-functionality.md)
- [Export data for auditing](../../finance-how-to-export-audit-files.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
