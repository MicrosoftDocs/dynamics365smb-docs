---
    title: How to Move Components to an Operation Area in Basic Warehouse Configurations | Microsoft Docs
    description: If item processing operations occur at your warehouse location, then you may have to move items between internal bins to respond to internal source documents, such as production, assembly, or service orders at the location.
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
# Move Components to an Operation Area in Basic Warehouse Configurations
If item processing operations occur at your warehouse location, then you may have to move items between internal bins to respond to internal source documents, such as production, assembly, or service orders at the location.  

> [!NOTE]  
>  For information about moving items between bins without source documents, see Internal Movement.  

In advanced warehouse configurations, which are locations that use the **Directed Put-away and Pick** setup field, you can use the **Movement Worksheet** page to move items between bins. For more information, see [Move Items in Advanced warehouse Configurations](warehouse-how-to-move-items-in-advanced-warehousing.md).  

In basic warehouse configurations, which are locations that use the **Bin Mandatory** setup field and the **Require Pick** setup field, you can register movement of items to internal operation areas based on internal source documents in the following ways:  

-   With the **Inventory Movement** page.  
-   With the **Inventory Pick** page.  

> [!NOTE]  
>  Inventory picks also post negative item ledger entries as consumption and are only supported for production components. For more information, see the Inventory Pick page.  

For detailed information about inventory movements, see the Inventory Movement page.  

Two different roles can create the initial inventory movement. An assembly worker, for example, can create it from a released assembly order so that it shows up in the warehouse worker’s list of work to do. To create an inventory movement for assembly order lines that are ready to have components moved to their specified bins, the assembly worker uses the **Create Inventory Movement** function.  

Alternatively, a warehouse worker can create it by pointing to the released assembly order in question. This is described in the following procedure.  

> [!NOTE]  
>  If the movement is for an assembly order where the item is assembled to a sales order, then you can define that the inventory movement document is automatically created when you create the inventory pick document that takes the finished assembly item and posts the shipment. To set this up, select the **Create Movements Automatically** field on the **Assembly Setup** page  
>   
>  For more information about assembly orders and basic warehouse configurations, see [Handling Assemble-to-Order Items with Inventory Picks](warehouse-how-to-pick-for-production.md#handling-assemble-to-order-items-with-inventory-picks).  

This procedure shows how to create an inventory movement from the **Inventory Movement** page by referencing a released assembly order as a source document. The procedure is the same when you move components for production orders and service orders.  

## To move components to an operation area in basic warehouse configurations  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Movement**, and choose the relevant link.  
2.  On the **General** FastTab, fill in the **No.** field. You can press the Enter key  to select from the number series.  
3.  In the **Location Code** field, enter the location where the movement occurs.  
4.  Choose the **Get Source Documents** action. Alternatively, fill in the **Source Document** field, and then choose the **AssistEdit** button in the **Source No.** field.  
5.  On the **Source Documents** page, select the assembly order that you want to move components for, and then choose the **OK** button.  

    For each needed component that can be moved, one Take line and one Place line are generated on the **Inventory Movements** page. All fields except the **Qty. to Handle** field are prefilled according to the source document lines. The **Qty. to Handle** field is set to zero until you enter the quantity that you have actually moved.  

    You can change the bin code on a Take line but only according to availability. If you choose the **AssistEdit** button in the **Bin Code** field on a Take line, then the **Bin Contents** page opens and only shows bins where the component is available.  

    You cannot change the bin code on a Place line. Only the bin code that is defined on the component line of the source document is accepted. This supports the principle that the role who requests a component, which is an assembly worker in this procedure, knows where the component must be placed. If you want to place the components in a different bin, then you must first change the bin code on the component line and then re-create the inventory movement lines.  
6.  In the **Qty. to Handle** field, enter the full or partial quantity that you have actually moved. The value on the Take and the Place lines must be the same. Otherwise, you cannot register the movement.  

    > [!NOTE]  
    >  As in other warehouse activities, you can split the Place line by selecting the **Actions** action and then choosing the **Split Line** action. In that case, the sum of the two split Place lines must equal the quantity on the Take line.  

7.  When you are ready to register the movements that you have performed, choose the **Register Invt. Movement** action.  

    Warehouse entries are created reflecting that the components now exist in the bins specified on the assembly order lines.  

    > [!NOTE]  
    >  Unlike when you move components with an inventory pick, consumption is not posted when you register an inventory movement. That step must be performed separately by posting the assembly order output and consumption. For more information, see Assembly Order.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
