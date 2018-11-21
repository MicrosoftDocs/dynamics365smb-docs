---
    title: Automatic Transfer and Combined Entries | Microsoft Docs
    description: In cost accounting, you can transfer general ledger entries to a cost type by using a combined posting. You can specify if a cost type receives combined entries in the **Combine Entries** field in the cost type definition. The following table describes the different options.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 11/13/2018
    ms.author: sgroespe
    redirect_url: finance-transfer-and-post-cost-entries

---
# Automatic Transfer and Combined Entries
In cost accounting, you can transfer general ledger entries to a cost type by using a combined posting. You can specify if a cost type receives combined entries in the **Combine Entries** field in the cost type definition. The following table describes the different options.  

|Combine entries|Description|  
|---------------------|-----------------|  
|None|Each general ledger entry is transferred individually to the corresponding cost type.|  
|Day|General ledger entries with the same posting date are transferred as one entry to the corresponding cost type.|  
|Month|All general ledger entries in the same calendar month are transferred as one entry to the corresponding cost type.|  

> [!IMPORTANT]  
>  If you have selected the **Auto Transfer from G/L** check box in the **Cost Accounting Setup** page, [!INCLUDE[d365fin](includes/d365fin_md.md)] updates the cost accounting after every posting in the general ledger. Combined entries are not possible.  

## See Also  
 [Transferring and Posting Cost Entries](finance-transfer-and-post-cost-entries.md)   
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
