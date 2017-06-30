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
# How to: Block Shipment for Negative Inventory
You can block outbound shipment for an item when a transaction results in a negative inventory for that item.  
  
### To block shipment for negative inventory  
  
1.  In the **Search** box, enter **\($ N\_459 Sales & Receivable Setup $\)**, and then choose the related link.  
  
2.  In the **\($ N\_459 Sales & Receivable Setup $\)** window, on the **General** FastTab, select the **Block ship. when neg. invent.** check box.  
  
     When this check box is selected, the inventory for all items is calculated when you post a sales shipment. If the transaction leads to a negative quantity in inventory for an item, an error message appears.  
  
3.  Choose the **OK** button.  
  
## See Also  
 [\($ T\_311 Sales & Receivables Setup $\)](../\($%20T_311%20Sales%20&%20Receivables%20Setup%20$\).md)   
 Sales Shipment Line   
 Calculate Inventory