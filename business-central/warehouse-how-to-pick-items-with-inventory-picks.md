---
    title: How to Pick Items with Inventory Picks | Microsoft Docs
    description: If a location is set up to require pick processing but not shipment processing, you use the inventory pick documents to record and post picking and shipping information for your source documents.
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
# Pick Items with Inventory Picks
When your location is set up to require pick processing but not shipment processing, you use the **Inventory Pick** page to record and post picking and shipping information for your source documents. The outbound source document can be a sales order, a purchase return order, an outbound transfer order, or a production order whose components are ready to be picked.

> [!NOTE]  
> Components for assembly orders cannot be picked or posted with inventory picks. Instead, use the **Inventory Movement** page. For more information, see [Move Components to an Operation Area in Basic Warehousing](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

>  When picking and shipping sales line quantities that are assembled to the order, you must follow certain rules when creating the inventory pick lines. For more information, see the “Handling Assemble-to-Order Items in Inventory Picks” section.  

You can create an inventory pick in three ways:  

- Create the pick in two steps by first requesting an inventory pick by releasing the source document. This signals to the warehouse that the source document is ready for picking. The inventory pick can then be created on the **Inventory Pick** page based on the source document.  
- Create the inventory pick directly from the source document itself.  
- You can create inventory picks for several source documents at the same time by using the batch job.  

## To request an inventory pick by releasing the source document  
For sales orders, purchase return orders, and outbound transfer orders, you create the warehouse request by releasing the order. The following describes how to do this from a sales order.

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Select the sales order that you want to release, and then choose the **Release** action.

For production orders, you automatically create the warehouse request for the picking of components, called *flushing*, when the production order status is changed to **Released** or when the released production order is created. For more information, see [Pick for Production or Assembly](warehouse-how-to-pick-for-production.md).

After the warehouse request has been created, a warehouse employee assigned to picking items can see that the source document is ready to be picked and can create a new pick document based on the warehouse request.  

## To create an inventory pick based on the source document
Now that the request is created, the warehouse employee can create a new inventory pick based on the released source document.
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Picks**, and then choose the related link.  
2.  Choose the **New** action.  
3. In the **Source Document** field, select the type of source document you are picking for.  
4. In the **Source No.** field, select the source document.  
5. Alternatively, choose the **Get Source Document** action to select the document from a list of outbound source documents that are ready for picking at the location.  
6. Choose the **OK** button to fill the pick lines according to the selected source document.  

## To create an inventory pick from the source document  
1.  In the source document, which can be a sales order, purchase return order, outbound transfer order, or production order, choose the **Create Inventory Put-away/Pick** action.
2.  Select the **Create Invt. Pick** check box.  
3.  Choose the **OK** button. A new inventory pick will be created.

## To create multiple inventory picks with a batch job  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Create Invt. Put-away / Pick**, and then choose the related link.  
2.  On the **Warehouse Request** FastTab, use the **Source Document** and **Source No.** fields to filter on certain types of documents  or ranges of document numbers. For example, you can create picks only for sales orders.  
3. On the **Options** FastTab, select the **Create Invt. Pick** check box.
4. Choose the **OK** button. The specified inventory picks are created.

> [!NOTE]  
>  If picking and shipping sales line quantities that are assembled to the order you should follow certain rules when creating the inventory pick lines. For more information, see the “Handling Assemble-to-Order Items in Inventory Picks” section.  
>   
>  In basic warehouse configurations, items that are assembled to sales orders are picked from the related sales order, as explained in this topic. For more information, see “Handling Assemble-to-Order Items in Inventory Picks” in Inventory Pick.  

## To record the inventory picks  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Pick**, and then choose the related link.  
2. In the **Bin Code** field on the pick lines, the bin that the items must be picked from is suggesting per the item's default bin. You can change the bin in this page if necessary.  
3. Perform the pick and enter the information for the actual quantity put away in the **Qty. to Handle** field.

    If it is necessary to pick the items for one line from more than one bin, for example because they are not available in the designated bin, then use the **Split Line** function on the **Lines** FastTab. For more information about splitting lines, see [Split Warehouse Activity Lines](warehouse-how-to-split-warehouse-activity-lines.md).  
4. When you have performed the pick, choose the **Post** action.    

The posting process will post the shipment of the source document lines that have been picked, or in the case of production orders, the posting process will post the consumption. If the location uses bins, the posting will also create warehouse entries to post the bin quantity changes.  

## To delete inventory pick lines  
If items on the inventory pick are not available, then you can delete those inventory pick lines after posting and then delete the inventory pick document. The source document, such as a sales order or a production order, will have remaining items to be picked, which can be obtained through a new inventory pick later when the items become available.  

> [!WARNING]  
>  This process is not possible if serial/lot numbers are specified on the source document. For example, if a sales order line contains a serial/lot number, then that item tracking specification will be deleted if an inventory pick line for the serial/lot number is deleted.  
>   
>  If inventory pick lines have serial/lot numbers that are not available, you must not delete the lines in question. Instead, you must change the **Qty. to Handle** field to zero, post the actual picks, and then delete the inventory pick document. This ensures that the inventory pick lines for those serial/lot numbers can be recreated from the sales order later.  

## Handling Assemble-to-Order Items with Inventory Picks
The **Inventory Pick** page is also used to pick and ship for sales where items must be assembled before they can be shipped. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).

Items to be shipped are not physically present in a bin until they are assembled and posted as output to a bin in the assembly area. This means that picking assemble-to-order items for shipment follows a special flow. From a bin, warehouse workers take the assembly items to the shipping dock and then post the inventory pick. The posted inventory pick then posts the assembly output, the component consumption, and the sales shipment.

You can set up [!INCLUDE[d365fin](includes/d365fin_md.md)] to automatically create an inventory movement when the inventory pick for the assembly item is created. To enable this, you must select the **Create Movements Automatically** field on the **Assembly Setup** page. For more information, see [Move Components to an Operation Area in Basic Warehousing](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

Inventory pick lines for sales items are created in different ways depending on whether none, some, or all of the sales line quantities are assembled to order.

In regular sales where you use inventory picks to post shipment of inventory quantities, one inventory pick line, or several if the item is placed in different bins, is created for each sales order line. This pick line is based on the quantity in the **Qty. to Ship** field.

In assemble-to-order sales where the full quantity on the sales order line is assembled to order, one inventory pick line is created for that quantity. This means that the value in the Quantity to Assemble field is the same as the value in the **Qty. to Ship** field. The **Assemble to Order** field is selected on the line.

If an assembly output flow is set up for the location, then the value in the **Asm.-to-Order Shpt. Bin Code** field or the value in the **From-Assembly Bin Code** field, in that order, is inserted in the **Bin Code** field on the inventory pick line.

If no bin code is specified on the sales order line, and no assembly output flow is set up for the location, then the **Bin Code** field on the inventory pick line is empty. The warehouse worker must open the **Bin Contents** page and select the bin where the assembly items are assembled.

In combination scenarios, where a part of the quantity must first be assembled and another must be picked from inventory, a minimum of two inventory pick lines are created. One pick line is for the assemble-to-order quantity. The other pick line depends on which bins can fulfill the remaining quantity from inventory. Bin codes on the two lines are filled in different ways as described for the two different sales types respectively. For more information, see the “Combination Scenarios” section in [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
