---
    title: How to Pick Items for Warehouse Shipment | Microsoft Docs
    description: When the location is set up to require warehouse pick processing as well as warehouse shipment processing, you use the warehouse pick documents to create and process pick information prior to posting the warehouse shipment.
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
# How to: Pick Items for Warehouse Shipment
When the location is set up to require warehouse pick processing as well as warehouse shipment processing, you use the warehouse pick documents to create and process pick information prior to posting the warehouse shipment.  

 You cannot create a warehouse pick document from scratch because a pick activity is always part of a workflow, either in a pull or a push scenario.  

 You can create warehouse pick documents in a pull fashion by opening an empty warehouse shipment document, detect source documents that are released to shipment, and then create warehouse pick lines for those shipments. You can use the **Get Source Documents** or **Use Filter to Get Source Documents** functions to detect source documents that are ready for shipment. Alternatively, you can use the **Pick Worksheet** window to pull and create pick lines in batch mode. For more information, see [How to: Plan Picks in Worksheets](../how-to-plan-picks-in-worksheets.md).  

 You can also create warehouse pick documents in a push fashion from the **Warehouse Shipment** window by selecting **Create Pick**.  

> [!NOTE]  
>  Picking for warehouse shipment of items that are assembled to the sales order being shipped follows the same steps as for regular warehouse picks for shipment, as described in this topic. However, the number of pick lines per quantity to ship may be many to one because you pick the components, not the assembly item.  
>   
>  The warehouse pick lines are created for the value in the **Remaining Quantity** field on the lines of the assembly order that is linked to the sales order line that is being shipped. This ensures that all components are picked in one action.  
>   
>  For more information, see “Handling Assemble-to-Order Items in Warehouse Shipments” in Warehouse Shipment.  
>   
>  For information about picking components for assembly orders generally, including situations where the assembly item is not due on a sales shipment, see [How to: Pick for Internal Operations in Advanced Warehouse Configurations](../how-to-pick-for-internal-operations-in-advanced-warehousing.md).  

### To pick items for warehouse shipment  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Picks**, and then choose the related link.  

     If you need to work on a particular pick, select the pick from the list or filter the list to find the picks that have been assigned to you specifically. Open the pick card.  

2.  If the **Assigned User ID** field is empty, enter your ID to identify yourself if necessary.  

3.  If you want a printed pick document for the lines in the window, on the **Home** tab, in the **Process** group, choose **Print**.  

4.  Perform the actual picking of items.  

     If the warehouse is set up to use bins, then the items’ default bins are used to suggest where to take the items from. The instructions appear as two separate lines, at least one for each action type, Take and Place.  

     If the warehouse is set up to use directed put-away and pick, then the bin ranking is used to calculate the best bins to pick from, and those bins are then suggested on the pick lines. The instructions appear as two separate lines, at least one for each action type, Take and Place.  

5.  When you have performed the pick and placed the items in the shipping area or shipping bin, select **Register Pick**.  

 The person responsible for shipment can now bring the items to the shipment dock and post the shipment, including the related source document, in the **Warehouse Shipment** window.  

 In addition to picking for source documents, as described in this topic, you can take and place items between bins without referring to source documents. For more information, see [How to: Move Items in advanced warehouse configurations](../how-to-move-items-in-advanced-warehousing.md).  

 You can perform internal picks for items that belong to the company but are not available for ordinary warehouse picking. For more information, see Whse. Internal Pick.  

## See Also  
 Warehouse Pick   
 Warehouse Shipment   
 Bin Ranking   
 Remaining Quantity   
 [How to: Use Filters to Get Source Documents](../how-to-use-filters-to-get-source-documents.md)   
 [Pick Items](../pick-items.md)   
 [How to: Plan Picks in Worksheets](../how-to-plan-picks-in-worksheets.md)   
 [How to: Sell Items Assembled to Order](../how-to-sell-items-assembled-to-order.md)   
 [How to: Prepare Shipments](../How%20to:%20Prepare%20Shipments.md)   
 [How to: Sell Items Assembled to Order](../how-to-sell-items-assembled-to-order.md)   
 [Design Details: Warehouse Management](../../design-details-warehouse-management.md)
