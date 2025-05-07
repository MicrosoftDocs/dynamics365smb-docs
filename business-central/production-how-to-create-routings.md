---
title: Create routings
description: This article gives an overview of the different ways to create routings including prerequisites required and how to create routing links.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 99000764, 99000765, 99000766, 99000767, 99000794, 99000796, 99000798, 99000806, 99000808, 99000810, 99000817, 99000834, 99000835, 99000836, 99000837, 99000840, 99000841, 99000844, 99000845
ms.date: 06/06/2024
ms.service: dynamics-365-business-central

---
# Create routings

Manufacturing companies use routings to visualize and direct the manufacturing process.

The routing is the basis of process scheduling, capacity scheduling, scheduled assignment of material needs, and manufacturing documents.  

As for production bills of material (BOMs), the routings are assigned to the manufacturing end item. A routing holds master data that captures the process requirements of a given produced item. After a production order is created for an item, its routing governs the scheduling of operations as represented on the **Prod. Order Routing** page under the production order.  

Before you can set up a routing, the following setups must be in place:  

- Item cards are created for parent items that take part in manufacturing. To learn more, go to [Register New Items](inventory-how-register-new-items.md).
- Production resources are set up. To learn more, go to [Set Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md).

## To create a routing

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
2. Choose the **New** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. In the **Type** field, select one of the following options:
   - **Serial** to calculate the production routing according to the value in the **Operation No.** field.  
   - Select **Parallel** to calculate the operations according to the value in the **Next Operation No.** field.  
5. To edit the routing, set the **Status** field to **New** or **Under Development**.  

    Proceed to fill in the routing lines.
6. In the **Operation No.** field, enter the number of the first operation, for example,  **10**.  
7. In the **Type** field, specify which kind of resource is used, for example, **Work Center**.  
8. In the **No.** field, select the resource to be used, or type it in the field.  
9. In the **Routing Link Code** field, enter a code to connect the component to a specific operation. For more information, see [To create routing links](production-how-to-create-routings.md#to-create-routing-links).
10. In the **Run Time** and **Setup Time** fields, enter the process times needed to perform the operation.

     > [!NOTE]
     > Setup time is calculated per production order, whereas run time is calculated per produced item.  

11. In the **Concurrent Capacities** field, specify how many units of the selected resource are used to perform the operation. For example, allocating two people to one packing operation halves the run time.  
12. Continue to fill in lines for all operations involved in producing the item in question.  
13. To copy lines from an existing routing, choose the **Copy Routing** action to select existing lines.  
14. To activate the routing, in the **Status** field, choose **Certified**.  
15. You can now attach the new routing to the card of the production item in question, by filling in the **Routing No.** field. To learn more, go to [Register New Items](inventory-how-register-new-items.md).  

> [!NOTE]  
> Remember to recalculate the item's standard cost from the **Item** card. Choose the **Production** action, the **Calc. Production Std. Cost** action, and then choose the **All Levels** action.  You can also calculate and update the standard cost for one or many items on the **Standard Cost Worksheet** page. Learn more at [Update Standard Costs](finance-about-calculating-standard-cost.md#updating-standard-costs-with-standard-cost-worksheet).  


## To create routing links

You can create routing links to connect components to specific operations to retain their relationship even though the production BOM or routing is modified. Routing links also facilitate just-in-time flushing of components, namely when the specific linked operation starts, not when the complete production order is released. To learn more, go to [Flush Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).  

Another important benefit is that linked components and operations display in a logical process structure when you use the **Production Journal** page to post output and consumption.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
2. Open the routing that contains the operations that you want to link.  

    Make sure the routing status is **Under Development**.  

3. On the relevant routing line, in the **Routing Link Code** field, select a code.  
4. Add different routing link codes to other operations in the routing, if relevant.  

    > [!NOTE]  
    > You shouldn't use the same routing link code in different operations on a routing because you might incorrectly link a component to two different operations, so that it is consumed two times.  
    >
    > It's a good idea to name the routing link code after the operation to ensure operation-specific routing links.

5. Set the routing status to **Certified**.  

    Routing link codes are now assigned to operations. Next, you must create the actual link by assigning the same codes to specific components in the relevant production BOM.  

6. Open the **Production BOM** that contains the components that you want to link to the above operations. To learn more, go to [Create Production BOMs](production-how-to-create-production-boms.md).
7. Make sure the BOM status is **Under Development**.  
8. On the relevant production BOM line, in the **Routing Link Code** field, select the code that you assigned to the operation.  
9. Proceed to add routing link codes to other components according to the unique operations where they're used.  
10. Set the production BOM status to **Certified**.  

    > [!NOTE]  
    > To enable the routing links on an existing production order, you must refresh the production order. To learn more, go to [Create Production Orders](production-how-to-create-production-orders.md).  

The selected components are now linked to the selected operations when you create or refresh a production order using the production BOM and routing. This link is visible on the **Prod. Order Components** page under the production order. You can remove and add the routing link codes at any time.

## To assign personnel, tools, and quality measures to routing operations

If you require personnel with qualifications, special knowledge, or special authorization for an operation, you can assign these personnel to the operation. In addition, you can assign tools and quality requirements to the operation. This procedure describes how to assign personnel. The steps are similar for other types of operation information.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
2. Open the relevant routing.  
3. On the **Lines** FastTab, select the line that you want to process, choose the **Operations** action, and then choose the **Personnel** action.  
4. Fill in the fields on the **Routing Personnel** page.  
5. Choose the **OK** button to exit the page. The entered values are copied and assigned to the operation.  

## To create a new version of a routing

The version principle enables you to manage several versions of a routing. The structure of the routing version corresponds to the structure of the routing consisting of the routing version header and the routing version lines. The starting date defines the basic difference.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
2. Select the routing to copy, and then choose the **Versions** action.  
3. On the **Routing Versions** page, choose the **New** action.
4. In the **Version Code** field, enter the unique identification of the version. You can use any combination of numbers and letters.  

    The newly created version is automatically assigned the status **New**.  
5. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](../archive/SetupAndAdministration/includes/tooltip-inline-tip_md.md)]
6. To create operation lines, select the first blank line, and then fill in the **Operation No.** field according to the sequence of operations.

    The operation lines are in ascending order by operation numbers. To be able to make changes later, we recommend that you select adequate step widths. The **Next Operation No.** field refers to the next operation in the routing.

7. When you're done setting up the routing version, in the **Status** field, choose **Certified**.

## Related information

[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
