---
title: Set up item tracking with serial, lot, and package numbers
description: Set up item tracking with serial numbers, lot numbers, and package numbers
author: brentholtorf
ms.author: bholtorf    
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/24/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Set up item tracking with serial, lot, and package numbers

Keep track of inventory items, even in complex warehouse configurations, by assigning numbers that are specific to each item. You can use numbers for individual objects, lots, or packages. With item tracking, you can trace items across internal warehouse movements, and outbound and inbound documents.

Items with serial and lot numbers can be traced both backwards and forward in the supply chain. Tracing is useful for general quality assurance and for product recalls. For more information, see [Trace Item-Tracked Items](inventory-how-to-trace-item-tracked-items.md).  

## Numbers and item tracking

As part of your warehouse processes, you can bundle your stock in packages, boxes, containers, and so on. But in order to keep track of the items, you assign unique numbers as identification. For example, you manufacture and sell a chair that has the item number *1900-S*. Each chair has a serial number, *1001*, but you also bundle four chairs into a lot, *LOT0001*. You also ship the chairs in a container with the package number *CONTAINER010* that also includes *LOT0100* with side tables, and *LOT200* with lamps.  

Depending on your configuration, you use these different numbers to keep track of inventory in [!INCLUDE [prod_short](includes/prod_short.md)] at the various stages of purchasing, sales, warehouse operations, and so on.

## To set up item tracking codes

An item tracking code reflects the different considerations a company has regarding the use of serial and lot numbers for items moving through the inventory.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Tracking Codes**, and then choose the related link.  
2. Choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. On the **Serial No.**, **Lot No.**, and the **Package Tracking** FastTabs, define policies of item tracking by serial, lot, and package numbers respectively.  

> [!NOTE]  
> If you want to track specific items or specific lots throughout their lifetime, you must choose the **SN Specific Tracking**, **Lot Specific Tracking**, and **Package Specific Tracking** fields, respectively. As a result, when you handle an outbound unit of an item with this item tracking code, you must always specify which serial number or lot number to handle. This means that when you sell a unit of the item, it must be applied against a specific pool of serial numbers or lot numbers. In other words, the serial, lot, or package number assigned to the item when it enters inventory must follow the item when it leaves inventory.

Because these setup fields cover all possible transactions with the item, the individual inbound/outbound fields are selected. However, the individual inbound/outbound fields have nothing to do with application across inventory. They merely define your company's work flow concerning when to assign item tracking numbers.  

> [!NOTE]  
> To assign item tracking numbers in warehouse activities, the **SN Warehouse Tracking** and **Lot Warehouse Tracking** fields must be selected on the item's item tracking code card.  

## To set up expiration rules for serial or lot numbers

For some items, you might want to set up specific expiration dates and rules in the item tracking code. This functionality allows you to keep track of when specific serial numbers and lot numbers expire.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Tracking Codes**, and then choose the related link.
2. Select an existing item tracking code, and then choose the **Edit** action.  
3. On the **Misc.** FastTab, select the following fields:  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Strict Expiration Posting**|Specifies that the expiration date for the item tracking number when it entered inventory is respected when it exits inventory.|  
    |**Require Expiration Date Entry**|Specifies that you must enter an expiration date on the item tracking line.|  
    |**Use Expiration Dates**|Specifies that you want to calculate expiration dates. |  

## To set up warranties for serial or lot numbers

For some items, you might want to set up specific warranties in the item tracking code. This functionality allows you to keep track of when the warranties on specific serial or lot numbers in your inventory expire.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Tracking Codes**, and then choose the related link.  
2. Select an existing item tracking code, and then choose the **Edit** action.  
3. On the **Misc.** FastTab, fill in the **Warranty Date Formula** field, and then select the fields as follows:  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Warranty Date Formula**|Specifies the last day of warranty for the item.|  
    |**Require Warranty Date Entry**|Specifies that you must manually enter a warranty date on the item tracking line.|  

## To set up items for tracking with the correct item tracking codes

To enable item tracking, you first have to assign the item tracking codes to an item. There are two ways to add item tracking codes, by selecting the code from a predefined list or by assigning a new unique code. Hover over the fields to read a short description.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item**, and then choose the related link.
2. Select an existing item from the list, and open the **Item Card** page.  
3. On the **Item Tracking** FastTab, assign the appropriate item tracking codes and choose the **Item Tracking Code**, the **Serial Nos.**, and the **Lot Nos.**.
    1. Alternatively you can also create a new item tracking code by selecting the **New** action.

## To specify opening balances for the items, you track

You can create opening balances for the items you track. Because you can choose different warehouse configurations, there are two options:

* Enable specific batches on the **Item Journal** page to let people enter serial, lot, and package data directly on journal lines.
* For locations where the **Directed Put-away and Pick** toggle is turned on, use the **Warehouse Physical Inventory Journal** page to make all item tracking fields available. The fields that are available include the **Warranty Date** and **Expiration Date** fields.

### Item journals

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Journals**, and then choose the related link.
2. To open a list of item journal batches, choose the **Name** field.
3. Choose **New** to create a new batch, and then turn on the **Item Tracking on Lines** toggle.
4. Choose **OK** to select the batch you created.
5. Fill in the fields on the item journal line as necessary. The **Lot No.**, **Serial No.**, **Expiration Date**, **Warranty Date**, and **Package No.** fields are available if you enabled item tracking.
    1. Alternatively choose the **Edit in Excel** action. Using Excel lets you quickly fill in columns, including **Serial No.**, **Lot No.**, **Package No.**, **Expiration Date**, and **Warranty Date**. When you're done, choose **Publish** to send changes to [!INCLUDE [prod_short](includes/prod_short.md)].
6. Choose the **Post** action to adjust inventory.

> [!NOTE] 
> [!INCLUDE [prod_short](includes/prod_short.md)] does a few minor validations when you enter or import data. A more comprehensive check happens when you post or transfer data from journal lines to the **Item Tracking** page. The latter happens automatically when you open the **Item Tracking** page from the item journal line or if you choose the **Update Item Tracking Lines** action.

### Warehouse physical inventory journal for locations where directed pick and put-away is turned on  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Physical Inventory Journal**, and then choose the related link.
2. Fill in the fields on the item journal line as necessary. The **Lot No.**, **Serial No.**, **Expiration Date**, **Warranty Date**, and **Package No.** fields are available if you enabled item tracking.
3. Choose the **Register** action to make the inventory adjustments. Remember to synchronize the adjusted warehouse entries with the related item ledger entries. To learn more, go to [synchronize the adjusted warehouse entries](/dynamics365/business-central/inventory-how-count-adjust-reclassify#to-synchronize-the-adjusted-warehouse-entries-with-the-related-item-ledger-entries).

For bulk imports, use configuration packages to import data to the journals.

## Related information

[Work with Serial and Lot Numbers](inventory-how-work-item-tracking.md)  
[Trace Item-Tracked Items](inventory-how-to-trace-item-tracked-items.md)  
[Inventory](inventory-manage-inventory.md)  
[Design Details: Item Tracking](design-details-item-tracking.md)  
[Design Details - Item Tracking and Reservations](design-details-item-tracking-and-reservations.md)  
[Reserve Items](inventory-how-to-reserve-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
