---
title: "Count, Adjust, and Reclassify Inventory"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "adjusting, inventory"
  - "inventory, reclassifying"
  - "reclassifying, inventory"
  - "inventory, counting"
  - "inventory, adjustments"
  - "counting, inventory"
ms.assetid: 581a4ce7-9687-43b9-80aa-b353e336d0ec
caps.latest.revision: 5
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Count, Adjust, and Reclassify Inventory
At least once every fiscal year you must take a physical inventory, that is, count all the items on inventory, to see if the quantity registered in the database is the same as the actual physical quantity in the warehouses. When the actual physical quantity is known, it must be posted to the general ledger as a part of period\-end [valuation of inventory](../Finance/report-costs-and-reconcile-with-the-general-ledger.md).  
  
 If you need to adjust recorded inventory quantities, in connection with counting or for other purposes, you can use an item journal to change the inventory ledger entries directly without posting business transactions.  
  
 If you need to change attributes on item ledger entries as well as the quantities, you can use the item reclassification journal. Typical attributes to reclassify include serial\/lot numbers, expiration dates, and variant codes.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Learn how the warehouse adjustment bin functions as a means to synchronize warehouse entries \(made in warehouse activities\), with item ledger entries.|[Warehouse Adjustment Bin](../WarehouseActivities/warehouse-adjustment-bin.md)|  
|Periodically synchronize warehouse entries, created from warehouse activities, with the related item ledger entries, especially prior to counting physical inventory.|Calculate Whse. Adjustment|  
|In locations configured for directed put away and pick, make a physical count of items represented by warehouse entries only.|[How to: Perform Warehouse Physical Inventories](../WarehouseActivities/how-to-perform-warehouse-physical-inventories.md)|  
|Prepare an inventory counting process by compiling all the inventory quantities that are recorded in the database, the expected inventory.|[How to: Perform a Physical Inventory](../DesignAndEngineering/how-to-perform-a-physical-inventory.md)|  
|Count physical inventories at regular intervals.|[How to: Perform Cycle Counting](../WarehouseActivities/how-to-perform-cycle-counting.md)|  
|Create initial item ledger entries, for example, in connection with a new installation.|[How to: Register Opening Item Entries](../DesignAndEngineering/how-to-register-opening-item-entries.md)|  
|Increase or decrease inventory quantities directly without posting business documents.|Item Journal|  
|Save and reuse item journal lines for recurring postings, such as material consumption, in installations without production features.|[Save as Standard Journal](../Finance/how-to-save-standard-journals.md) and [Get Standard Journals](../DesignAndEngineering/how-to-reuse-standard-journals.md)|  
|Record any observed differences in bin quantity as they occur to keep a record of how many items exist in the warehouse \- until synchronizing with the item ledger entries with the warehouse adjustment bin.|[How to: Register Quantity Adjustments in Warehouse Item Journals](../WarehouseActivities/how-to-register-quantity-adjustments-in-warehouse-item-journals.md)|  
|Change the quantity \(of warehouse entries\) in bins while observing the requirements to synchronize with inventory quantities.|[How to: Post Quantity Adjustments for Bins](../WarehouseActivities/how-to-post-quantity-adjustments-for-bins.md)|  
|Assign a different bin to an item than the default bin defined by the first place where the item was put away.|[How to: Change Default Bins for Items](../WarehouseActivities/how-to-change-default-bins-for-items.md)|  
|Update the details of a bin content entry.|[How to: Modify Bin Content](../WarehouseActivities/how-to-modify-bin-content.md)|  
|Change item attributes, such as serial\/lot numbers and variant codes.|Item Reclass. Journal|  
|Change serial\/lot numbers on item ledger entries and warehouse entries.|[How to: Reclassify Lot Numbers and Serial Numbers](../DesignAndEngineering/how-to-reclassify-lot-numbers-and-serial-numbers.md)|  
|Use a dedicated warehouse reclassification journal to change warehouse entry attributes, such as bin codes and serial\/lot numbers.|"Restructure Your Warehouse when Using Directed Put\-away and Pick" in [Restructuring Your Warehouse](../WarehouseActivities/how-to-restructure-warehouses.md)|  
  
## See Also  
 [Design and Engineering](../DesignAndEngineering/design-and-engineering.md)   
 [Perform Warehouse Activities](../WarehouseActivities/perform-warehouse-activities.md)   
 [Set Up Inventory Valuation and Costing](../Finance/set-up-inventory-valuation-and-costing.md)