---
title: Transaction Numbers in Business Central for Spain
description: Learn how transaction numbers group general ledger entries in Business Central for Spain and how period transaction numbers order entries by date.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: transaction numbers, Spanish version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Transaction numbers

Transaction numbers allow you to group entries with the same document number and date, so that you can balance them together.

The **Set Period Trans. Nos.** batch job assigns **Period Trans. No.** values to existing general ledger entries in posting date and transaction number order. Entries with the same posting date and transaction number receive the same period transaction number. Numbering starts at 1 for the first general ledger transaction, or at 2 when the batch starts at a later fiscal year boundary. The batch job doesn't create an opening transaction.

When you enter a transaction number in the first line of a journal, the same transaction number is automatically entered into the other lines if the entries aren't balanced. If the entries are balanced, the next number in the sequence is automatically entered into the other lines.  

Having sequential period transaction numbers, ordered by date, allows you to identify transactions posted in a fiscal year.

## Related information  

- [Post and Print All Transactions for a Period](how-to-post-and-print-all-transactions-for-a-period.md)
- [Spain Local Functionality](spain-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
