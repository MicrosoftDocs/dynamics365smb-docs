---
title: "About Warehouse Management"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "bins, warehouse management overview"
  - "shipments, warehouse management overview"
  - "receipts, warehouse management overview"
  - "cycle counting, warehouse management overview"
  - "warehouse, journals"
  - "warehouse management, about"
  - "putting away, warehouse management overview"
  - "movements, warehouse management overview"
  - "picking, warehouse management overview"
ms.assetid: 4decca19-d1af-4357-af25-83e71f122c4d
caps.latest.revision: 3
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
# About Warehouse Management
With warehouse management, you can organize and handle the items in inventory on a bin level. Depending on your setup and the granules specified in your license, you can receive items and put them away in bins, pick and ship from bins, and move items between bins. The sections below describe the various features of warehouse management.  
  
## Bins  
 In the program, you can specify the zones and bins that you use in your warehouse. Once your zones and bins are established, you can specify which items are in those bins or you can fix an item to a bin, even if there is currently no quantity in the bin. Using these features in your daily warehouse activities of receiving, shipping, picking, and putting away, you will have a better overview of your inventory and its movements. The program has features that make organizing and using bins easier. Two of these are bin contents and bin creation worksheets, described below.  
  
### Bin Contents  
 In the **[\($ N\_7374 Bin Contents $\)](DynamicsNAV:////runpage?Page=7374)** window, you can view the contents of bins in the warehouse. Bin content entries exist for both bins that contain quantities of items and also for bins that do not yet contain any quantity of an item but that are fixed to a certain item. A bin is fixed to an item by placing a check mark in the **Fixed** field. Floating bins with nothing in them are not included in this window. At the bottom of the window is the calculated **Qty. on Adjustment Bin** field. This field is used when you are using directed put\-away and pick and shows, for each bin content \(item in a bin\) line, the sum of the adjustments currently in the adjustment bin for this bin content. Every time you register an adjustment in item quantity in a bin, you make a counterbalancing entry in the adjustment bin. When you post the adjustments to the item journal, the program makes entries in the adjustment bin to force the value in the **Qty. on Adjustment Bin** field to 0 and corresponding entries in the item ledger.  
  
### Bin Creation Worksheets  
 With the Bin Setup granule, instead of creating warehouse bins one by one, which can be a time\-consuming process, you can generate many similar bins all at once by using the bin creation worksheet. You must decide what kind of bins you want to include in the warehouse and make bin templates \(prototypes\/models\) that the program will copy when you create bins in the worksheet. You must also consider the most appropriate bin code numbering system, keeping in mind that one of the sorting methods for put\-aways, picks, and movements is the bin code. The bin creation process consists of three steps: first you calculate the bins according to the information you filled in on the worksheet, then you edit or cancel the results, and finally, when you are satisfied, you create the bins.  
  
## Receipts  
 Here, you receive items on the basis of source documents, plan cross\-docks, and post your item receipts, when your warehouse is set up to require warehouse receipt processing with warehouse documents. Under certain conditions, you can also create put\-away instructions for zones and bins. You can view the cross\-dock opportunities available at any given time and decide how many items you want to cross\-dock.  
  
 You use warehouse receipts to post the items you receive at the warehouse to the item ledger. When items arrive, you retrieve the lines of the source document that triggered their receipt, and fill in the quantities of the items you have received. If you have bins, you also record the receiving bin where you have placed the items. When you post the receipt, you either create a put\-away instruction or make the receipt lines available in the put\-away worksheet, depending on how the warehouse is set up.  
  
## Shipments  
 With warehouse shipments, you prepare shipments requested by source documents when your warehouse is set up to require shipment processing with warehouse documents. If your location requires pick processing, you can create pick instructions shipment by shipment, or you can release shipment lines to the pick worksheet where you can plan a more efficient pick round for a number of shipments. When employees have picked all the items, you can finish preparing the shipment and then post it.  
  
## Put\-aways and Picks  
 These two features contain the instructions that warehouse employees must follow when moving items around the warehouse. The warehouse put\-aways are used when the location is set up to require both warehouse receipt and warehouse put\-away processing, and warehouse picks are used when the location is set up to require both warehouse picking and warehouse shipment processing.  
  
 When your location is set up to use bins, the instructions suggest the bin from which you should take an item and the bin in which to put it. If you are using directed put\-away and pick, this suggestion is based on calculations the program makes using bin ranking or put\-away templates, depending on the activity. If you are not using directed put\-away and pick, the suggestion is based on the item's default bins. You can always modify the instructions the program has suggested.  
  
 If your warehouse is set up for directed put\-away and pick, you can use an automatic data capture system to facilitate putting away and picking items within the warehouse.  
  
### Pick Worksheets  
 If your location is set up to require both pick and shipment processing, you can plan and create pick instructions using the pick worksheet. The program retrieves lines that come from released documents \(including production orders\) that need to have items from the warehouse. Only lines that are not yet on pick instructions can be retrieved in the worksheet. When you have assembled and sorted a number of lines, you can create pick instructions from the worksheet.  
  
### Put\-away Worksheets  
 If your location is set up to require both put\-away and receipt processing, you can plan and create a put\-away instruction for several receipts in this worksheet. You can sort the receipt lines that you have retrieved in several different ways and thereby create instructions that reduce the time and effort warehouse employees use in putting items away. On the location card, the **Use Put\-Away Worksheet** field allows the warehouse to choose whether the program during posting of receipts will create put\-away instructions or make the lines available in the put\-away worksheet.  
  
### Cross\-Docking  
 The cross\-docking functionality, which is available if your location requires warehouse receipt and put\-away processing, allows you to quickly see the program's suggestion for the quantity to cross\-dock in the warehouse receipt. You can view, in a separate window, a list of the individual source document lines that formed the basis for the cross\-dock calculation. You can reduce or increase the quantity to cross\-dock before you post the receipt, or you can do this in the put\-away instruction. Cross\-docked items are not set aside for any specific outbound source document, but you can make an ordinary reservation using a short\-cut in the **Cross\-Dock Opportunity** window.  
  
 The program places cross\-docked items in one of the cross\-dock bins, which are the first bins that the program considers when picking items for shipment. Warehouses with bins also have information about cross\-docked items on each shipment line: when you add a line to a shipment, the program calculates how many items are available in the cross\-dock bin. If you are concerned about a back order that is waiting for one item, this information helps you to quickly see if the shipment can be completed.  
  
## Movements  
 Movements contain the instructions that warehouse employees must follow when moving items around the warehouse. The movement worksheet and movement documents are available when your location is set up to use directed put\-away and pick.  
  
 If your location is set up for directed put\-away and pick, you can use an automatic data capture system to facilitate moving items within the warehouse.  
  
### Movement Worksheets  
 If you are using directed put\-away and pick, you can use movement worksheets to calculate bin replenishment and review the replenishment lines suggested by the program before creating a movement instruction. You can also plan individual movements from bin to bin and then create a movement instruction. Unlike the other worksheets, this worksheet contains fields for both the zone and bin in which an item is currently located and the zone and bin to which it will be moved.  
  
## Internal Put\-aways and Internal Picks  
 With internal put\-aways and picks, you plan and create instructions for putting away and picking items without a source document. You can use these for many special purposes, including picking unplanned consumption for production and returning items not used in production to the warehouse, placing items to be used in a sales demonstration in a non\-pick type bin that is used for this purpose, or placing representative items in a quality control bin.  
  
 In the internal put\-away, if you are using bins, you enter the bin from which you want items to be taken, and create the put\-away instruction. If you are using directed put\-away and pick, the program then suggests, according to your warehouse's put\-away rules, the bin in which you should place the items. In the internal pick, you enter the bin in which you want items to be placed and create a pick instruction. If you are using directed put\-away and pick, when you create a pick from the internal pick, the program suggests the bin from which you should take the items, according to warehouse picking rules.  
  
## Warehouse Journals  
 The warehouse journals are similar to the inventory journals, except that they handle the items on a bin level. These journals are only available when the location is set up for directed put\-away and pick.  
  
### Warehouse Item Journal  
 The warehouse item journal is quite similar to the item journal in Inventory, but it only concerns quantity adjustments of items in the warehouse bins. If you observe a discrepancy in the number of items that should be in a bin, you enter the positive or negative adjustment quantity directly on the journal line and register the entry. The program adjusts the quantity of item in the bin to the actual quantity counted, and makes a corresponding \(but opposite in sign\) adjustment in the warehouse adjustment bin. Later on, someone with permissions in Inventory can post the adjustment in the item ledger by running the Calculate Whse. Adjustment function in the item journal.  
  
### Warehouse Reclassification Journal  
 In some situations, you might have to move items without first preparing an instruction document. In this case, you can register the movement in the reclassification journal by entering the item numbers, the quantity moved, the bins from which you took the items, and the bins in which you placed them. You can also use the reclassification journal in the process of restructuring your warehouse, if you need to do so.  
  
### Warehouse Physical Inventory Journal  
 If you are using directed put\-away and pick, you use the warehouse physical inventory journal when you want to count your inventory in the bins. When have counted all the bins with a particular item, you register the results as warehouse entries. A counterbalancing entry is created in the warehouse adjustment bin for any differences that have been registered and entries are made in the warehouse register to indicate that a physical inventory has been taken. You then create a physical inventory in the Inventory area for the same items as you counted in the warehouse physical inventory. When you run the Calculate Inventory function, the program fills in the quantity on the basis of the entries in the warehouse adjustment bin. You can now post the physical inventory. The quantity of the item in the warehouse corresponds to the quantity in the item ledger, and the physical inventory has been posted in the physical inventory ledger.  
  
## Cycle Counting  
 If you want to count some of your inventory at regular intervals, you can use the cycle counting functionality. You establish various counting periods and assign them to the items that you want to count on a periodic basis. When you want to conduct the first cycle count and you do not use directed put\-away and pick, you use the **[\($ N\_392 Phys. Inventory Journal $\)](DynamicsNAV:////runpage?Page=392)** window. If you do use directed put\-away and pick, you use the **[\($ N\_7326 Whse. Phys. Inventory Journal $\)](DynamicsNAV:////runpage?Page=7326)** window. You follow the procedures for cycle counting, including updating the counting period on the item card after you have counted the item throughout the warehouse. If you are using directed put\-away and pick, you must first register the cycle counting results in the warehouse physical inventory and then in the physical inventory journal in inventory.  
  
## Warehouse Adjustment Bin  
 When you are using directed put\-away and pick, the warehouse adjustment bin is the link between the warehouse and the rest of the program. Whenever a transaction occurs in the company that has an impact on inventory, or an activity in the warehouse\- other than posting of receipts or shipments \(which by definition create entries in the item ledger\)\- that has an impact on the item ledger, the program makes an entry in the adjustment bin. Sometimes entries cancel each other out within a short period of time \(for example, items misplaced yesterday are found today\), but at regular points in time, the quantities in the adjustment bin are posted in the item journal, so that the physical count of items in the warehouse is the same as the quantities in the item ledger.  
  
## Registered Documents  
 You can find records of all completed internal warehouse instruction documents: registered put\-aways, picks, and movements. These documents do not create entries in the item ledger, but can be important short\-term records of warehouse activity. The program stores them automatically, and you can view them in the menu items, but you might choose to delete them when you no longer need to refer to them. You can delete them one by one or in a batch job.  
  
## Source Documents  
 Items arrive at or leave a warehouse location on the basis of decisions made elsewhere in the company. The details of these decisions are recorded in source documents, which are released to the warehouse before items can be received or shipped. The source documents for receipts are purchase orders, sales return orders, or inbound transfers. The source documents for shipments are sales orders, purchase return orders, or outbound transfers.  
  
 The technical interface between the source documents and the warehouse is the **Warehouse Request** table, which the user cannot view directly. The program creates entries in this table when you release any of the source documents mentioned above, or when production in the same location plans consumption or output of items in the warehouse.  
  
 You can track the progress of source documents released to the warehouse. In the source document, click Order and then Whse. Receipt Lines or Whse. Shipment Lines, depending on whether a receipt or a shipment is the expected outcome of the source document. You can then view any shipment lines or receipt lines that have been created in the warehouse, if any. If there are no lines, the items have not yet arrived in the case of receipts, or the warehouse has not yet begun to prepare the shipment.  
  
## Automatic Data Capture Systems \(ADCS\)  
 If you want to register electronically the placement of items within the warehouse and your warehouse is set up for directed put\-away and pick, you can use the automatic data capture system, which is designed to operate with handheld devices. The ADCS allows you to register the movements of items as soon as they are made.  
  
## See Also  
 [How to: Receive Items](../Receiving/how-to-receive-items.md)   
 [How to: Cross\-Dock Items](../Receiving/how-to-cross-dock-items.md)   
 [How to: Put Items Away with Warehouse Put\-aways](../WarehouseActivities/how-to-put-items-away-with-warehouse-put-aways.md)   
 [How to: Pick Items for Warehouse Shipment](../WarehouseActivities/how-to-pick-items-for-warehouse-shipment.md)   
 [How to: Prepare Shipments](../Topic/How%20to:%20Prepare%20Shipments.md)