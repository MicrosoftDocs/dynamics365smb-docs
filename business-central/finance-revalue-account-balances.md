---
title: Revalue General Ledger Account Balances 
description: Learn how to revalue general ledger account balances before you produce your financial statements.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: conceptual
ms.date: 02/28/2024
ms.custom: bap-template
ms.search.form: 
ms.service: dynamics-365-business-central
---

# Revalue general ledger account balances

If you use general ledger accounts to register balance sheet items that are denominated in foreign currencies, it's probably a good idea to revaluate the balances before you produce financial statements for your business. Revaluation helps make your financial statements more accurate.

[!INCLUDE [prod_short](includes/prod_short.md)] helps simplify revaluations. For the general ledger accounts that you use for revaluations, you can post entries in currencies to the account. The source currency code and amount are saved to the ledger entry. On the **G/L Account Card** page, you can select whether to post revaluation adjustments to released or unrealized gains/losses accounts.

To minimize errors, you can set up a validation for the currencies you post to individual G/L accounts:

* Allow only one currency
* Multiple currencies
* All currencies

To revalue G/L account balances, you select a new batch job from the chart of accounts page: **Revalue G/L Accounts** to revalue the foreign currency amounts in local currency. The batch job creates an adjustment entry in a journal corresponding to the adjustment needed to revalue a currency’s local currency balance using the currency exchange rate table. An entry is created for each currency with a balance for each G/L account you include in the batch job. You can then select to post the journal or make edits if needed.

The setup is available on the G/L account cards, and the batch job in the menu on the **Chart of Accounts** page.

> [!NOTE]
> G/L revaluation might not meet all requirements for transaction and asset registrations that need revaluation. For example, for financial instruments, securities, leased assets, or if you use them for specific or large volumes of transactions or assets. We recommend that you discuss with your auditor whether you can use the feature.

Posting gains and losses during a currency exchange rate adjustment follows the normal posting routine. For example, it’s done for each setup on the currency card.

> [!NOTE]
> The new feature doesn’t provide the ability to apply or unapply entries. Adjustments are done on a balance per currency basis.

## See also

[Review Amounts in General Ledger Accounts](finance-review-accounts.md)  
[Understanding the General Ledger and Chart of Accounts](finance-general-ledger.md)  
