---
title: Undo a Journal Posting by Posting a Reversing Entry| Microsoft Docs
description: If you have made an erroneous posting in the general journal, then you can use the Reverse Transaction function to undo the posting with a correct audit trail.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reimbursement
ms.date: 06/15/2017
ms.author: sgroespe

---
# How to: Reverse Journal Posting
To undo an erroneous journal posting, you select the entry and create a reverse entry (entries identical to the original entry but with opposite sign in the amount field) with the same document number and posting date as the original entry. After reversing an entry, you must make the correct entry.

You can only reverse entries that are posted from a general journal line. An entry can only be reversed once.

For more information about posting from a general journal, see [How to: Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).

You can reverse entries from all **Ledger Entries** windows. The following procedure is based on the **General Ledger Entries** window.

## To reverse the journal posting of a general ledger entry
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Entries**, and then choose the related link.
2. Select the entry that you want to reverse, and then choose the **Reverse Transaction** action. Note that is must originate from a journal posting.
3. In the **Reverse Transaction Entries** window, select the relevant entry, and then choose the **Reverse** action.
4. Choose the **Yes** button on the confirmation message.

## See Also
[How to: Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md)  
[Working with General Journals](ui-work-general-journals.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)](ui-work-product.md)  
