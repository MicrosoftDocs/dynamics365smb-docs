---
author: brentholtorf
ms.topic: include
ms.date: 10/08/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

> [!NOTE]
> The country/region specific feature for applying and unapplying general ledger entries, described in this article, has been deprecated and is no longer available on the **General Ledger Entries** page. It's replaced by [Review Amounts in General Ledger Accounts](../../../finance-review-accounts.md), a feature available in all country/region versions. You can still access entries that were applied before the deprecation, but you can't use this feature to apply or unapply new entries. Learn more in [Deprecated Features in the Base App](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1).

Historically, by applying temporary general ledger entries, companies could work with temporary and transfer accounts in the general ledger. Temporary and transfer accounts are used to store temporary ledger entries that are waiting for further processing into the general ledger.  

Businesses used temporary accounts for:  

- Money transfers from one bank account to another.  
- Financial transaction transfers from one system to another in which part of the information temporarily resides on the original system.  
- Transactions for which a sales invoice was issued to a customer but the corresponding purchase invoice from the vendor hadn't yet been received.  

Entries that were applied before the feature was deprecated remain available for reference on the **General Ledger Entries** page, but you can no longer apply or unapply entries from that page. To track and confirm general ledger account balances going forward, use the **Review Entries** action on the **Chart of Accounts** or the **G/L Account Card** page instead. Learn more in [Review Amounts in General Ledger Accounts](../../../finance-review-accounts.md).  

## View general ledger entries

1. Choose the ![Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **G/L Registers**, and then choose the related link.  
1. Select a general ledger register, and then choose the **General Ledger** action.  

   The **General Ledger Entries** page shows the posted entries for the register, including any entries that were applied before this feature was deprecated.  
