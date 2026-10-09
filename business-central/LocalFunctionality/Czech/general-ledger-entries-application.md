---
title: General Ledger Entries Application [CZ]
description: The Czech version of General ledger entries application enables companies to manage temporary and transfer accounts in the general ledger for improved tracking and processing of pending amounts.
author: ACMartinKunes
ms.topic: article
ms.search.keywords: Czech, finance, CZ, General ledger, Entries
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# General ledger entries application in the Czech version

Apart from the application of customer and vendor ledger entries, a new functionality for general ledger entry application has been introduced. Application of G/L entries is typically used to allow companies to work with temporary and transfer accounts in the general ledger. Temporary and transfer accounts are used as a temporary "storage" and contain amounts (ledger entries) pending further processing. The new application functionality lets you match general expenses to distributed expenses (transferred earlier from a general account for all amounts) by using the new applying and unapplying functions, and lets companies see analytic subtotals for a specific date by using the new **Open G/L Entries To Date** or **Inventory Account to Date** reports.

The G/L entries structure has been redesigned by adding new storage for application information of a G/L entry. The `Detailed G/L Entry` table contains all entries related to the original G/L entry and stores the application amount, while the `G/L Entry` table contains the total of this amount in the **Applied Amount** field.

The **Apply Entries** and **Unapply Entries** functions on the **General Ledger Entries** page have been added to the user interface.

Partial application is allowed. The remaining amount for applying is shown on the G/L entry. You can apply G/L entries before posting the general journal or the cash desk.

You can run batch application by using the **G/L Entry Applying** report.

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
