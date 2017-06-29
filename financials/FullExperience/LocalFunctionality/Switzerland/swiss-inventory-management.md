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
ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> includes Swiss enhancements to inventory management. This includes the following:  
  
-   Detailed reporting.  For more information, see the Inventory \- Sales Statistics report and the Inventory \- List report.  
  
-   The ability to track an invoice with multiple shipments.  
  
-   Including an item card location code as the default location code for sales lines and item journals. For more information, see [How to: Set Up Locations](../../DesignAndEngineering/how-to-set-up-locations.md) and the Item Card window.  
  
## Managing Item Details  
 Companies can have different warehouses for different product categories. In such cases, you must use the default location code retrieved from the item card. When you define a location code for an item, it is transferred to the sales lines and item journals as a default item location code. For more information, see the Sales Line and the Item Journal Line table.  
  
 You can provide an item description with up to 50 characters, and a tariff number with up to 15 characters. For more information, see the Item Card window.  
  
 Additional information, such as customer number, ship\-to address code, and customer sales person code, is stored in item ledger entries. This information helps you to create customized reporting criteria, such as revenue per customer, and item or sales provisions for sales people. For more information, see the Item Ledger Entry table.  
  
### Invoices with Multiple Shipments  
 If multiple shipments have been posted for a customer, then you can create a combined invoice with the **Get Shipment Lines** function. For more information, see the Get Shipment Lines window. When you use this function, the text created on the invoice lines includes information about the shipment number and the shipment date. For example, the text could appear as Shipment No. 102040 of 25.01.01. This allows you to easily track invoices with multiple shipments.  
  
## See Also  
 [How to: Block Shipment for Negative Inventory](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-block-shipment-for-negative-inventory.md)   
 [How to: Block Inventory Items for Sales or Purchases](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-block-inventory-items-for-sales-or-purchases.md)   
 [How to: Copy Existing Items to New Items](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Austria/how-to-copy-existing-items-to-new-items.md)   
 [How to: Deactivate Item Cost Tracking](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-deactivate-item-cost-tracking.md)   
 [Switzerland Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/switzerland-local-functionality.md)   
 Inventory \- Sales Statistics   
 Inventory \- List   
 Item Card   
 Item   
 Item Ledger Entry   
 Item Journal Line   
 Sales Line   
 [How to: Set Up Locations](../../DesignAndEngineering/how-to-set-up-locations.md)   
 Get Shipment Lines