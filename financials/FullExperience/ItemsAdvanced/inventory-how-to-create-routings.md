---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Create Routings
A routing holds master data that captures the process requirements of a given produced item. Once a production order is created for that item, its routing will govern the scheduling of operations as represented in the **Prod. Order Routing** window under the production order.  
  
 **Prerequisites**  
  
-   Item cards are created. For more information, see [How to: Register New Products](../how-to-register-new-products.md).  
  
-   Production resources are set up. For more information, see [How to: Set Up Work Centers](../how-to-set-up-work-centers.md).  
  
-   Gather all data about produced items, production resources, operation specifications, and process times.  
  
### To fill in the routing header  
  
1.  In the **Search** box, enter **Routings**, and then choose the related link.  
  
2.  Create a new routing. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  In the **No.** field, number the routing, for example, according to the process or the parent item.  
  
4.  In the **Description** field, name the routing, for example, after the process or the parent item.  
  
5.  In the **Type** field, select **Serial** to calculate the production routing according to the value in the **Operation No.** field.   
    Select **Parallel** to calculate the operations according to the value in the **Next Operation No.** field.  
  
6.  To edit the routing, set the **Status** field to **New** or **Under Development**. To activate it, set the **Status** field to **Certified**.  
  
### To fill in the routing lines  
  
1.  In the **Operation No.** field, enter the number of the first operation, for example,  **10**.  
  
2.  In the **Type** field, specify which kind of resource is used, for example, **Work Center**.  
  
3.  In the **No.** field, select the resource to be used, or type it in the field.  
  
4.  In the **Routing Link Code** field, enter a code to connect the component to a specific operation. ADD INCLUDE<!--[!INCLUDE[bp_choose_columns](../../includes/bp_choose_columns_md.md)]-->  
  
    > [!NOTE]  
    >  Routing links between operations and components ensure that material consumption is not posted until it has actually been consumed. In addition, routing links provide a process view in the **Production Journal** window where components are listed under the linked operation. For more information, see [How to: Create Routing Links](../how-to-create-routing-links.md).  
  
5.  In the **Run Time** and **Setup Time** fields, enter the process times needed to perform the operation.  
  
    > [!NOTE]  
    >  Setup time is calculated per production order, whereas run time is calculated per produced item.  
  
6.  In the **Concurrent Capacities** field, specify how many units of the selected resource are used to perform the operation. For example, two people allocated to one packing operation will halve the run time.  
  
7.  Continue to fill in lines for all operations involved in producing the item in question.  
  
8.  To copy lines from an existing routing, on the **Actions** tab, in the  **Functions** group, choose **Copy Routing** to select existing lines.  
  
9. Certify the routing.  
  
10. You can now attach the new routing to the card of the production item in question. For more information, see [How to: Register New Products](../how-to-register-new-products.md).  
  
> [!NOTE]  
>  Remember also to recalculate the item’s standard cost from the **Item** card: On the **Navigate** tab, in the **Item** group, choose **Manufacturing**, and then set **Calc. Standard Cost** to **All Levels**.  
  
## See Also  
 [Purpose of the Routings](../purpose-of-the-routings.md)