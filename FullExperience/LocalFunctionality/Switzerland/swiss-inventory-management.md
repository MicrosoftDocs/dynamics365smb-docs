---
title: "Swiss Inventory Management"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "invoices with multiple shipments"
  - "inventory management, defined (Swiss)"
ms.assetid: cec8e9c5-db3a-4288-909a-60b3ec4ccc6f
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "de-ch"
  - "fr-ch"
---
# Swiss Inventory Management
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] includes Swiss enhancements to inventory management. This includes the following:  
  
-   Detailed reporting.  For more information, see the [\($ R\_712 Inventory \- Sales Statistics $\)](../Topic/\($%20R_712%20Inventory%20-%20Sales%20Statistics%20$\).md) report and the [\($ R\_701 Inventory \- List $\)](../Topic/\($%20R_701%20Inventory%20-%20List%20$\).md) report.  
  
-   The ability to track an invoice with multiple shipments.  
  
-   Including an item card location code as the default location code for sales lines and item journals. For more information, see [How to: Set Up Locations](../../DesignAndEngineering/how-to-set-up-locations.md) and the [\($ N\_30 Item Card $\)](../Topic/\($%20N_30%20Item%20Card%20$\).md) window.  
  
## Managing Item Details  
 Companies can have different warehouses for different product categories. In such cases, you must use the default location code retrieved from the item card. When you define a location code for an item, it is transferred to the sales lines and item journals as a default item location code. For more information, see the [\($ T\_37 Sales Line $\)](../Topic/\($%20T_37%20Sales%20Line%20$\).md) and the [\($ T\_83 Item Journal Line $\)](../Topic/\($%20T_83%20Item%20Journal%20Line%20$\).md) table.  
  
 You can provide an item description with up to 50 characters, and a tariff number with up to 15 characters. For more information, see the [\($ N\_30 Item Card $\)](../Topic/\($%20N_30%20Item%20Card%20$\).md) window.  
  
 Additional information, such as customer number, ship\-to address code, and customer sales person code, is stored in item ledger entries. This information helps you to create customized reporting criteria, such as revenue per customer, and item or sales provisions for sales people. For more information, see the [\($ T\_32 Item Ledger Entry $\)](../Topic/\($%20T_32%20Item%20Ledger%20Entry%20$\).md) table.  
  
### Invoices with Multiple Shipments  
 If multiple shipments have been posted for a customer, then you can create a combined invoice with the **Get Shipment Lines** function. For more information, see the [\($ N\_5708 Get Shipment Lines $\)](../Topic/\($%20N_5708%20Get%20Shipment%20Lines%20$\).md) window. When you use this function, the text created on the invoice lines includes information about the shipment number and the shipment date. For example, the text could appear as Shipment No. 102040 of 25.01.01. This allows you to easily track invoices with multiple shipments.  
  
## See Also  
 [How to: Block Shipment for Negative Inventory](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-block-shipment-for-negative-inventory.md)   
 [How to: Block Inventory Items for Sales or Purchases](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-block-inventory-items-for-sales-or-purchases.md)   
 [How to: Copy Existing Items to New Items](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-copy-existing-items-to-new-items.md)   
 [How to: Deactivate Item Cost Tracking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-deactivate-item-cost-tracking.md)   
 [Switzerland Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/switzerland-local-functionality.md)   
 [\($ R\_712 Inventory \- Sales Statistics $\)](../Topic/\($%20R_712%20Inventory%20-%20Sales%20Statistics%20$\).md)   
 [\($ R\_701 Inventory \- List $\)](../Topic/\($%20R_701%20Inventory%20-%20List%20$\).md)   
 [\($ N\_30 Item Card $\)](../Topic/\($%20N_30%20Item%20Card%20$\).md)   
 [\($ T\_27 Item $\)](../Topic/\($%20T_27%20Item%20$\).md)   
 [\($ T\_32 Item Ledger Entry $\)](../Topic/\($%20T_32%20Item%20Ledger%20Entry%20$\).md)   
 [\($ T\_83 Item Journal Line $\)](../Topic/\($%20T_83%20Item%20Journal%20Line%20$\).md)   
 [\($ T\_37 Sales Line $\)](../Topic/\($%20T_37%20Sales%20Line%20$\).md)   
 [How to: Set Up Locations](../../DesignAndEngineering/how-to-set-up-locations.md)   
 [\($ N\_5708 Get Shipment Lines $\)](../Topic/\($%20N_5708%20Get%20Shipment%20Lines%20$\).md)