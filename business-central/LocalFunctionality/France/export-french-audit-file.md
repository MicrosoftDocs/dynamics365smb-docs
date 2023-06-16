---
title: Export entries for tax audits
description: This article describes how to prepare and export audit files to comply with the specified tax regulations in France.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 
ms.date: 06/13/2023
ms.author: altotovi

---

# Export General Ledger entries for tax audits

In France, companies must provide corporate tax and VAT information, such as transactions and general ledger postings, for audits. The information must be provided in a file format that's specified by tax authorities. In [!INCLUDE[prod_short](../../includes/prod_short.md)], this information is recorded in a standard audit file that is designed to provide information about account types that include posted entries.

> [!NOTE]
> There is a new feature in release 22.1. To use this feature, run the **Audit File Export Document** page. 

## Export the audit file

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Audit File Export Document**, and then select the related link.
2. Select **New** to create new exporting process. 
3. In the **Audit File Export Format** field, select **FEC** to specifiy the format that's used to export the audit file.  
4. On the **FEC** FastTab, mark the **Include Opening Balances** field to include opening balances in the audit report file. The balances are calculated as of the date before the first date of the period covered by the report. 
5. Enter the **Default Source Code** to specify the source code to be used if there is no code specified in the G/L entry. 
6. Enter information in the remaining fields as described in the article, [How to export Audit Files](\..\finance-how-to-export-audit-files.md).

## See also

[French Local Functionality](france-local-functionality.md)
[How to use Audit Files Export app](\..\finance-how-to-export-audit-files.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
