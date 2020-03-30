---
    title: Swiss Inventory Management
    description: Swiss enhancements include special inventory management features.

    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Swiss Inventory Management
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] includes Swiss enhancements to inventory management. This includes the following:  

- Detailed reporting.  For more information, see the Inventory - Sales Statistics report and the Inventory - List report.  
- The ability to track an invoice with multiple shipments.  
- Including an item card location code as the default location code for sales lines and item journals. For more information, see [Set Up Locations](../../inventory-how-setup-locations.md).

## Managing Item Details  
Companies can have different warehouses for different product categories. In such cases, you must use the default location code retrieved from the item card. When you define a location code for an item, it is transferred to the sales lines and item journals as a default item location code. For more information, see the Sales Line and the Item Journal Line table.  

Additional information, such as customer number, ship-to address code, and customer sales person code, is stored in item ledger entries. This information helps you to create customized reporting criteria, such as revenue per customer, and item or sales provisions for sales people. For more information, see the Item Ledger Entry table.  

## Invoices with Multiple Shipments  
If multiple shipments have been posted for a customer, then you can create a combined invoice with the **Get Shipment Lines** function. For more information, see the Get Shipment Lines page. When you use this function, the text created on the invoice lines includes information about the shipment number and the shipment date. For example, the text could appear as Shipment No. 102040 of 25.01.01. This allows you to easily track invoices with multiple shipments.  

## See Also  
 [Switzerland Local Functionality](switzerland-local-functionality.md)   
 [Set Up Locations](../../inventory-how-setup-locations.md)
