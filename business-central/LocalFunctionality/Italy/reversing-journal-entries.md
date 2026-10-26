---
title: Reversing Journal Entries in the Italian Version [IT]
description: Reversing Journal Entries feature introduces controls on the Reverse Transaction Entries page to ensure compliance with Italian legal requirements.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: reversing journal entries, Italian version
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Reversing journal entries in the Italian version

The Italian version adds checks to journal transaction reversal:

- You can't use **Reverse Transaction** for entries whose **Document Type** is **Invoice** or **Credit Memo**.
- A transaction can't be reversed after its G/L book entry has a progressive number from final printing.
- VAT entries must pass the reversal checks, including checks that they aren't closed or already reversed.

These checks don't mean that every transaction involving VAT is blocked. Journal reversal is also different from correcting a posted sales or purchase document. Use the correction or credit memo workflow appropriate to that document.

## Related information

- [Italy Local Functionality](italy-local-functionality.md)  
- [Reverse Journal Postings and Undo Receipts/Shipments](../../finance-how-reverse-journal-posting.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
