---
    title: How to Pick Items for Warehouse Shipment | Microsoft Docs
    description: When the location is set up to require warehouse pick processing as well as warehouse shipment processing, you use the warehouse pick documents to create and process pick information prior to posting the warehouse shipment.
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
# Pick Items for Warehouse Shipment
When the location is set up to require warehouse pick processing as well as warehouse shipment processing, you use the warehouse pick documents to create and process pick information prior to posting the warehouse shipment.  

You cannot create a warehouse pick document from scratch because a pick activity is always part of a workflow, either in a pull or a push scenario.  

You can create warehouse pick documents in a pull fashion by opening an empty warehouse shipment document, detect source documents that are released to shipment, and then create warehouse pick lines for those shipments. You can use the **Get Source Documents** or **Use Filter to Get Source Documents** functions to detect source documents that are ready for shipment.

Alternatively, you can use the **Pick Worksheet** page to pull and create pick lines in batch mode. For more information, see [Plan Picks in Worksheets](warehouse-how-to-plan-picks-in-worksheets.md).  

You can also create warehouse pick documents in a push fashion from the **Warehouse Shipment** page by selecting **Create Pick**.  

> [!NOTE]  
>  Picking for warehouse shipment of items that are assembled to the sales order being shipped follows the same steps as for regular warehouse picks for shipment, as described in this topic. However, the number of pick lines per quantity to ship may be many to one because you pick the components, not the assembly item.  
>   
>  The warehouse pick lines are created for the value in the **Remaining Quantity** field on the lines of the assembly order that is linked to the sales order line that is being shipped. This ensures that all components are picked in one action.  
>   
>  For more information, see the “Handling Assemble-to-Order Items in Warehouse Shipments” section.  
>   
>  For information about picking components for assembly orders generally, including situations where the assembly item is not due on a sales shipment, see [Pick for Production or Assembly](warehouse-how-to-pick-for-production.md).  

## To pick items for warehouse shipment  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Picks**, and then choose the related link.  

    If you need to work on a particular pick, select the pick from the list or filter the list to find the picks that have been assigned to you specifically. Open the pick card.  
2.  If the **Assigned User ID** field is empty, enter your ID to identify yourself if necessary.  
3.  Perform the actual picking of items.  

    If the warehouse is set up to use bins, then the items’ default bins are used to suggest where to take the items from. The instructions appear as two separate lines, at least one for each action type, Take and Place.  

    If the warehouse is set up to use directed put-away and pick, then the bin ranking is used to calculate the best bins to pick from, and those bins are then suggested on the pick lines. The instructions appear as two separate lines, at least one for each action type, Take and Place.  

4.  When you have performed the pick and placed the items in the shipping area or shipping bin, choose the **Register Pick** action.  

The person responsible for shipment can now bring the items to the shipment dock and post the shipment, including the related source document, on the **Warehouse Shipment** page. For more information, see [Ship Items](warehouse-how-ship-items.md).   

In addition to picking for source documents, as described in this topic, you can take and place items between bins without referring to source documents. For more information, see [Pick and Put Away Without a Source Document](warehouse-how-to-create-put-aways-from-internal-put-aways.md).  

## Handling Assemble-to-Order Items in Warehouse Shipments
In assemble-to-order scenarios, the **Qty. to Ship** field on warehouse shipment lines is used to record how many units are assembled. The specified quantity is then posted as assembly output when the warehouse shipment is posted.

For other warehouse shipment lines, the value in the **Qty. to Ship** field is zero from the start.

When workers in charge of assembly finish assembling parts or all of the assemble-to-order quantity, they record it in the **Qty. to Ship** field on the warehouse shipment line and then choose the **Post Shipment** action. The result is that the corresponding assembly output is posted, including the component consumption. A sales shipment for the quantity is posted for the sales order.

From the assembly order, you can choose **Asm.-to-Order Whse. Shpt. Line** to access the warehouse shipment line. This is convenient for workers who do not typically use the **Warehouse Shipment** page.

After the warehouse shipment is posted, various fields on the sales order line are updated to show progress in the warehouse. The following fields are also updated to show how many assemble-to-order quantities remain to be assembled and shipped:

- **ATO Whse. Outstanding Qty.**
- **ATO Whse. Outstd. Qty. (Base)**

> [!NOTE]
> In combination scenarios, in which a part of the quantity must first be assembled and another must be shipped from inventory, two warehouse shipment lines are created. One is for the assemble-to-order quantity, and one is for the inventory quantity.

> In that case, the assemble-to-order quantity is handled as described in this topic, and the inventory quantity is handled as any other regular warehouse shipment line. For more information about combination scenarios, see [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
