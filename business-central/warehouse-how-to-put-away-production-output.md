---
    title: Put Away Production Output
    description: How you put away your output from production depends on how your warehouse is set up as a location. Inventory put-away can be performed in the following ways.
    author: SorenGP

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 06/25/2021
    ms.author: edupont

---
# Put Away Production or Assembly Output

How you put away your output from production depends on how your warehouse is set up as a location. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).  

In basic warehouse configurations where the location requires put-away processing, you use the **Inventory Put-away** document to post production output and record the put-away of output.  

> [!NOTE]  
> Inventory put-away is not supported for assembly processes. You post an assembly order to register output. If you use bins, you can move items between bins later. For more information, see [Move Items Ad Hoc in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md).  

In advanced warehouse configurations where the location requires both put-away and receive processing, you create either an internal put-away document or a movement document to put away the output.  

## To put away production output with an inventory put-away

The first step in creating putting output away is to create the inbound warehouse request. This request informs the warehouse that the production or assembly order output is ready to be put away.

### To create the inbound warehouse request  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Order**, and then choose the related link.  
2.  On the production order that is ready for put-away, choose the **Create Inbound Whse. Request** action.  

> [!NOTE]  
> You can also create the inbound warehouse request by choosing the **Create Inbound Request** field when you refresh the production order. For more information, see [Refresh or Replan Production Orders](production-how-to-replan-refresh-production-orders.md).  

### To put output away with an inventory put-away  
1.  Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Put-away**, and then choose the related link.  
2.  Create a new inventory put-away. For more information, see [Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md).
3.  To access the production order output, choose the **Get Source Documents** action, and then select the released production order.  
4.  Fill in the put-away lines as appropriate.
5.  When the lines are ready for posting, choose the **Post** action. The posting will create the necessary warehouse entries and post the output of the items.  

You can also create an **Inventory Put-away** directly from the released production order. For more information, see [Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md).  

When you post an inventory put-away, it is assumed that all the operations are posted according to the standard routing, that is, output quantity is posted according to the last operation. You can use the output journal to post variances in output quantity and the setup and run times. If it is required to post partially after you have created the inventory put-away, you can do so on setup times and quantities for all operations except the last one. In that case, the last operation is controlled by the inventory put-away.  

If you only need to post setup or run time on the last operation, then set the output quantity on the last operation to 0. Alternatively, you can choose not to post the last line at all by simply deleting it  

## To put assembly and production output away in advanced warehouse configurations
When you post the output of production or assembly order in the  warehouse that is set up to use directed put-away and pick, the output is placed in the bin defined in the production or assembly order. 

The following table describes different ways of moving items within the warehouse with advanced configurations where all warehouse activities must be performed in a directed workflow. 

|**To**|**See**|  
|------------|-------------|  
|Move items with the warehouse movement worksheet.|[Move Items in Advanced Warehouse Configurations](warehouse-how-to-move-items-in-advanced-warehousing.md#to-move-items-with-the-warehouse-movement-worksheet)|  
|Create an internal put-away to put produced or assembled items away in an advanced warehouse configuration.|[Create an internal put-away](warehouse-how-to-create-put-aways-from-internal-put-aways.md#to-create-an-internal-put-away)|

> [!NOTE]  
> You cannot enter the source document number, such as the Production Order No., in the internal put-away, put-away, or movement documents for either of these procedures.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
