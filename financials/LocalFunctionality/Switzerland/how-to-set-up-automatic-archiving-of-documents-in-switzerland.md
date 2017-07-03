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
# How to: Set Up Automatic Archiving of Documents in Switzerland
You can set up automatic archiving of sales documents and purchase documents—such as quotes, blanket orders, and orders—before you delete documents.  
  
 The following procedure describes how to set up automatic archiving of sales documents, but the same steps apply to purchase documents.  
  
### To set up automatic archiving of documents  
  
1.  In the **Search** box, enter **Sales & Receivables Setup**, and then choose the related link.  
  
2.  On the **Sales & Receivables Setup** window, on the **Archiving** FastTab, fill in the fields as described in the following table.  
  
    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Archiving Sales Quote**|**Never** to never archive sales quotes when they are deleted.<br /><br /> –or–<br /><br /> **Question** to prompt the user to choose whether to archive sales quotes when they are deleted.<br /><br /> –or–<br /><br /> **Always** to archive sales quotes automatically when they are deleted.|  
    |**Archiving Blanket Sales Orders**|Select to archive blanket sales orders automatically each time they are deleted.|  
    |**Arch. Orders and Ret. Orders**|Select to automatically archive sales orders each time they are deleted.|  
    |**Automatic Interaction Log**|Select to automatically create an entry for the contact in the interaction log when a sales order or partial shipment is posted, or when a sales quote is converted into a sales order. **Note:**  This field is not available on the **Purchases & Payables Setup** page.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 [Swiss Purchase Documents and Sales Documents](swiss-purchase-documents-and-sales-documents.md)   
 Sales & Receivables Setup   
 [How to: Import Swiss Post Codes](how-to-import-swiss-post-codes.md)   
 [How to: Print an Inventory Picking List from a Sales Order](how-to-print-an-inventory-picking-list-from-a-sales-order.md)   
 [How to: Print Sales and Purchase Orders During Batch Posting](how-to-print-sales-and-purchase-orders-during-batch-posting.md)