---
title: Close advance letters
description: This article describes how to close advance letters for Advance Payments in the Czech version.
author: bholtorf
ms.reviewer: bholtorf
ms.author: bholtorf
ms.topic: how-to
ms.search.keywords: Czech, Advance Payments, Localization
ms.date: 10/08/2026
ms.custom: bap-template
ai-usage: ai-assisted
---

# Close an advance letter

If you don't draw or fully utilize an unpaid advance letter, you can close it. The function for closing the advance is available from the **Sales Advance Letters** or **Purchase Advance Letters** pages by using the **Close Advance Letter** action. You don't close advances from the advance history entries.

To close an advance, follow these steps:

1. Select the ![Lightbulb icon to open the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters** or **Purchase Advance Letters**, and then select the related link.
2. Open the advance letter card.
3. Select the **Close Advance Letter** action.
4. In the **Advance Payment Close Dialog**, you can specify the date on which to close the advance. Closing triggers VAT settlement and creates a **VAT Close** entry for the advance VAT credit memo. From the **VAT Close** entry, you can print the VAT credit memo. Both the **Close** and **VAT Close** entries use the number series defined in the **Advance Letter Cr. Memo Nos.** field on the advance letter template.

The unused part of the advance transfers to the customer's balance as an open customer ledger entry.  

When you close the advance, a negative **Initial Entry** is automatically created so that the remaining payable amount of the advance is zero (initial original entry minus payments plus closing amount).

## Related information

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
