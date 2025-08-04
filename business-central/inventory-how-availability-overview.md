---
title: Get an availability overview
description: You can get information about the availability of items or stock across locations, per sales or purchase events, by time period, and more.
documentationcenter: ''
author: brentholtorf
ms.topic: overview
ms.devlang: al
ms.search.keywords: stock
ms.search.form: 908, 909, 925, 926, 504, 501, 500, 499, 99000896, 342, 515, 5417, 5415, 5871, 5530, 492, 157, 5540, 5416, 5414, 1872, 1873, 99000902, 353, 491, 9231, 5390
ms.date: 04/08/2024
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# View the availability of items

From the context of a business task, you can get advanced information about when and where an item is available, such as when talking to a customer about a delivery date.

You can view the availability of all items per location, and you can view the availability of each item by event or by period as well. An event is any scheduled item transaction, such as a sales shipment or an inbound transfer receipt.

> [!NOTE]  
>   Availability views by location require that you maintain inventory at more than one location. For more information, see [Set Up Locations](inventory-how-setup-locations.md).

If you use warehousing functionality, availability varies depending on allocations at the bin level when warehouse activities such as picks and movements occur and when the inventory reservation system imposes restrictions to comply with. A rather complex algorithm verifies that all conditions are met before allocating quantities to picks for outbound flows. For more information, see [Design Details: Availability in the Warehouse](design-details-availability-in-the-warehouse.md).

In [!INCLUDE[prod_short](includes/prod_short.md)], availability figures are typically shown in two different fields, each with a different definition:

* The **Quantity on Hand** field, in some places named **Inventory**, shows the actual quantity today according to posted item ledger entries.
* The **Projected Available Balance** field is calculated and shows the quantity on hand plus scheduled receipts minus gross requirements. (In [!INCLUDE[prod_short](includes/prod_short.md)], scheduled receipts include quantities on purchase orders and inbound transfer orders. Gross requirements include quantities on sales orders and outbound transfer orders.)

> [!TIP]  
>   The projected available balance is especially relevant to view in the **Item Availability by Periods** and **Item Availability by Event** pages because they contain the date dimension.  

> [!NOTE]  
>   The following procedures describe how to view advanced availability information from the items list and item card. You can also access the information from sales document lines for the item on the line. For more information, see [Sell Products](sales-how-sell-products.md).

## To view the availability of an item according to when it will be received or shipped

You view the availability of an item according to scheduled item transactions on the **Availability by Event** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card of an item that you want to view availability for.
3. Choose the **Item Availability by** action, and then choose the **Event** action.

    The **Item Availability by Event** page shows how the inventory quantity of the item will develop over time according to scheduled shipment and receipt events. The page gives a condensed view that shows one line of accumulated information per time interval in which inventory quantities change. Time intervals where no events occurred aren't shown. You can expand each line to show details about the event or events that caused the accumulated quantity on the line.
4. Choose the value in the **Projected Available Balance** field to view the item ledger entries or open documents that make up the value.

## To view the availability of an item in different periods

You view the availability of an item over time for specified time periods on the **Item Availability by Periods** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card of an item that you want to view availability for.
3. Choose the **Item Availability by** action, and then choose the **Period** action.

    The **Item Availability by Periods** page shows how the inventory quantity of the item will develop over time, shown for a period that you select, such as Day, Week, or Quarter.
4. Choose the value in the **Projected Available Balance** field to view the item ledger entries or open documents that make up the value.

## To view the availability of an item at the locations where it's stored

You view the availability of an item at the different places where it's stored on the **Item Availability by Location** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card of an item that you want to view availability for.
3. Choose the **Item Availability by** action, and then choose the **Location** action.

    The **Item Availability by Location** page shows how the inventory quantity of the item will develop in the future, shown for each location where it's stored.
4. Choose the value in the **Qty. on Hand** field to view the item ledger entries that make up the value.
5. Choose the value in the **Projected Available Balance** field to view the item ledger entries or open documents that make up the value.

## To view the availability of all items by the location where they're stored

You view the availability of all your items across all your locations on the **Items by Location** page.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Choose the **Items by Location** action.

    The **Items by Location** page shows for all your items how many are available at each location.
3. Choose the value in the **Qty. on Hand** field to view the item ledger entries that make up the value.

## To view the availability of an item by its use in assembly or production BOMs

If an item is part of assembly or production BOMs as either a parent item or a component, you can view how many units of it are required on the **Item Availability by BOM Level** page. The page shows how many units of a parent item you can make based on the availability of child items on underlying lines. Any item that has an assembly or production BOM is shown on the page as a collapsible line. You can expand this line to see the underlying components and lower-level subassemblies with their own BOMs.

For example, you can use the page to determine whether you can fulfill a sales order for an item on a specified date by looking at its current availability and the quantities that can be supplied by its components. You can also use the page to identify bottlenecks in related BOMs.

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

## To view the availability of an item by its units of measure

The **Item Availability by Unit of Measure** page shows the availability of an item in the units of measure that it's stored in.

> [!NOTE]  
> To keep this information accurate, you must convert item units of measure. For example, if you purchase an item in one unit of measure, such as boxes, and you sell items in another unit of measure, such as pieces, you must use an item journal to convert the units of measure, or "unbox" items. You can use a negative adjustment item journal line to reduce inventory in the purchase unit of measure, for example boxes, and a positive adjustment to increase inventory in the sales unit of measure, for example pieces. 

## To view the availability of an item by its variants

The **Item Availability by Variant** page shows the actual and projected availability of an item grouped according to variant code.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card of an item that you want to view availability for.
3. Choose the **Item Availability by** action, and then choose the **Variant** action.

    The **Item Availability by Variant** page shows availability for every variant that exists for the item. The page is empty if no variants exist for the item.

4. In the **View by** field, select the length of the time period that you want to view.
5. View the availability figures in the different quantity fields for each line.

[!INCLUDE [inventory_variant-availability](includes/inventory_variant-availability.md)]

## Assembly availability page

The **Assembly Availability** page shows detailed availability information for the assembly item. It opens:

- Automatically from a sales order line in assemble-to-order scenarios when you enter a quantity that causes a component availability issue.
- Automatically from an assembly order header when you enter a value in the Quantity field that causes a component availability issue.
- Manually when you open it from an assembly order. On the Actions tab, in the Functions group, select Show Availability.

The **Details** FastTab shows detailed availability information for the assembly item, including how many of the assembly order quantity can be assembled by the due date based on availability of the required components. This is shown in the Able to Assemble field on the Details FastTab.

The value in the **Able to Assemble** field is shown in red font if the quantity is lower than the quantity in the **Remaining Quantity** field, indicating that there aren't enough components available to assemble the full quantity.

The **Lines** FastTab shows detailed availability information for the assembly components.

If one or more assembly components aren't available, then this is reflected in the **Able to Assemble** field on the line in question as a quantity less than the quantity in the **Remaining Quantity** field on the **Details** FastTab.

## Related information

[Manage Inventory](inventory-manage-inventory.md)  
[Assembly Management](assembly-assemble-items.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Create Production BOMs](production-how-to-create-production-boms.md)  
[Set Up Locations](inventory-how-setup-locations.md)  
[Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md)  
[Sell Products](sales-how-sell-products.md)  
[General Business Functionality](ui-across-business-areas.md)  
[Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
