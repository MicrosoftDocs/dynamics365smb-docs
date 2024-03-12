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

If you use general ledger accounts to register balance sheet items in foreign currencies, you should revaluate the balances before you produce financial statements. Revaluation helps make your financial statements more accurate.

[!INCLUDE [prod_short](includes/prod_short.md)] helps simplify revaluations. For the general ledger accounts that you use for revaluations, you can post entries in currencies to the account. The source currency code and amount are saved to the ledger entry. On the **G/L Account Card** page, you can select whether to post revaluation adjustments to released or unrealized gains/losses accounts.

To minimize errors, you can set up a validation for the currencies that you want to allow to post to individual G/L accounts:

* Only one currency
* Multiple currencies
* All currencies
* Only local currency

To revalue the foreign currency amounts in local currency for G/L account balances, on the **Chart of Accounts** page, use the **Revalue G/L Accounts** action to start a batch job. The batch job creates an adjustment entry in a journal corresponding to the adjustment needed. The local currency revaluation uses the currency exchange rate table. A journal entry is created for each currency with a balance for each G/L account you include in the batch job. You can then post or edit the journal.

The setup is available on card pages for G/L accounts, and the **Revalue G/L Accounts** action is on the **Chart of Accounts** page.

> [!NOTE]
> G/L account revaluation might not meet all requirements for transaction and asset registrations that need revaluation. For example, for financial instruments, securities, leased assets, or if you use them for specific or large volumes of transactions or assets. We recommend that you discuss with your auditor whether you can use the feature.

Posting gains and losses during a currency exchange rate adjustment follows the normal posting routine. For example, you do it for each setup on the **Currency Card** page. To learn more about exchange rate adjustments, go to [Update currency exchange rates](finance-how-update-currencies.md).

> [!NOTE]
> The new feature doesn’t provide the ability to apply or unapply entries. Adjustments happen on a balance per currency basis.

## Revaluate G/L accounts for exchange rate adjustments for customer, vendor, and bank accounts

Revaluation simplifies the task of adjusting G/L account balances before you generate a financial statement. The feature revaluates the balance per currency per G/L account, much like you do for adjustments to G/L accounts that are linked to bank accounts. If youre using the G/L account to keep track of multiple assets, you might have to consider using a vendor or customer account instead. 

> [!NOTE]
> G/L account revaluation might not meet all requirements for transaction and asset registrations that need revaluation. For example, for financial instruments, securities, leased assets, or if you use them for specific or large volumes of transactions or assets. We recommend that you discuss with your auditor whether you can use the feature.

The following examples illustrate the difference between using a G/L account and using a vendor account to track the balance of two monetary assets that use a foreign currency.

**Use a G/L account**
Example with posting 2 'loans', making a few payments and a few revals. Pointing to the adjustments being made per currency balances

**Use a vendor account**
Example with posting 2 'loans, making a few payments and a few revals. Pointing to the adjustments being made per vendor ledger entry (if the setting "post per entry" is selected in reqs page).

> [!TIP]
> We recommend that you ask your accountant or auditor which type of account is best for your business. Also, there might be an app for [!INCLUDE [prod_short](includes/prod_short.md)] on [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=dynamics-365-business-central) that's just right for your business scenarios.

## See also

[Review Amounts in General Ledger Accounts](finance-review-accounts.md)  
[Understanding the General Ledger and Chart of Accounts](finance-general-ledger.md)  
