---
title: Get an Availability Overview| Microsoft Docs
description: You can get information about the availability of items or stock across locations, per sales or purchase events, by a time period, or by the item's position on an assembly or production BOM.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: stock
ms.date: 04/01/2020
ms.author: SorenGP

---
# View the Availability of Items
From the context of a business task, you can get advanced information about when and where an item is available, such as when talking to a customer about a delivery date.

You can view the availability of all items per location, and you can view the availability of each item by event, by period, or by location. An event is any scheduled item transaction, such as a sales shipment or an inbound transfer receipt.

> [!NOTE]  
>   Availability views by location require that you maintain inventory at more than one location. For more information, see [Set Up Locations](inventory-how-setup-locations.md).

If you use warehousing functionality, availability varies depending on allocations at the bin level when warehouse activities such as picks and movements occur and when the inventory reservation system imposes restrictions to comply with. A rather complex algorithm verifies that all conditions are met before allocating quantities to picks for outbound flows. For more information see [Design Details: Availability in the Warehouse](design-details-availability-in-the-warehouse.md).

In [!INCLUDE[d365fin](includes/d365fin_md.md)], availability figures are typically shown in two different fields, each with a different definition:

* The **Quantity on Hand** field, in some places named **Inventory**, shows the actual quantity today according to posted item ledger entries.
* The **Projected Available Balance** field is calculated and shows the quantity on hand plus scheduled receipts minus gross requirements. (In [!INCLUDE[d365fin](includes/d365fin_md.md)], scheduled receipts include quantities on purchase orders and inbound transfer orders. Gross requirements include quantities on sales orders and outbound transfer orders.)

> [!TIP]  
>   The projected available balance is especially relevant to view in the **Item Availability by Periods** and **Item Availability by Event** pages as they contain the date dimension.  

> [!NOTE]  
>   The following procedures describe how to view advanced availability information from the items list and item card. You can also access the information from sales document lines, for the item on the line. For more information, see [Sell Products](sales-how-sell-products.md).

## To view the availability of an item according to when it will be received or shipped
You view the availability of an item according to scheduled item transactions on the **Availability by Event** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card of an item that you want to view availability for.
3. Choose the **Item Availability by** action, and then choose the **Event** action.

    The **Item Availability by Event** page shows how the inventory quantity of the item will develop over time according scheduled shipment and receipt events. The page gives a condensed view that shows one line of accumulated information per time interval in which inventory quantities change. Time intervals where no events occurred are not shown. You can expand each line to show details about the event or events that caused the accumulated quantity on the line.
4. Choose the value in the **Projected Available Balance** field to view the item ledger entries or open documents that make up the value.

## To view the availability of an item in different periods
You view the availability of an item over time for specified time periods on the **Item Availability by Periods** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card of an item that you want to view availability for.
3. Choose the **Item Availability by** action, and then choose the **Period** action.

    The **Item Availability by Periods** page shows how the inventory quantity of the item will develop over time, shown for a period that you select, such as Day, Week, or Quarter.
4. Choose the value in the **Projected Available Balance** field to view the item ledger entries or open documents that make up the value.

## To view the availability of an item at the locations where it is stored
You view the availability of an item at the different places where it is stored on the **Item Availability by Location** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card of an item that you want to view availability for.
3. Choose the **Item Availability by** action, and then choose the **Location** action.

    The **Item Availability by Location** page shows how the inventory quantity of the item will develop in the future, shown for each location where it is stored.
4. Choose the value in the **Qty. on Hand** field to view the item ledger entries that make up the value.
5. Choose the value in the **Projected Available Balance** field to view the item ledger entries or open documents that make up the value.

## To view the availability of all items by the location where they are stored
You view the availability of all your items across all your locations on the **Items by Location** page.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Choose the **Items by Location** action.

    The **Items by Location** page shows for all your items how many are available at each location.
3. Choose the value in the **Qty. on Hand** field to view the item ledger entries that make up the value.

## To view the availability of an item by its use in assembly or production BOMs
If an item exists in assembly or production BOMs, either as a parent item or as a component, then you can view how many units of its are required on the **Item Availability by BOM Level** page. The page shows how many units of a parent you can make based on the availability of child items on underlying lines. Any item that has an assembly or production BOM is shown on the page as a collapsible line. You can expand this line to see the underlying components and lower-level subassemblies with their own BOMs.

You can use the page to find out whether you can fulfill a sales order for an item on a specified date by looking at its current availability and the quantities that can be supplied by its components. You can also use the page to identify bottlenecks in related BOMs.

On each line on the page for both parent items and child items, the following key fields specify the availability figures. You can use these figures to promise how many units of a parent you can supply if you start the related assembly process.

|Field|Description|
|------|-----------|
|**Able to Make Parent**|Shows how many units of any subassembly in the top item you can make. The field specifies how many immediate parent units you can assemble. The value is based on availability of the item on the line.|
|**Able to Make Top Item**|Shows how many units of the top item you can make. The field specifies how many units of the top-line BOM item you can assemble. The value is based on availability of the item on the line.|

### To view the availability of an item according to demand for its parent
The **Item Availability by BOM Level** page shows information for the item on the card or document line that the page is opened for. The item is always shown on the top line. You can view information for other items or for all items by changing the value in the **Item Filter** field.

> [!NOTE]  
>   By default, availability figures on the lines show the total availability of all items under the top item. These figures are displayed in the **Available Quantity** field, and the focus is on the top item. However, information about how many subassemblies you can make may be skewed. To get a true indication of how many of the shown subassemblies you can make, you must clear the **Show Total Availability** check box and then see the figure in the **Able to Make Parent** field.

The **Bottleneck** field specifies which item in the BOM structure restricts you from making a larger quantity than the quantity that is shown in the **Able to Make Top Item** field. For example, the bottleneck item can be a purchased component with an expected receipt date that is too late to make additional units of the top item by the date in the **Needed by Date** field.

### To view the availability of an item by its units of measure
The **Item Availability by Unit of Measure** page shows an items availability broken down in the different units of measure that it is stored in.

## Assembly Availability Page
The **Assembly Availability** page shows detailed availability information for the assembly item. It opens:

- Automatically from a sales order line in assemble-to-order scenarios when you enter a quantity that causes a component availability issue.
- Automatically from an assembly order header when you enter a value in the Quantity field that causes a component availability issue.
- Manually when you open it from an assembly order. On the Actions tab, in the Functions group, click Show Availability.

The **Details** FastTab shows detailed availability information for the assembly item, including how many of the assembly order quantity can be assembled by the due date based on availability of the required components. This is shown in the Able to Assemble field on the Details FastTab.

The value in the **Able to Assemble** field is shown in red font if the quantity is lower than the quantity in the **Remaining Quantity** field, indicating that there are not enough components available to assemble the full quantity.

The **Lines** FastTab shows detailed availability information for the assembly components.

If one or more assembly components are not available, then this is reflected in the **Able to Assemble** field on the line in question as a quantity less than the quantity in the **Remaining Quantity** field on the **Details** FastTab.

## See Also
[Manage Inventory](inventory-manage-inventory.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with Bills of Materials](inventory-how-work-BOMs.md)    
[Set Up Locations](inventory-how-setup-locations.md)  
[Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md)  
[Sell Products](sales-how-sell-products.md)      
[Working with Business Central](ui-work-product.md)  
[General Business Functionality](ui-across-business-areas.md)
