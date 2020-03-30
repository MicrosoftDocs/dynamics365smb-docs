---
    title: How to Sell Items Assembled to Order | Microsoft Docs
    description: If the item is set up for assemble-to-order, then the item is not expected to be in inventory, and it must be assembled specifically to a sales order. When you enter the item on a sales order line, then an assembly order is automatically created and linked to the sales order.
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
# Sell Items Assembled to Order
If the **Assembly Policy** field on the item card of an assembly item is **Assemble-to-Order**, then the item is not expected to be in inventory, and it must be assembled specifically to a sales order. When you enter the item on a sales order line, then an assembly order is automatically created and linked to the sales order.  

> [!NOTE]  
>  If some assemble-to-order items are already in inventory, then you can deduct that quantity from the assembly order and reserve it from inventory. For more information, see [Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  

In this procedure, you process the sale of an item that will be assembled according to specifications that are requested by the customer. The steps include initiating the sales order line, customizing the assembly item by editing its components and resources, checking availability to establish a delivery date, and releasing the sales order to be assembled and immediately shipped.  

> [!NOTE]  
>  The following procedure does not include the standard sales order steps before the step where you enter the assemble-to-order item on a sales order line.  

## To sell an item that is assembled to order  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2.  Create a sales order. For more information, see [Sell Products](sales-how-sell-products.md).  
3.  In the **No.** field, enter an item that is set up to be assembled to order.  
4.  In the **Location Code** field, define which location the item will be sold from. The assembly process will occur at that location.  
5.  In the **Quantity** field, enter how many units to sell.  

    > [!NOTE]  
    >  If one or more components of the requested assembly item quantity are not available, then a detailed availability warning page opens. For more information, see Assembly Availability.  

    An assembly order is now automatically created and linked to the sales order line. The due date of this assembly order is synchronized with the shipment date of the sales order line.  

    The quantity to sell is copied to the **Qty. to Assemble to Order** field, which indicates that the item setup expects the full quantity on the sales line to be assembled to the order. You can decrease the quantity to assemble to order, such as if you know that some items are already available. For more information, see [Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  

6.  To reflect that the customer wants an additional item in a kit, on the **Lines** FastTab, choose the **Line** action, choose the **Assemble to Order** action, and then choose the **Assemble-to-Order Lines** action to view and change the standard assembly components. Alternatively, choose the **Qty. to Assemble to Order** field.  
7.  On the **Assemble-to-Order Lines** page, create a new line of type **Item** for the requested additional kit content. The line represents an additional assembly component.  

    You could also customize the order by increasing the quantity of one standard item in the kit. You can do this by increasing the value in the **Quantity Per** field on the specific assembly order line.  

    > [!NOTE]  
    >  The **Assemble-to-Order Lines** page only contains the basic fields that a salesperson is expected to use to customize the component list, add item tracking numbers, or to solve component availability issues. To see more assembly order information, such as the assembly order starting date, choose the **Show Documents** action. This opens a full view of the assembly order that is linked to the sales order line. You cannot change the contents of most fields on the assembly order header, and you cannot post assembly output from it because you must use shipment posting of the sales order line.  
    >   
    >  On the header of linked assembly orders, only the **Starting Date** field can be changed to enable assembly workers to specify a date that is earlier than the due date when they will start the process. All fields on the lines of the linked assembly order can be changed so that warehouse workers can enter consumption figures during the process.  

8.  Review or react to component availability issues. For example, select an available substitute item or establish a later due date.  
9. Close the **Assemble-to-Order Lines** page. The linked assembly order is now ready to start to assemble the customized items by the due date.  
10. On the sales order, choose the **Release** action to notify the assembly department that the assembly process can start.  
11. In the assembly department, perform the steps of assembling the items that are sold in this procedure. For more information, see [Assemble Items](assembly-how-to-assemble-items.md).  

## See Also  
[Assembly Management](assembly-assemble-items.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Inventory](inventory-manage-inventory.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
