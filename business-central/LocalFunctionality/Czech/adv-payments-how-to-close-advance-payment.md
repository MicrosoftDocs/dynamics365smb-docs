---
title: Closing advance letter
description: This section describes Advance Payments Localization for Czech extension functionality.
author: v-pejano

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, Advance Payments, Localization
ms.date: 10/01/2021
ms.reviewer: v-pejano
ms.author: v-pejano
---

# Closing an Advance Letter

If an unpaid advance letter will not be drawn or fully utilized, it can be closed. The function for closing the advance is available from the Sales/Purchase Advance Letter card (not from the advance history entries), via the **Close Advance Letter** action.

To close an advance, follow these steps:

1. Select the ![Lightbulb icon to open the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Advance Letters**, and then select the related link. For purchases, search for **Purchase Advance Letters**.
2. Open the advance letter card.
3. On the action bar, select **Close Advance Letter**.
4. In the Advance Payment Close dialog box, you can specify the date on which the advance will be closed. Closing triggers VAT settlement and creates a **VAT Close** entry for the advance VAT credit memo. From the **VAT Close** entry, you can print the VAT credit memo. Both the **Close** and **VAT Close** entries use the number series defined in the advance letter templates in the field for advance Letter credit memo number series.

The unused part of the advance will be transferred to the customer's balance as an open customer ledger entry.  
When closing the advance, a negative **Initial Entry** is automatically created so that the remaining payable amount of the advance is zero (initial Original Entry minus payments plus closing amount).

## See also

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
