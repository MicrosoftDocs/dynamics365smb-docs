---
    title: Swiss General Ledger Accounts
    description: Swiss enhancements include special general ledger account features.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Swiss General Ledger Accounts
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] includes Swiss enhancements to general ledger accounts.

- Maintain the foreign currency balances of a bank account in the general ledger.  
- Sort general ledger account numbers on the **Chart of Accounts** page.  
- Preview the effects that posting general journals would have on the balances of certain general ledger accounts before actually posting them.  

## General Ledger Accounts and General Journals  
Companies often have different bank accounts for foreign currencies, and have a general ledger account for each bank account. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can set up currency code and foreign currency balance information on the **Chart of Accounts** page. This allows you to maintain the original foreign currency balance of a bank account. For more information, see [Understanding the General Ledger and the COA](../../finance-general-ledger.md).  

For example, a company has two bank accounts: one for local currency (LCY) and one for euros (EUR). You must create a general ledger account for each bank account. For the EUR account, define the currency code as **EUR** and post journals in EUR or LCY.  

When the exchange rate for EUR and LCY changes, you can update and adjust the local currency balance for the EUR general ledger account using the adjust exchange rates batch job. This batch job creates and posts currency adjustment entries to the general ledger and updates the LCY balance.  

## Data Type for General Ledger Accounts  
The data type is set to text for the general ledger account number or account code to support the sorting requirements for the standardized Swiss Kontenrahmen Käfer (KMU) common chart of accounts. The account numbers list is sorted based on the text data type. The KMU chart of accounts contains the following account numbers:  

- 1176  
- 119.0  
- 1190  

## Viewing Temporary Balances in General Journals  
Before posting a general journal you can preview the effect that posting would have on the balances of certain general ledger accounts. You can open a statistics page that shows the balances of the accounts, and the balances of the active lines that included the unposted values for the current journal. For more information, see [View Temporary Balances in General Ledger Journals](how-to-view-temporary-balances-in-general-ledger-journals.md).  

## See Also

[View Temporary Balances in General Ledger Journals](how-to-view-temporary-balances-in-general-ledger-journals.md)  
[Switzerland Local Functionality](switzerland-local-functionality.md)  
