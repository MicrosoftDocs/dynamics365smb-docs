---
    title: How to Assemble Items | Microsoft Docs
    description: If the **Replenishment System** field on the item card contains **Assembly**, then the default method of supplying the item is to assemble it from defined components and potentially by a defined resource.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: kit, kitting
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Assemble Items
If the **Replenishment System** field on the item card contains **Assembly**, then the default method of supplying the item is to assemble it from defined components and potentially by a defined resource.  

The components and resources that go into this kind of an assembly item must be defined in an assembly BOM. For more information, see [Work with Bills of Material](inventory-how-work-BOMs.md).  

Assembly items can be set up for two different assembly processes:  

-   Assemble to stock.  
-   Assemble to order.  

You typically use **Assemble to Stock** for items that you want to assemble ahead of sales, such as to prepare for a kit campaign, and keep in stock until they are ordered. These items are usually standard items such as packaged kits that you do not offer to customize to customer requests.  

You typically use **Assemble to Order** for items that you do not want to stock because you expect to customize them to customer requests or because you want to minimize the inventory carrying cost by supplying them just in time. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  

For more information about how to set up an assembly item, see [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).  

These setup options are default settings that manage how sales and assembly order lines are initially processed. You can depart from these defaults and supply the assembly item in the most optimal way when processing a sale. For more information, see [Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md) and [Sell Assemble-to-Order Items and Inventory Items Together](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).

> [!NOTE]  
> Assembly components are handled in a special way in basic warehouse configurations. For more information, see the “Handling Assemble-to-Order Items in Inventory Picks” section in [Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md).   

In this procedure, you create and process an assembly order for items that are assembled to stock, which means without a linked sales order. The steps include initiating the assembly order, handling potential component availability issues, and partially posting assembly item output.

## To assemble an item  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Assembly Orders**, and then choose the related link.  
2.  Choose the **New** action. The **New Assembly Order** page opens.  
3.  Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4.  In the **Item No.** field, select the assembly item that you want to process. The field is filtered to show only items that are set up for assembly, which means that they have assembly BOMs assigned.  
5.  In the **Quantity** field, enter how many units of the item that you want assembled.  

    > [!NOTE]  
    >  If one or more components are not available to fulfill the entered assembly item quantity on the defined due date, then the **Assembly Availability** page automatically opens to provide detailed information about how many assembly items can be assembled based on component availability. For more information, see [View the Availability of Items](inventory-how-availability-overview.md). When you close the page, the assembly order is created with availability alerts on the affected component lines.  

    The assembly order lines are automatically filled with the contents of the assembly BOM and with line quantities according to the assembly order header.  

    > [!NOTE]  
    >  If the **Assembly Availability** page opened when you filled in the assembly order header, then each affected assembly order line contains a **Yes** in the **Avail. Warning** field with a link to detailed availability information. For more information, see Check Availability. You can resolve a component availability issue by postponing the starting date, replacing the component with another item, or selecting an available substitution if one is defined.  

6.  In the **Quantity to Assemble** field, enter how many units of the assembly item that you want to post as output the next time that you post the assembly order. This quantity can be lower than the value in the **Quantity** field to reflect a partial output posting.  

    > [!NOTE]  
    >  To make sure that component consumption posting matches the assembly item output posting, the quantity fields in the assembly order lines automatically adjust to the value that you enter in the **Quantity to Assemble** field.  
7.  On assembly order lines of type **Item** or **Resource**, in the **Quantity to Consume** field, specify how many units you want to post as consumed the next time that you post the assembly order.
8.  When you are ready to partially or fully post, choose the **Post** action.  

    > [!NOTE]  
    >  If warnings are still present in any of the assembly order lines, then the posting is blocked. A message about which component or components are not in inventory is displayed.  

After posting succeeds, the assembly item is posted as output to the location code and potential bin code that are defined on the assembly order. For manually created assembly orders, the location may be copied from the **Default Location for Orders** setup field. For assemble-to-order flows, the location code may be copied from the sales order line.  

## See Also
[Assembly Management](assembly-assemble-items.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Inventory](inventory-manage-inventory.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
