---
    title: How to: Set Up Corrective Invoicing | Microsoft Docs
    description: You can create corrective invoices and corrective credit memos to reflect changes in quantity and amounts after the items were shipped or received. First, you must set up [!INCLUDE[d365fin](../../includes/d365fin_md.md)] with prerequisites.
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
# How to: Set Up Corrective Invoicing
You can create corrective invoices and corrective credit memos to reflect changes in quantity and amounts after the items were shipped or received. First, you must set up [!INCLUDE[d365fin](../../includes/d365fin_md.md)] with prerequisites.  
  
### To set up number series for corrective documents  
  
1.  In the Navigation Pane, in the **Sales & Marketing** area, expand **Setup**, and then choose **Sales & Receivables Setup**.  
  
2.  In the **Sales & Receivables Setup** window, on the **Numbering** tab, specify the number series that must be used for posted corrective invoices and credit memos.  
  
### To set up inventory posting groups  
  
1.  In the Navigation Pane, in the **Financial Management** area, choose **Setup**, choose **Posting Groups**, and then choose **Inventory**.  
  
2.  In the **Inventory Posting Groups** window, in the **Sales Corr. Doc. Charge (Item)** field, select the item charge code that you want to use in in value entries to correct the original price of items in the corrective documents.  
  
     You can set up a separate code for each inventory posting group.  
  
## See Also  
 [Corrective Documents](corrective-documents.md)   
 Sales & Receivables Setup   
 Inventory Posting Groups