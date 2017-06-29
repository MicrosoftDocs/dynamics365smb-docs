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
# Perform Warehouse Activities
Warehouse activities are defined as the tasks involved in handling items that exist inside the warehouse, in accounting terms called "on inventory". [Receiving](../Receiving/receiving.md) and [shipping](../Topic/Shipping.md) are the surrounding inventory events reflecting the incoming and outgoing transactions. The in\-warehouse activities of putting away and picking are similar to receiving and shipping tasks. In large warehouses these different handling tasks can be separated by departments and the integration managed by a directed workflow. In simpler installations the flow is less formalized, and the warehouse activities are performed with so\-called inventory put\-aways and picks.  
  
 Other warehouse activities include, counting, adjusting, and reclassifying items and their serial\/lot numbers, as well as moving items between bins within a warehouse.  
  
 An in\-warehouse activity that is common in whole sale is to pick, assemble, and pack inventory items in kits just before selling the kit, or, alternatively, assembling kits to stock.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Put away items received from purchases, sales returns, transfers, or production output according to the defined warehouse activity flow.|[Put Items Away](../WarehouseActivities/put-items-away.md)|  
|Move items between bins.|[Move Items](../WarehouseActivities/move-items.md)|  
|Put sellable items together in simple steps to make a new item, such as a kit.|[Assemble Items](../WarehouseActivities/assemble-items.md)|  
|Pick items to be shipped, transferred, or consumed in production, according to the defined warehouse activity flow.|[Pick Items](../WarehouseActivities/pick-items.md)|  
|Count and report the physical inventory, manually increase or decrease inventory quantities, and change item attributes, such as dimensions and serial\/lot numbers.|[Count, Adjust, and Reclassify Inventory](../WarehouseActivities/count-adjust-and-reclassify-inventory.md)|  
  
## See Also  
 [Receiving](../Receiving/receiving.md)   
 [Shipping](../Topic/Shipping.md)   
 [Purchasing](../Purchasing/purchasing.md)   
 [Sales](../Sales/sales.md)   
 [Production](../Production/production.md)