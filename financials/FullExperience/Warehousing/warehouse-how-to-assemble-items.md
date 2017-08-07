---
    title: How to: Assemble Items | Microsoft Docs
    description: If the **Replenishment System** field on the item card contains **Assembly**, then the default method of supplying the item is to assemble it from defined components and potentially by a defined resource.
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
# How to: Assemble Items
If the **Replenishment System** field on the item card contains **Assembly**, then the default method of supplying the item is to assemble it from defined components and potentially by a defined resource.  
  
 The components and resources that go into this kind of an assembly item must be defined in an assembly BOM. For more information, see [How to: Create Assembly BOMs](../how-to-create-assembly-boms.md).  
  
 Assembly items can be set up for two different assembly processes:  
  
-   Assemble to stock.  
  
-   Assemble to order.  
  
 You typically use **Assemble to Stock** for items that you want to assemble ahead of sales, such as to prepare for a kit campaign, and keep in stock until they are ordered. These items are usually standard items such as packaged kits that you do not offer to customize to customer requests.  
  
 You typically use **Assemble to Order** for items that you do not want to stock because you expect to customize them to customer requests or because you want to minimize the inventory carrying cost by supplying them just in time. For more information, see [How to: Sell Items Assembled to Order](../how-to-sell-items-assembled-to-order.md).  
  
 For more information about how to set up an assembly item, see [Assemble to Order or Assemble to Stock](../assemble-to-order-or-assemble-to-stock.md).  
  
> [!NOTE]  
>  These setup options are default settings that manage how sales and assembly order lines are initially processed. You can depart from these defaults and supply the assembly item in the most optimal way when processing a sale. For more information, see [How to: Sell Inventory Items in Assemble-to-Order Flows](../how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  
  
 In this procedure, you create and process an assembly order for items that are assembled to stock, which means without a linked sales order. The steps include initiating the assembly order, handling potential component availability issues, and partially posting assembly item output.  
  
### To assemble an item  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Assembly Orders**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**. The **New Assembly Order** window opens.  
  
3.  In the **No.** field, press the Enter key to insert a new number from the assembly order number series. Alternatively, enter a number manually.  
  
4.  In the **Item No.** field, select the assembly item that you want to process. The field is filtered to show only items that are set up for assembly, which means that they have assembly BOMs assigned.  
  
5.  In the **Quantity** field, enter how many units of the item that you want assembled.  
  
    > [!NOTE]  
    >  If one or more components are not available to fulfill the entered assembly item quantity on the defined due date, then the **Assembly Availability** window automatically opens to provide detailed information about how many assembly items can be assembled based on component availability. For more information about this window, see Assembly Availability. ADD INCLUDE<!--[!INCLUDE[bp_windownoneditable](../../includes/bp_windownoneditable_md.md)]--> When you close the window, the assembly order is created with availability alerts on the affected component lines.  
  
     The assembly order lines are automatically filled with the contents of the assembly BOM and with line quantities according to the assembly order header.  
  
    > [!NOTE]  
    >  If the **Assembly Availability** window opened when you filled in the assembly order header, then each affected assembly order line contains a **Yes** in the **Avail. Warning** field with a link to detailed availability information. For more information, see Check Availability. You can resolve a component availability issue by postponing the starting date, replacing the component with another item, or selecting an available substitution if one is defined.  
  
6.  In the **Quantity to Assemble** field, enter how many units of the assembly item that you want to post as output the next time that you post the assembly order. This quantity can be lower than the value in the **Quantity** field to reflect a partial output posting.  
  
    > [!NOTE]  
    >  To make sure that component consumption posting matches the assembly item output posting, the quantity fields in the assembly order lines automatically adjust to the value that you enter in the **Quantity to Assemble** field.  
  
7.  On assembly order lines of type **Item** or **Resource**, in the **Quantity to Consume** field, specify how many units you want to post as consumed the next time that you post the assembly order. By default, the expected quantity to consume according to the assembly BOM and the assembly order header quantity is inserted, but you can increase or decrease it, such as to reflect an overconsumption of components or that extra resources were used.  
  
8.  When you are ready to partially or fully post, on the **Actions** tab, in the **Posting** group, choose **Post**.  
  
    > [!NOTE]  
    >  If warnings are still present in any of the assembly order lines, then the posting is blocked. A message about which component or components are not in inventory is displayed.  
  
     After posting succeeds, the assembly item is posted as output to the location code and potential bin code that are defined on the assembly order. For manually created assembly orders, the location may be copied from the **Default Location for Orders** setup field. For assemble-to-order flows, the location code may be copied from the sales order line.  
  
## See Also  
 Assembly Order   
 Replenishment System   
 Quantity to Assemble   
 Assembly Availability   
 Check Availability   
 Quantity to Consume   
 [How to: Create Assembly BOMs](../how-to-create-assembly-boms.md)   
 [How to: Sell Items Assembled to Order](../how-to-sell-items-assembled-to-order.md)   
 [How to: Sell Inventory Items in Assemble-to-Order Flows](../how-to-sell-inventory-items-in-assemble-to-order-flows.md)   
 [How to: Sell Assemble-to-Order Items and Inventory Items Together](../how-to-sell-assemble-to-order-items-and-inventory-items-together.md)   
 [Assemble to Order or Assemble to Stock](../assemble-to-order-or-assemble-to-stock.md)