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
# How to: Select from Existing Serial Numbers and Lot Numbers
When you are working with items that require item tracking and you are creating outbound transactions, where the items go out of inventory, you typically need to select the lot or serial numbers from those that already exist in inventory.  
  
 The exact rules for handling item tracking numbers across your company are governed by the setup of the **Item Tracking Code** table.  
  
> [!NOTE]  
>  To handle item tracking numbers in warehouse activities, the item must be set up with SN\/Lot Warehouse Tracking, as this dictates the special principles governing serial and lot numbers in the warehouse.  
  
### To select from existing serial or lot numbers  
  
1.  From any outbound document, select the line that you want to select serial or lot numbers for.  
  
2.  On the **Lines** FastTab, choose **Actions**![Action Menu icon](../DesignAndEngineering/media/actionmenuicon.png "actionMenuIcon"), choose **Line** or **Item**, and then choose **Item Tracking Lines**.  
  
3.  In the **Item Tracking Lines** window, you have three options for specifying lot or serial number:  
  
    -   Select the **Lot No.** or **Serial No.** field and select a number from the **Item Tracking Summary** window.  
  
    -   On the **Actions** tab, in the **Functions** group, choose **Select Entries**. The **Select Entries** window shows all lot or serial numbers along with availability information. In the **Selected Quantity** field, enter the quantity of each lot or serial number that you would like to use.   
        Choose the **OK** button, and the selected item tracking information is transfered to the **Item Tracking Lines** window.  
  
    -   Type or scan in the item tracking number.  
  
 The matrix of quantity fields in the header dynamically displays the quantities and sums of the item tracking numbers you define in the window. The quantities must correspond to those of the document line, which is signified by **0** in the **Undefined** fields.  
  
 When you post the document line, the the item tracking information is transfered to the associated item ledger entries.  
  
## See Also  
 [Item Tracking Availability](../DesignAndEngineering/item-tracking-availability.md)   
 [How to: Assign Serial Numbers and Lot Numbers During Outbound Transactions](../WarehouseActivities/how-to-assign-serial-numbers-and-lot-numbers-during-outbound-transactions.md)   
 Item Tracing