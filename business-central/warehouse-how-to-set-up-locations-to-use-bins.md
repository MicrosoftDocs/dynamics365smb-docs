---
title: How to Set Up Locations to Use Bins
description: Bins represent the basic warehouse structure and are used to make suggestions about the placement of items. 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/28/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Set Up Locations to Use Bins

Bins represent the basic warehouse structure, and you use them to suggest where to place items. After you create your bins you define their contents, or let them serve as floating bins without specific contents.

To use the bin functionality at a location, turn on the **Bin Mandatory** toggle on the **Location** card. After you turn on the toggle, the **Bin Code** and **Zone Code** fields are available on the following documents:

* Warehouse receipt header
* Warehouse receipt lines
* Warehouse put-away lines
* Warehouse shipment header
* Warehouse shipment lines
* Warehouse put-away lines

The next step is to design the item flow at the location by specifying bin codes in setup fields that represent the different flows.  

> [!NOTE]  
> You must create bin codes before you can specify them for the location. For more information, see [Create Bins](warehouse-how-to-create-individual-bins.md).  

## To set up a location to use bins

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.  
2. Select the location where you want to use bins.  
3. Choose the **Edit** action.  
4. On the **Warehouse** FastTab, select the **Bin Mandatory** checkbox.  
5. If you aren't using directed put-away and pick for the location, in the **Default Bin Selection** field, choose the method you want [!INCLUDE [prod_short](includes/prod_short.md)] to use to assign a default bin to an item.  
6. Open the card for the location that you want to set up bins for.
7. On the **Bins** FastTab, select the bins to use as the default for receipts, shipments, inbound, outbound, and open shop floor bins.  

    The bin codes you specify appear automatically on the headers and lines of various warehouse documents. The default bins define all starting or ending placements of items in the warehouse.  
8. If you're using directed put-away and pick, select a bin for warehouse adjustments. The bin code in the **Adjustment Bin Code** field defines the virtual bin in which to record discrepancies in inventory:

    * When you observe differences registered in the warehouse item journal
    * Differences calculated when you register a warehouse physical inventory  
9. Optional: Fill in the fields on the **Bin Policies** FastTab. The most important fields are **Bin Capacity Policy**, **Allow Breakbulk**, and **Put-away Template Code** fields.  
10. On the **Warehouse** FastTab, fill in the **Outbound Whse. Handling Time**, **Inbound Whse. Handling Time**, and the **Base Calendar Code** fields. To learn more, go to [Set Up Base Calendars](across-how-to-assign-base-calendars.md).

## Fill in the consumption bin

The following flow chart shows how the **Bin Code** field on production order component lines is filled in according to your location setup.

:::image type="content" source="media/binflow.png" alt-text="Bin code field on production order component lines.":::

## Related information

[Warehouse Management Overview](design-details-warehouse-management.md)
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
