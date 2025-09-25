---
title: Pick items for warehouse shipment
description: Learn about using warehouse pick documents to create and process pick information prior to posting a warehouse shipment.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 04/23/2024
ms.custom: bap-template
ms.search.forms: 7335, 7339, 7345, 

---
# Pick items for warehouse shipment

In [!INCLUDE[prod_short](includes/prod_short.md)], you pick and ship items using one of four methods, as described in the following table.

|Method|Outbound Process|Require Pick|Require Shipment|Complexity Level (Learn more at [Warehouse Management Overview](design-details-warehouse-management.md))|  
|------|----------------|-----|---------|-------------------------------------------------------------------------------------|  
|A|Post the pick and shipment from the order line|||No dedicated warehouse activity.|  
|B|Post the pick and shipment from an inventory pick document|Turned on||Basic: Order-by-order.|  
|C|Post the pick and shipment from a warehouse shipment document||Turned on|Basic: Consolidated receive/ship posting for multiple orders.|  
|D|Post the pick from a warehouse pick document, and post the shipment from a warehouse shipment document|Turned on|Turned on|Advanced|  

Learn more at [Outbound Warehouse Flow](design-details-outbound-warehouse-flow.md).

This article refers to method D in the table. To learn more about shipping items, go to [Shipping Items](warehouse-how-ship-items.md).

When a location is set up to require warehouse pick processing and warehouse shipment processing, use warehouse pick documents to create and process pick information before you post the warehouse shipment.  

You can't create a warehouse pick document from scratch. Picks are part of a workflow where the person processing an order creates them in a push fashion, or the warehouse employee creates them in a pull fashion:

- In a push fashion, where you use the **Create Pick** action in the **Warehouse Shipment** page. Select the lines to be picked and prepare the picks by specifying, for example, which bins to take from and place in, and how many units to handle. Bins can be predefined for the warehouse location or resource.
- In a pull fashion, where you use the **Release** action in the **Warehouse Shipment** page to make the items available for picking. Then, on the **Pick Worksheet** page, warehouse employees can use the **Get Warehouse Documents** action to pull their assigned picks.

> [!NOTE]  
> Picking for a warehouse shipment of items that are assembled for a sales order follows the same steps as for regular warehouse picks for shipments, as described in this article. However, the number of pick lines for the quantity to ship may be many to one because you pick the components, not the assembled item.  
>
> Warehouse pick lines are created for the value in the **Remaining Quantity** field on the lines of the assembly order that's linked to the sales order line being shipped. All components are picked in one action. Learn more at [Handling Assemble-to-Order Items in Warehouse Shipments](warehouse-how-ship-items.md#handling-assemble-to-order-items-in-warehouse-shipments).  
>  
> To learn more about picking components for assembly orders, including situations where assembly items aren't related to a sales shipment, go to [Pick for Production, Assembly, or Jobs in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).  

## Check whether items are available for picking

[!INCLUDE [inventory-availability-overview](includes/inventory-availability-overview.md)]

## To create pick documents in bulk with the pick worksheet

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Pick Worksheet**, and then choose the related link.  

2. Choose the **Get Warehouse Documents** action.  

    The list will include all shipments that have been released for picking, including those for which pick instructions have already been created. Documents with pick lines that have been completely picked and registered are not shown in this list.  
3. Select the shipments for which you want to prepare a pick.

    > [!NOTE]  
    >  If you try to select a shipment or internal pick document for which you've already created instructions for all of its lines you'll get a message that says something like, "there is nothing to handle." To combine warehouse pick instructions that you've already created into one pick instruction, you must delete the individual warehouse picks first.

4. Fill in the **Sorting Method** field to sort the lines.  

    > [!NOTE]  
    >  The way the lines are sorted in the worksheet doesn't automatically carry through to the pick instruction. However, the same sorting and bin ranking opportunities exist. You can easily recreate the line order you plan in the worksheet when you create the pick instructions or sort in the pick instructions.

5. Fill in the **Qty. to Handle** field either manually, or by using the **Autofill Qty.to Handle** action.  

    The page shows the quantities available in cross-docking bins. This information is useful for planning work assignments in cross-docking situations. [!INCLUDE[prod_short](includes/prod_short.md)] will always propose a pick from a cross-dock bin first.
6. If needed, edit the lines. You can also delete lines to make the pick more efficient. For example, if there are multiple lines with items that are in cross-dock bins, you might create a pick for all of the lines. The cross-docked items will be shipped with the other items on the shipment, and the cross-dock bins will have space for more incoming items.  

    > [!NOTE]  
    >  If you delete lines, they're only deleted from the worksheet. They aren't deleted from the pick selection list.  

7. Choose the **Create Pick** action. The **Create Pick** page opens, where you can add more information to the pick you are creating. Specify how to combine pick lines in the pick documents by selecting one of the following options.  

    |Option|Description|
    |-|-|
    |Per Whse. Document|Creates separate pick documents for worksheet lines with the same warehouse source document.|
    |Per Cust./Vend./Loc.|Create separate pick documents for each customer (sale orders), vendor (purchase return orders), and location (transfer orders).|
    |Per Item|Create separate pick documents for each item on the pick worksheet.|
    |Per From Zone|Create separate pick documents for each zone that you'll take items from.|
    |Per Bin|Create separate pick documents for each bin that you'll take items from.|
    |Per Due Date|Create separate pick documents for source documents that have the same due date.|

    Specify how the pick documents are created by selecting from the following options.

    |Option|Description|
    |-|-|
    |Max. No. of Pick Lines|Creates pick documents that have no more than the specified number of lines in each document.|
    |Max. No. of Pick Source Docs.|Creates pick documents that each cover no more than the specified number of source documents.|
    |Assigned User ID|Creates pick documents only for worksheet lines that are assigned to the selected warehouse employee.|
    |Sorting Method for Pick Lines|Select from the available options to sort lines in the created pick document.|
    |Set Breakbulk Filter|Hides intermediate breakbulk pick lines when a larger unit of measure is converted to a smaller unit of measure and completely picked.|
    |Do Not Fill Qty. to Handle|Leaves the Qty. to Handle field in the created pick lines empty.|
    |Print Pick|Prints the pick documents when they are created. You can also print from the created pick documents.|

8. Choose **OK**. [!INCLUDE [prod_short](includes/prod_short.md)] will create the pick according to your selections.  

## To pick items for a warehouse shipment

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Warehouse Picks**, and then choose the related link.  

    If you need to work on a particular pick, select the pick from the list or filter the list to find the picks that have been assigned to you specifically. Open the pick card.  
2. If the **Assigned User ID** field is empty, enter your ID to identify yourself if needed.  
3. Pick the items.  

    If the warehouse is set up to use bins, the items’ default bins are used to suggest where to take the items from. The instructions contain at least two separate lines for Take and Place actions.  

    If the warehouse is set up to use directed put-away and pick, bin ranking is used to calculate the best bins to pick from. Those bins are suggested on the pick lines. The instructions contain at least two separate lines for Take and Place actions.  

    * The first line, with **Take** in the **Action Type** field, indicates where the items are located in the picking area. If you're shipping a large number of items on one shipment line, you might have to pick the items in several bins, so there's a Take line for each bin.
    * The next line, with **Place** in the **Action Type** field, shows where you must place the items in the warehouse. You can't change the zone and bin on this line.

    > [!NOTE]
    > If you must pick or place the items for one line in more than one bin, for example because the designated bin is full, use the **Split Line** action on the **Lines** FastTab. The action creates a line for the remaining quantity to handle.
        
    You can sort the pick lines by various criteria, for example, by item, shelf number, or due date. Sorting can help optimize the put-away process, for example:

    * If the Take and Place lines for each shipment line don't immediately follow one another, and you want them to, sort the lines by selecting **Item** in the **Sorting Method** field.  
    * If bin rankings reflect the physical layout of the warehouse, use the **Bin Ranking** sorting method to organize the work by bin locations.

  > [!NOTE]  
  > Lines are sorted in ascending order by the selected criteria. If you sort by document, sorting is done first by document type based on the **Warehouse Activity Source Document** field. If you sort by ship-to, sorting is done first by destination type based on the **Warehouse Destination Type** field.

4. After you pick and place the items in the shipping area or shipping bin, choose the **Register Pick** action.  

You can now bring the items to the shipment dock and post the shipment, including the related source document, on the **Warehouse Shipment** page. Learn more at [Ship Items](warehouse-how-ship-items.md).

## Related information

- [Warehouse Management Overview](design-details-warehouse-management.md)
- [Manage Inventory](inventory-manage-inventory.md)  
- [Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
- [Assembly Management](assembly-assemble-items.md)    
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
