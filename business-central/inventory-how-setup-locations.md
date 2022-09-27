---
title: Set Up a Location Card and Define Transfer Routes (contains video)
description: If you buy, store, or sell items in more than one place, you can set up each place as a location. 
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, distribution center
ms.search.forms: 5703, 15
ms.date: 07/05/2022
ms.author: bholtorf

---
# Set Up Locations

Locations are places such as warehouses where you buy, store, or sell items. [!INCLUDE [prod_short](includes/prod_short.md)] uses locations to help keep track of inventory in both simple and complex warehouse processes.

You can then create document lines for a specific location, view availability by location, and transfer inventory between locations. For more information, see [Manage Inventory](inventory-manage-inventory.md).
<br><br>  
  
> [!Video https://www.microsoft.com/videoplayer/embed/RE4aQvq?rel=0]

## Location cards

You specify information about a location, such as a warehouse or distribution center, on the **Location Card** page. You give each location a name and a code that represents the location. You can then enter the location code in other parts of the program when you want to record transactions for a given location.  

You can enter information about bins and warehouse policies for each location. Based on your warehouse policies, you can use the options on the **Bins** FastTab to specify the bins to use by default for transactions. If you're using directed put-away and pick, the options on the **Bin Policies** FastTab let you define how to use advanced warehousing features.  

Some option fields depend on settings in the **Location Card** page to restrict unsupported setup combinations.  

Choose the **Zones** or **Bins** actions to view information about zones and bins that are defined for the location.

### To set up a location

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. Choose the **New** action.
3. On the **Location Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Repeat steps 2 and 3 for every location where you want to keep inventory.

> [!NOTE]  
> Many fields on the Location Card page are related to the handling of items in inbound and outbound warehouse processes. These fields are not relevant for companies that do not require complex warehouse functionality. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).

You can change the configuration of a location as long as it doesn't have item ledger entries.  

If you have multiple locations, you can define transfer routes between locations. For more information, see [To create a transfer route](inventory-how-setup-locations.md#to-create-a-transfer-route).

### To create a transfer route

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Routes**, and then choose the related link.
2. Choose the **New** action.
4. On the **Location Card** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

You can now transfer inventory items between two locations. For more information, see [Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md).    

## Bins

Bins represent the basic warehouse structure and can suggest where to put items. Your bins can have contents, or be floating bins without specific contents. 

To use the bin functionality at a location, on the **Location Card** page, on the **Warehouse** FastTab, turn on the **Bin Mandatory** toggle. You can design the item flow at the location by specifying bin codes in the fields for the warehouse processes on the **Bins** and **Bin Policies** FastTabs.

> [!NOTE]
> Before you can specify bin codes on a location, you must create bin codes. For more information, see [Create Bins](warehouse-how-to-create-individual-bins.md) and [Set Up Bin Types](warehouse-how-to-set-up-bin-types.md).  

## Zones

If you want to structure your bins under zones, you can do that in the **Zones** page. When you assign a zone to bins, [!INCLUDE [prod_short](includes/prod_short.md)] copies information from the zone to the bins. You can also choose to set up one zone and use bins alone to organize your warehouse. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).  

## Default Dimensions for Locations

You set default dimensions for a location on the **Location Card** page by choosing **Dimensions**. Afterward, the location's default dimensions are assigned to documents when you choose the location on a line. If needed, you can delete or change the dimension on the line. In the **Value Posting** field, you can require people to specify dimensions for locations before they can post an entry. If you want to allow people to choose only certain dimension values, you can specify the values in the **Allowed Values Filter** field. You can also include location dimension values on the **Default Dimension Priorities** page, and for combinations of priority and dimension rules on the **Dimension Combinations** page.

## See related training at [Microsoft Learn](/learn/modules/trade-set-up-dynamics-365-business-central/)

## See also

[Manage Inventory](inventory-manage-inventory.md)  
[Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md)  
[Create Bins](warehouse-how-to-create-individual-bins.md)  
[Set Up Bin Types](warehouse-how-to-set-up-bin-types.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Change Which Features are Displayed](ui-experiences.md)  
[General Business Functionality](ui-across-business-areas.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
