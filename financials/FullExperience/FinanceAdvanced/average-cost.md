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
# Automatic Transfer and Combined Entries
In cost accounting, you can transfer general ledger entries to a cost type by using a combined posting. You can specify if a cost type receives combined entries in the **Combine Entries** field in the cost type definition. The following table describes the different options.  
  
|Combine entries|Description|  
|---------------------|-----------------|  
|None|Each general ledger entry is transferred individually to the corresponding cost type.|  
|Day|General ledger entries with the same posting date are transferred as one entry to the corresponding cost type.|  
|Month|All general ledger entries in the same calendar month are transferred as one entry to the corresponding cost type.|  
  
> [!IMPORTANT]  
>  If you have selected the **Auto Transfer from G\/L** check box in the **Cost Accounting Setup** window, ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> updates the cost accounting after every posting in the general ledger. Combined entries are not possible.  
  
## See Also  
 [How to: Transfer General Ledger Entries to Cost Entries](../Finance/how-to-transfer-general-ledger-entries-to-cost-entries.md)   
 [Criteria for Transferring General Ledger Entries to Cost Entries](../Finance/criteria-for-transferring-general-ledger-entries-to-cost-entries.md)   
 [Results of the Transfer](../Finance/results-of-the-transfer.md)   
 [Transfer and Post Cost Entries](../Finance/transfer-and-post-cost-entries.md)   
 Cost Accounting Setup