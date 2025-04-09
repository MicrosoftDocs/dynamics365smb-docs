---
title: Deferrals in Sales ledger and Purchase ledger reports
description: Learn how to set up and use deferrals in Sales ledger and Purchase ledger reports in the Belgian version of Business Central.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: deferral, sales ledger, purchase ledger
ms.search.form: 279, 1700, 1701
ms.date: 04/04/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Deferrals in Sales ledger and Purchase ledger reports

When you use deferrals, the Purchase ledger and Sales ledger reports in the Belgian version of Dynamics 365 Business Central must show only the original entries from invoices and credit memos, and not those created using deferrals.

## Set up deferrals

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Source Code Setup**, and then select the related link.  
1. On the **General** FastTab, enter any required field information and the fields described in the following table.  

   |      Field   |         Description        |
   |--------------|----------------------------|
   | **General Deferral** | The **Source Code** that the system uses for deferrals that are created from posting in General journals. |
   | **Sales Deferral** | The **Source Code** that the system uses for deferrals that are created from posting in Sales documents. |
   | **Purchase Deferral** | The **Source Code** that the system uses for deferrals that are created from posting in Purchase documents. |

1. Select **OK**.

> [!NOTE]
> You can configure specific source codes for deferral postings or use the same source code for the general journal, sales journals, and purchase journals.  

## Belgium Sales ledger and Purchase ledger reports

After the deferral entries have a specific source code, you can manipulate the reports’ view by selecting **Exclude Deferral Entries** in the Sales ledger and Purchase ledger reports.

When you set the option to **Off**, the report prints all entries related to a specified period. When the switch is **On**, the report excludes the deferral entries.  

> [!NOTE]
> The next period, of one month, doesn't include deferral entries when the switch is **On**.

## Related information

- [Belgium Local Functionality](belgium-local-functionality.md)
- [Make Journal Templates Mandatory](specify-journal-template-mandatory.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
