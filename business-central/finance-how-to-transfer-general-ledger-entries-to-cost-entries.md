---
    title: How to Transfer General Ledger Entries to Cost Entries | Microsoft Docs
    description: You can transfer general ledger entries to cost entries.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Transfer General Ledger Entries to Cost Entries
You can transfer general ledger entries to cost entries.  

Before you run the process for transferring general ledger entries to cost entries, you must prepare the transfer to avoid manual correction posting.  

## To prepare the transfer  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Cost Accounting Setup**, and then choose the related link.  
2.  In the **Cost Accounting Setup** window, verify that the **Starting Date for G/L Transfer** field is set to the correct value.  
3.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Cost Types**, and then choose the related link.  
4.  In the **Cost Type Card** window, verify that the **G/L Account Range** field is linked correctly for each cost type to take entries from the general ledger.  
5.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.  
6.  For each relevant general ledger account, in the **G/L Account Card** window, verify that the **Cost Type No.** field is linked correctly to a cost type. For more information, see [Defining the Relationship Between Cost Types and General Ledger Accounts](finance-defining-the-relationship-between-cost-types-and-general-ledger-accounts.md).  
7.  Verify that all relevant general ledger entries have dimension values that correspond to a cost center and a cost object.  

## To transfer general ledger entries to cost entries  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transfer GL Entries to CA**, and then choose the related link.  
2.  Choose the **Yes** button to start the transfer. The process transfers all general ledger entries that have not already been transferred.  

    During the transfer, the process creates connections in the entries in the **Cost Entry** table and the **Cost Register** table. This makes it possible to trace the source of cost entries.  

## See Also  
 [Criteria for Transferring General Ledger Entries to Cost Entries](finance-criteria-for-transferring-general-ledger-entries-to-cost-entries.md)   
 [Automatic Transfer and Combined Entries](finance-automatic-transfer-combined-entries.md)   
 [Results of the Transfer](finance-results-of-the-transfer.md)   
 [Transferring and Posting Cost Entries](finance-transfer-and-post-cost-entries.md)   
 [Defining the Relationship Between Cost Types and General Ledger Accounts](finance-defining-the-relationship-between-cost-types-and-general-ledger-accounts.md)   
