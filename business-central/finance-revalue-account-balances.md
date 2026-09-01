---
title: Revalue general ledger account balances 
description: Learn how to revalue general ledger account balances before you produce your financial statements.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.date: 09/01/2026
ms.custom: bap-template
ms.search.form: 
ms.service: dynamics-365-business-central
---

# Revalue general ledger account balances

If you use general ledger (G/L) accounts to register balance sheet items in foreign currencies, revalue the account balances before you produce financial statements. Because exchange rates change over time, the local currency (LCY) value of foreign-currency balances might not reflect their current value. Revaluation helps make your financial statements balances more accurate by using current exchange rates.

## About source currency tracking

[!INCLUDE [prod_short](includes/prod_short.md)] can store the original currency and amount for entries posted to G/L accounts. This information is referred to as the **source currency**.

Source currency tracking helps you:

- Analyze G/L balances by original transaction currency.
- Review source currency balances for individual accounts.
- Revalue balances that are tracked directly on G/L accounts.
- Report on assets and liabilities maintained outside customer, vendor, or bank ledgers.

Source currency information complements LCY and additional reporting currency (ACY) amounts. It isn't intended to replace customer, vendor, bank, or detailed ledger entries.

> [!NOTE]
> Source currency amounts are stored for information, analysis, audit, reporting, and revaluation purposes. They preserve the original transaction amount and currency that were used when the transaction was posted. Source currency amounts don't replace LCY amounts or ACY amounts in posting calculations, balancing logic, or financial reporting processes. [!INCLUDE [prod_short](includes/prod_short.md)] continues to use LCY and, when configured, ACY according to the standard posting framework.

### When to use G/L account revaluation

Use G/L account revaluation for balances you maintain directly on G/L accounts that need periodic exchange rate adjustments. Examples include:

- Foreign currency loans.
- Intercompany balances you track directly through G/L accounts.
- Monetary assets and liabilities you maintain outside customer and vendor ledgers.
- Other balance sheet accounts where you need to monitor and revalue source currency balances.

### When not to use G/L account revaluation

Before enabling revaluation, check whether another [!INCLUDE [prod_short](includes/prod_short.md)] feature better matches your accounting or reporting requirements. Consider using customer, vendor, or bank accounts instead when:

- You need detailed audit trails for exchange rate adjustments.
- You must track assets separately.
- Existing exchange-rate adjustment processes already manage the balances.
- Regulatory or audit requirements require adjustment entries per transaction or per entity.

> [!IMPORTANT]
> Don't use G/L account revaluation for balances that customer, vendor, or bank ledger entries already manage and that the **Adjust Exchange Rates** process regularly adjusts. Discuss the appropriate setup with your auditor or accountant before implementing the feature.

## Set up revaluations

You set up each account that you want to include in source currency tracking and revaluations on the **G/L Account Card** page. You can control which currencies can be posted, enable or disable source currency revaluation, select whether to post revaluation adjustments to realized or unrealized gains/losses accounts, and select the accounts used to post revaluation adjustments. Posting gains and losses during a currency exchange rate adjustment follows the normal posting routine. For example, you do it for each setup on the **Currencies** page. To learn more about exchange rate adjustments, go to [Update currency exchange rates](finance-how-update-currencies.md).

### Configure source currency posting

To help prevent posting errors and inconsistent balances, use the **Source Currency Posting** field to control which currencies are allowed on individual G/L accounts.

| Option | Description |
|----------|----------|
| Blank (All currencies) | Transactions in any currency can be posted to the account. |
| Multiple currencies | Only currencies defined on the **Source Currencies** page can be posted. |
| Same currency | All foreign-currency entries posted to the account must use the same source currency. |
| Local currency | Only LCY transactions can be posted. Foreign-currency posting isn't allowed. |

If you select **Multiple currencies**, define the allowed currencies on the **Source Currencies** page.

### Enable source currency revaluation

Enable revaluation only on accounts whose balances you want to periodically adjust based on updated exchange rates. Accounts can use source currency tracking without participating in revaluation.

### How revaluation works

On the **Chart of Accounts** page, choose **G/L Currency Revaluation**.

The batch job:

1. Reviews balances posted in foreign currencies.
2. Calculates differences based on the current exchange rates.
3. Creates adjustment entries in the journal that you select.
4. Lets you review and modify entries before posting.

When you post adjustment entries, the LCY balance of the account updates to reflect current exchange rates while preserving the original source currency balance.

### Adjustment granularity

Unlike customer and vendor exchange-rate adjustment processes, G/L account revaluation works on balances. Revaluation creates adjustment entries per:

- G/L account
- Source currency
- Dimension combination

This behavior is important when evaluating reporting requirements because transaction-level adjustments aren't created.

> [!NOTE]
> Revaluation adjusts accumulated balances. It doesn't support applying and unapplying entries the way customer and vendor ledger entries do.

## Additional reporting currency

If you use an ACY, revaluation entries also contain ACY amounts. The ACY amount on the revaluation entry corresponds to the LCY adjustment being posted. The process doesn't independently revalue the historical ACY balance of the account.

If you change exchange rates for an ACY after posting revaluation entries, run **Adjust Exchange Rates** to update the affected entries.

## Closing your income statement

[!INCLUDE [prod_short](includes/prod_short.md)] supports source currency information when you close fiscal years and post closing entries.

The close income statement process preserves source currency balances separately for each original transaction currency when you configure an ACY. Closing entries maintain source currency traceability and help ensure that source currency totals remain meaningful when income statement accounts contain entries posted in multiple currencies.

If income statement accounts contain entries in multiple source currencies, you can generate closing entries separately for each source currency to maintain a consistent relationship between source currency amounts and source currency codes.

> [!NOTE]
> Closing entries always balance LCY amounts used in financial statements. Source currency information continues to serve reporting and analysis purposes and should be interpreted together with the corresponding source currency code.

## G/L account revaluation compared to exchange rate adjustment

Although both features deal with currency fluctuations, they serve different purposes.

### G/L account revaluation

- Works on G/L account balances.
- Creates adjustments per account and source currency.
- Intended for balances maintained directly on G/L accounts.
- Doesn't provide transaction-level revaluation history.

### Customer and vendor exchange rate adjustment

- Works on customer, vendor, and bank ledger entries.
- Creates adjustments based on detailed ledger data.
- Supports more granular reporting scenarios.
- Can optionally create adjustment entries per individual ledger entry.

### Example

Suppose a company records several foreign-currency loans in a single G/L account.

Using G/L account revaluation:

- Revaluation adjusts the aggregated account balance.
- One adjustment is created per currency and dimension combination.
- Individual loans aren't separately revalued.

Using vendor accounts:

- Each loan can be represented by a separate vendor.
- Adjustments are created per vendor and currency.
- More detailed reporting and audit tracking are available.

Choose the approach that best supports your accounting and reporting requirements.

## Known considerations

### Historical entries

Source currency tracking was introduced after some historical transactions were already posted. Historical entries created before source currency functionality was available or enabled might not contain complete source currency information.

When you review historical balances, consider the posting date and whether source currency tracking was available at the time the entries were created.

### Source currency consistency validation

[!INCLUDE [prod_short](includes/prod_short.md)] can validate source currency balances and posting consistency during posting operations.

In environments that use customizations, partner extensions, or integrations that extend standard posting features, specialized posting scenarios can require extra validation to ensure source currency information stays aligned with the implemented business logic.

If needed, administrators can disable source currency consistency validation on the **General Ledger Setup** page while they investigate or align customized posting behavior. When the solution is validated, enable the validation again to help maintain source currency integrity and reporting quality.

This setting is primarily relevant for customized implementations and isn't typically required for standard [!INCLUDE [prod_short](includes/prod_short.md)] features.

### System-generated entries

System-generated entries can differ from manually posted business transactions. Examples include adjustment entries, corrections, gain/loss postings, closing entries, and other balancing entries. Review results before you post and validate expected balances as part of your month-end process.

### Specialized financial scenarios

G/L account revaluation is designed for general balance-sheet revaluation scenarios. Organizations with requirements that involve the following entities should evaluate whether the feature satisfies their reporting and compliance obligations:

- Financial instruments
- Securities
- Leased assets
- High-volume transaction portfolios
- Industry-specific valuation requirements

### Rounding behavior

When you post transactions in foreign currencies, [!INCLUDE [prod_short](includes/prod_short.md)] applies currency rounding according to the posting process that you're using.

#### Documents

For sales and purchase documents, [!INCLUDE [prod_short](includes/prod_short.md)] applies currency rounding at the document level by using rolling rounding across the entire document. This behavior helps ensure that the total posted amount matches the expected document amount in the transaction currency.

#### Journals

For general journals, [!INCLUDE [prod_short](includes/prod_short.md)] rounds currencies per journal line. This behavior applies even when multiple journal lines share the same document number or represent a single invoice transaction. Because rounding happens independently for each line, the resulting source currency amounts can differ slightly from equivalent postings created through sales or purchase documents.

> [!TIP]
> When you compare source currency amounts between document postings and journal postings, consider the different rounding models before investigating apparent differences in source currency balances.

## Troubleshooting

### Revaluation creates fewer entries than expected

This behavior is often expected. G/L account revaluation works with balances and creates one adjustment per account, currency, and dimension combination rather than per transaction.

### Source currency information appears incomplete

If the source currency information seems to be incomplete, review whether:

- Source currency tracking was enabled when the entries were created.
- The entries were imported or generated by another process.
- The entries were created before source currency features were available.

### Revaluation results don't match customer or vendor adjustments

This difference can occur because the two processes operate on different data sets.

Customer and vendor exchange-rate adjustments use detailed ledger entries. G/L account revaluation uses aggregated account balances.

## Best practices

- Use source currency posting controls to prevent accidental posting in unsupported currencies.
- Review generated journals before posting revaluation adjustments.
- Avoid combining different accounting models for the same business balance.
- Discuss reporting and audit requirements with your accountant before choosing between G/L account revaluation and customer/vendor exchange-rate adjustments.
- Test the feature in a sandbox environment before implementation in production.
- When comparing source currency balances, consider whether transactions were posted through documents or journals because different rounding models can produce different source currency distributions while still producing the same financial result.

> [!TIP]
> Ask your accountant or auditor about which type of account is best for your business. Also, there might be an app for [!INCLUDE [prod_short](includes/prod_short.md)] on [Marketplace](https://marketplace.microsoft.com/en-us/marketplace/apps?page=1&product=dynamics-365-business-central) that's right for your business scenarios.

## Related information

[Review Amounts in General Ledger Accounts](finance-review-accounts.md)  
[Understanding the General Ledger and Chart of Accounts](finance-general-ledger.md)  
[Update currency exchange rates](finance-how-update-currencies.md)  
[Set up currencies](finance-set-up-currencies.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]