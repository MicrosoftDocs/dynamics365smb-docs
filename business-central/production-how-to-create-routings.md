---
    title: How to Create Routings | Microsoft Docs
    description: A routing holds master data that captures the process requirements of a given produced item. Once a production order is created for that item, its routing will govern the scheduling of operations as represented on the **Prod. Order Routing** page under the production order.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Create Routings
Manufacturing companies use routings to visualize and direct the manufacturing process.

The routing is the basis of process scheduling, capacity scheduling, scheduled assignment of material needs, and manufacturing documents.  

As for production BOMs, the routings are assigned to the manufacturing end item. A routing holds master data that captures the process requirements of a given produced item. Once a production order is created for that item, its routing will govern the scheduling of operations as represented on the **Prod. Order Routing** page under the production order.  

Before you can set up a routing, the following must be in place:  

- Item cards are created for parent items that take part in manufacturing. For more information, see [Register New Items](inventory-how-register-new-items.md).
- Production resources are set up. For more information, see [Set Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md).

## To create a routing  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
2.  Choose the **New** action.  
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4.  In the **Type** field, select **Serial** to calculate the production routing according to the value in the **Operation No.** field.   
    Select **Parallel** to calculate the operations according to the value in the **Next Operation No.** field.  
5.  To edit the routing, set the **Status** field to **New** or **Under Development**. To activate it, set the **Status** field to **Certified**.  

    Proceed to fill in the routing lines.
6.  In the **Operation No.** field, enter the number of the first operation, for example,  **10**.  
7.  In the **Type** field, specify which kind of resource is used, for example, **Work Center**.  
8.  In the **No.** field, select the resource to be used, or type it in the field.  
9.  In the **Routing Link Code** field, enter a code to connect the component to a specific operation. For more information, see [To create routing links](production-how-to-create-routings.md#to-create-routing-links).
10.  In the **Run Time** and **Setup Time** fields, enter the process times needed to perform the operation.

     > [!NOTE]
     > Setup time is calculated per production order, whereas run time is calculated per produced item.  

11.  In the **Concurrent Capacities** field, specify how many units of the selected resource are used to perform the operation. For example, two people allocated to one packing operation will halve the run time.  
12.  Continue to fill in lines for all operations involved in producing the item in question.  
13.  To copy lines from an existing routing, choose the **Copy Routing** action to select existing lines.  
14. Certify the routing.  
15. You can now attach the new routing to the card of the production item in question, by filling in the **Routing No.** field. For more information, see [Register New Items](inventory-how-register-new-items.md).  

> [!NOTE]  
>  Remember also to recalculate the item’s standard cost from the **Item** card: Choose the **Manufacturing** action, select the **Calc. Standard Cost** action, and then select the **All Levels** action.  

## To create routing links
You can create routing links to connect components to specific operations in order to retain their relationship even though the production BOM or routing is modified. It also facilitates just-in-time flushing of components, namely when the specific linked operation starts, not when the complete production order is released. For more information see [Flush Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).  

Another important benefit is that linked components and operations are displayed in a logical process structure when you use the **Production Journal** page for output and consumption posting.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
2.  Open the routing that contains the operations that you want to link.  

    Make sure the routing status is **Under Development**.  

3.  On the relevant routing line, in the **Routing Link Code** field, select a code.  
4.  Proceed to add different routing link codes to other operations in the routing, if relevant.  

    > [!NOTE]  
    >  You should not use the same routing link code in different operations on a routing because you may incorrectly link a component to two different operations, so that it is consumed two times.  
    >   
    >  It is a good idea to name the routing link code after the operation in order to ensure operation-specific routing links.

5.  Set the routing status to **Certified**.  

    Routing link codes are now assigned to operations. Next, you must create the actual link by assigning the same codes to specific components in the relevant production BOM.  

6.  Open the **Production BOM** that contains the components that you want to link to the above operations. For more information, see [Create Production BOMs](production-how-to-create-production-boms.md).
7.  Make sure the BOM status is **Under Development**.  
8.  On the relevant production BOM line, in the **Routing Link Code** field, select the code that you have just assigned to the relevant operation.  
9. Proceed to add routing link codes to other components according to the unique operations where they are used.  
10. Set the production BOM status to **Certified**.  

    > [!NOTE]  
    >  To enable the routing links on an existing production order, you must refresh the productio1n order. For more information, see [Create Production Orders](production-how-to-create-production-orders.md).  

The selected components will now be linked to the selected operations when you create or refresh a production order using the production BOM and routing in question. This is visible on the **Prod. Order Components** page under the production order, and here you can also remove and add the defined routing link codes at any time.

## To assign personnel, tools, and quality measures to routing operations.
If you require personnel with qualifications, special knowledge, or special authorization for an operation, you can assign these personnel to the operation. In addition, you can assign tools and quality requirements to the operation. This procedure describes how to assign personnel. The steps are similar for other types of operation information.

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
2.  Open the relevant routing.  
3.  On the **Lines** FastTab, select the line that you want to process, and then choose the **Personnel** action.  
4.  Fill in the fields on the **Routing Personnel** page.  
5.  Choose the **OK** button to exit the page. The entered values are copied and assigned to the operation.    

## To create a new versions of a routing  
The version principle enables you to manage several versions of a routing. The structure of the routing version corresponds to the structure of the routing consisting of the routing version header and the routing version lines. The basic difference is defined by the starting date.  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Routings**, and then choose the related link.  
2.  Select the routing to be copied, and then choose the **Versions** action.  
3. On the **Routing Versions** page, choose the **New** action.
4. Fill in the fields as necessary.
5.  In the **Version Code** field, enter the unique identification of the version. Any combination of numbers and letters is permitted.  

    The newly created version is automatically assigned the status **New**.  
6.  To create operation lines, select the first blank line, and then fill in the **Operation No.** field according to the sequence of operations.

    The operation lines are sorted in ascending order by operation numbers. To be able to make changes later, we recommend you to select adequate step widths. The **Next Operation No.** field refers to the following operation. The number of the operation can be entered directly.

7. When the routing version is completed, setting the **Status** field to **Certified**.

The time validity of the version is specified by the **Starting Date** field.  

## See Also  
[Create Production BOMs](production-how-to-create-production-boms.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Planning](production-planning.md)   
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
