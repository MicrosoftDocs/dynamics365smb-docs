---
title: Swiss General Ledger Accounts [CH]
description: This article explains enhancements to the Swiss General Ledger Accounts and General Journals.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: Swiss General Ledger Accounts, General Ledger Accounts enhancements, Swiss version
ms.search.form: 11500
ms.date: 04/30/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Swiss general ledger accounts

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes Swiss enhancements to general ledger accounts.

- Maintain the foreign currency balances of a bank account in the general ledger.  
- Sort general ledger account numbers on the **Chart of Accounts** page.  
- Preview the effects that posting general journals would have on the balances of certain general ledger accounts before actually posting them.  

## General ledger accounts and general journals

Companies often have different bank accounts for foreign currencies, and have a general ledger account for each bank account. In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can set up currency code and foreign currency balance information on the **Chart of Accounts** page. This allows you to maintain the original foreign currency balance of a bank account. Learn more in [Understanding the General Ledger and the COA](../../finance-general-ledger.md).  

For example, a company has two bank accounts: one for local currency (LCY) and one for euros (EUR). You must create a general ledger account for each bank account. For the EUR account, define the currency code as **EUR** and post journals in EUR or LCY.  

When the exchange rate for EUR and LCY changes, you can update and adjust the local currency balance for the EUR general ledger account using the adjust exchange rates batch job. This batch job creates and posts currency adjustment entries to the general ledger and updates the LCY balance.  

## Data type for general ledger accounts

The data type is set to text for the general ledger account number or account code to support the sorting requirements for the standardized Swiss Kontenrahmen Käfer (KMU) common chart of accounts. The account numbers list is sorted based on the text data type. The KMU chart of accounts contains the following account numbers:  

- 1176  
- 119.0  
- 1190  

## Viewing temporary balances in general journals

Before posting a general journal, you can preview the effect that posting would have on the balances of certain general ledger accounts. You can open a statistics page that shows the balances of the accounts, and the balances of the active lines that included the unposted values for the current journal. Learn more in [View Temporary Balances in General Ledger Journals](how-to-view-temporary-balances-in-general-ledger-journals.md).  

## Related information

- [View Temporary Balances in General Ledger Journals](how-to-view-temporary-balances-in-general-ledger-journals.md)
- [Switzerland Local Functionality](switzerland-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
