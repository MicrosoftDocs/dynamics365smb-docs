---
title: Export entries for Tax Audits
description: This topic describes how to prepare and export audit files to comply with the specified tax regulations in France.
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

# Export General Ledger Entries for Tax Audits in the French Version

In France, companies must provide corporate tax and VAT information, such as transactions and general ledger postings, for audits in a file format that is specified by tax authorities. In [!INCLUDE[prod_short](../../includes/prod_short.md)], this information is recorded in a standard audit file that is designed to provide information about account types that include posted entries.

> [!NOTE]
> There is a new feature from the release 22.1 and to use this feature you need to run **Audit File Export Document** page. 

## To start with exporting audit file

1.  Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Audit File Export Document**, and then choose the related link.  
2.  Click **New** action to create new exporting process. 
3.  In the **Audit File Export Format** field choosue the **FEC** option to specifiy the format which is used for exporting the audit file.  
4.  Mark the **Include Opening Balances** field in the **FEC** FastTab if you want to include opening balances in the audit report file. The balances are calculated as of the date before the first date of the period covered by the report. 
5.  Fill in the **Default Source Code** if you want to specify the source code to be used if there is no code specified in the G/L entry. 
6.  Fill in the fields as described in the article [How to export Audit Files](\..\finance-how-to-export-audit-files.md).

## See also

[French Local Functionality](france-local-functionality.md)
[How to use Audit Files Export app](\..\finance-how-to-export-audit-files.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
