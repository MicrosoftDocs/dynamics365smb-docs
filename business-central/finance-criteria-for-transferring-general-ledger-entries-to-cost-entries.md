---
    title: Criteria for Transferring General Ledger Entries to Cost Entries | Microsoft Docs
    description: It is important to understand the criteria for transferring general ledger entries to cost entries. During the transfer, the **Transfer GL Entries to CA** batch job uses the following criteria to determine if and how the general ledger entries are transferred.
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
# Criteria for Transferring General Ledger Entries to Cost Entries
It is important to understand the criteria for transferring general ledger entries to cost entries. During the transfer, the **Transfer GL Entries to CA** batch job uses the following criteria to determine if and how the general ledger entries are transferred.  

General ledger entries are transferred if:  

-   The entries have dimension values corresponding to either a cost center or a cost object.  
-   The entries have dimension values that correspond to a cost center and a cost object. For these entries, the cost center takes precedence. This helps avoid a situation where a cost type appears in both a cost object and a cost center and is therefore counted twice in the statistics.  
-   The document number in the entries is empty, so it will appear with a document number of 0000 in the cost entries.  
-   The entries are transferred to a cost type that allows for combined entries and these entries are transferred as a combined entry either monthly or daily.  

General ledger entries are not transferred if:  

-   The entries have dimension values that do not correspond to a cost center or a cost object.  
-   The entries have an amount of zero.  
-   The entries have a general ledger account that has been deleted.  
-   The entries have a general ledger account that is not of the type **Income Statement**.  
-   The entries have a general ledger account that is not assigned a cost type.  
-   The entries have a posting date before the **Starting Date for G/L Transfer**.  
-   The entries have been posted with a closing date. These are typically entries that set back the balance of the income statement at the end of the year.  

## See Also  
[Accounting for Costs](finance-manage-cost-accounting.md)  
 [Transfer General Ledger Entries to Cost Entries](finance-how-to-transfer-general-ledger-entries-to-cost-entries.md)   
 [Transferring and Posting Cost Entries](finance-transfer-and-post-cost-entries.md)   
 [About Cost Accounting](finance-about-cost-accounting.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
