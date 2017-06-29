---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Swiss General Ledger Accounts
ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> includes Swiss enhancements to general ledger accounts. This allows you to do the following:  
  
-   Maintain the foreign currency balances of a bank account in the general ledger.  
  
-   Sort general ledger account numbers in the **Chart of Accounts** window.  
  
-   Prevent use of the incorrect positive or negative signs for the amounts entered manually in the journals.  
  
-   Preview the effects that posting general journals would have on the balances of certain general ledger accounts before actually posting them.  
  
## General Ledger Accounts and General Journals  
 Companies often have different bank accounts for foreign currencies, and have a general ledger account for each bank account. In ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->, you can set up currency code and foreign currency balance information in the **Chart of Accounts** window. This allows you to maintain the original foreign currency balance of a bank account. For more information, see [Chart of Accounts Window](assetId:///fa407624-b670-44b6-8397-91aa606e4c39) and [G\/L Account Table](assetId:///a65c2b09-9bb2-43db-8c53-c047bfc49777).  
  
 For example, a company has two bank accounts: one for local currency \(LCY\) and one for euros \(EUR\). You must create a general ledger account for each bank account. For the EUR account, define the currency code as **EUR** and post journals in EUR or LCY.  
  
 When the exchange rate for EUR and LCY changes, you can update and adjust the local currency balance for the EUR general ledger account using the adjust exchange rates batch job. For more information, see [Adjust Exchange Rates Batch Job](../Topic/\($%20B_595%20Adjust%20Exchange%20Rates%20$\).md). This batch job creates and posts currency adjustment entries to the general ledger and updates the LCY balance.  
  
### Data Type for General Ledger Accounts  
 The data type is set to text for the general ledger account number or account code to support the sorting requirements for the standardized Swiss Kontenrahmen Käfer \(KMU\) common chart of accounts. For more information, see [Chart of Accounts Window](assetId:///fa407624-b670-44b6-8397-91aa606e4c39). The account numbers list is sorted based on the text data type. The KMU chart of accounts contains the following account numbers:  
  
-   1176  
  
-   119.0  
  
-   1190  
  
### Correcting Positive and Negative Signs in General Journals  
 When you manually enter amounts in the journal, the positive and negative signs for the amounts are automatically checked. Depending on the account type and the document type, incorrect signs are automatically corrected, and a message is displayed. For more information, see [General Journal Line Table](assetId:///5308c791-0964-41d9-bc54-fd87e815d1be).  
  
 The amounts for customer invoices, vendor credit memos, and payments must be positive. The amounts for vendor invoices, customer credit memos, and payments must be negative.  
  
### Viewing Temporary Balances in General Journals  
 Before posting a general journal you can preview the effect that posting would have on the balances of certain general ledger accounts. You can open a statistics window that shows the balances of the accounts, and the balances of the active lines that included the unposted values for the current journal. For more information, see [How to: View Temporary Balances in General Ledger Journals](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-view-temporary-balances-in-general-ledger-journals.md).  
  
## See Also  
 [How to: View Temporary Balances in General Ledger Journals](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-view-temporary-balances-in-general-ledger-journals.md)   
 G\/L Account   
 Chart of Accounts   
 Adjust Exchange Rates   
 Gen. Journal Line   
 Sales Journal   
 Purchase Journal   
 [Switzerland Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/switzerland-local-functionality.md)