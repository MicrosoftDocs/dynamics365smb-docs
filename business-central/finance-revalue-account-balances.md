---
title: Revalue general ledger account balances 
description: Learn how to revalue general ledger account balances before you produce your financial statements.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.date: 08/06/2024
ms.custom: bap-template
ms.search.form: 
ms.service: dynamics-365-business-central
---

# Revalue general ledger account balances

If you use general ledger (G/L) accounts to register, balance sheet items in foreign currencies, you should revaluate the account balances before you produce financial statements. Currency exchange rates often change, and revaluation helps make your financial statements more accurate.

## Set up revaluations

You set up each account that you want to include in revaluations on the **G/L Account Card** page. You can select whether to post revaluation adjustments to realized or unrealized gains/losses accounts. Posting gains and losses during a currency exchange rate adjustment follows the normal posting routine. For example, you do it for each setup on the **Currencies** page. To learn more about exchange rate adjustments, go to [Update currency exchange rates](finance-how-update-currencies.md).

To minimize errors, in the **Source Currency Posting** field, you can set up a validation for the currencies that you want to allow to post to individual G/L accounts:

* All currencies (blank)
* Multiple currencies
* Same currency
* Local currency

## Run a revaluation

To revalue the foreign currency amounts in local currency for G/L account balances, on the **Chart of Accounts** page, use the **G/L Currency Revaluation** action to start a batch job. The batch job creates adjustment entries in the journal that you select. When you post the entries, you adjust the local currency (LCY) balance for the account. G/L account balances that always show in LCY now reflect changes to the currencies in which entries were posted. This revaluation enables you to produce a more accurate financial statement with less effort.

If you're using an additional reporting currency (ACY), the G/L revaluation entries have an ACY amount. The amount only corresponding to the LCY amount on these entries, not the ACY balance on the G/L account. If you adjust the ACY rates after you post the adjustments, run the currency exchange rate adjustment one more time to adjust all G/L entries.

> [!IMPORTANT]
> G/L account revaluation might not meet all requirements for transaction and asset registrations that need revaluation. For example, for financial instruments, securities, leased assets, or if you use them for specific or large volumes of transactions or assets. We recommend that you discuss with your auditor whether you can use the feature, and if so, how you should use it. For example, if you'll allow currencies to mix for an account, or if you need to keep a separate account for each asset you want to track.

> [!NOTE]
> Revaluation doesn’t provide the ability to apply or unapply entries, like you can with customer and vendor ledger entries. Adjustments happen on a balance per currency basis.

## Revaluate accounts vs. customer and vendor exchange rate adjustments

Revaluation simplifies the task of adjusting G/L account balances. The feature revaluates the balance per currency per G/L account much like you do for adjustments to G/L accounts that are linked to bank accounts. If you use a G/L account to track multiple assets, consider using a vendor or customer account instead.

> [!NOTE]
> G/L account revaluation might not meet all requirements for transaction and asset registrations that need revaluation. For example, for financial instruments, securities, leased assets, or if you use them for specific or large volumes of transactions or assets. We recommend that you discuss with your auditor whether you can use the feature, and if so, how you should use it. For example, if you'll allow currencies to mix for an account, or if you need to keep a separate account for each asset you want to track.

The following examples illustrate the difference between using a G/L account and using a vendor account to track the balance of two monetary assets that use a foreign currency.

**Use a G/L account**
If you're using one G/L account to track either multiple assets (for example, loans or fixed assets) in the same currency, or individual part transactions for the same asset but still in the same currency, G/L revaluation makes one entry per revaluation for the currency. This means that you can't track the adjustments related to individual assets or individual transactions for the same asset.

**Use a vendor account**
If you set up multiple assets as vendors and you post transactions to them, either in same or different currencies, you'll get an adjustment per currency per vendor. Or, if you turn on the **Posting per entry** toggle on the **Adjust Currency Exchange Rate** job queue entry, you'll get an adjustment entry for each separate vendor ledger entry.

This difference is important when you assess whether G/L revaluation is the right feature to you for your reporting needs.

> [!TIP]
> We recommend that you ask your accountant or auditor which type of account is best for your business. Also, there might be an app for [!INCLUDE [prod_short](includes/prod_short.md)] on [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=dynamics-365-business-central) that's just right for your business scenarios.

## Related information

[Review Amounts in General Ledger Accounts](finance-review-accounts.md)    
[Understanding the General Ledger and Chart of Accounts](finance-general-ledger.md)  
