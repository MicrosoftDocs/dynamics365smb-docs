---
title: Sell Items Assembled to Order
description: Learn how to sell an item that is assembled to order.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 11/23/2022
ms.search.keywords: kit, kitting, substitute items
ms.search.form: 900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905
ms.custom: bap-template
---
# Sell Items Assembled to Order

Items that are set up for assemble-to-order aren't expected to be in inventory and will be assembled when it's included on a sales order. An item is set up for assemble-to-order when the **Assembly Policy** field on the item card contains **Assemble-to-Order**. When you enter the item on a sales order line, an assembly order is automatically created and linked to the sales order.  

> [!NOTE]  
> If assemble-to-order items are already in inventory, you can deduct that quantity from the assembly order and reserve it from inventory. Learn more at [Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  

In this procedure, you process the sale of an item that will be assembled according to specifications that are requested by the customer. The steps include: 

* Creating a sales order line.
* Customizing the assembly item by editing its components and resources.
* Checking availability to establish a delivery date.
* Releasing the sales order to be assembled and immediately shipped.  

> [!NOTE]  
> The following procedure does not include the steps for creating a standard sales order that happen before the step where you enter the assemble-to-order item on a sales order line. Learn more about creating sales orders at [Sell Products with a Customer Sales Order](sales-how-sell-products.md).  

## To sell an item that is assembled to order

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2. Create a sales order. 
3. In the **No.** field, enter an item that is set up to be assembled to order.  
4. In the **Location Code** field, define which location the item will be sold from. The assembly process will occur at that location.  
5. In the **Quantity** field, enter how many units to sell.  

    > [!NOTE]  
    >  If one or more components of the requested assembly item quantity aren't available, an availability warning page opens. <!-- Check whether the field help would be useful. For more information, see Assembly Availability.  -->

    An assembly order is created and linked to the sales order line. The due date of the assembly order is the shipment date of the sales order line.  

    The quantity to sell is copied to the **Qty. to Assemble to Order** field, which indicates that the item setup expects you'll assemble the full quantity on the sales line. You can decrease the quantity to assemble, for example, if you know that some items are already available. Learn more at [Sell Inventory Items in Assemble-to-Order Flows](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  

6. If the customer wants an additional item in a kit, on the **Lines** FastTab, choose the **Line** action, choose the **Assemble to Order** action, and then choose the **Assemble-to-Order Lines** action to view and change the standard assembly components. Alternatively, choose the **Qty. to Assemble to Order** field.  
7. On the **Assemble-to-Order Lines** page, create a new line of type **Item** for the additional assembly component.  

    You can also customize the order by increasing the quantity of one standard item in the kit. You can do this by increasing the value in the **Quantity Per** field on the specific assembly order line.  

    > [!NOTE]  
    >  The **Assemble-to-Order Lines** page only contains the basic fields for customizing the component list, adding item tracking numbers, or solving component availability issues. To add more assembly order information, such as the assembly order starting date, choose the **Show Documents** action. This opens a full view of the assembly order that is linked to the sales order line. You can't change the contents of most fields on the assembly order header, and you can't post assembly output from it. You must post the shipment of the sales order line.  
    >
    >  On the linked assembly orders, only the **Starting Date** field can be changed. Changing the starting date lets assembly workers specify that they're starting assembly earlier than the due date. All fields on the lines of the linked assembly order can be changed so that warehouse workers can enter consumption figures during the process.  

8. Review or react to component availability issues. For example, select a substitute item.  
9. Close the **Assemble-to-Order Lines** page. The linked assembly order is ready, and workers can start to assemble the customized items.  
10. On the sales order, choose the **Release** action to notify the assembly department that the assembly process can start. Learn more at [Assemble Items](assembly-how-to-assemble-items.md).  

> [!NOTE]  
> Item substitutions don't automatically replace an item with another item, for example, when creating a sales order or in a BOM. Instead, you'll be alerted to the fact that a substitution is available.

## Related information

[Assembly Management](assembly-assemble-items.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Register New Items](inventory-how-register-new-items.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]