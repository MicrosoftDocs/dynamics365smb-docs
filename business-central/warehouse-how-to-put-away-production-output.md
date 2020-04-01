---
    title: How to Put Away Production Output | Microsoft Docs
    description: How you put away your output from production depends on how your warehouse is set up as a location.
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
# Put Away Production or Assembly Output
How you put away your output from production depends on how your warehouse is set up as a location. For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).  

In basic warehouse configurations where the location requires put-away processing, but not receive processing, you use the **Inventory Put-away** document to organize and record the put-away of output.  

In advanced warehouse configurations where the location requires both put-away and receive processing, you create either an internal put-away document or a movement document to put away the output.  

The first step in creating putting output away is to create the inbound warehouse request. This request informs the warehouse that the production or assembly order output is ready to be put away.

## To create the inbound warehouse request  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Order**, and then choose the related link.  
2.  On the production order that is ready for put-away, choose the **Create Inbound Whse. Request** action.  

> [!NOTE]  
>  You can also create the inbound warehouse request by selecting the **Create Inbound Request** check box when you refresh the production order. For more information, see [Refresh or Replan Production Orders](production-how-to-replan-refresh-production-orders.md).  

## To put output away with an inventory put-away  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Put-away**, and then choose the related link.  
2.  Create a new inventory put-away. For more information, see [Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md).
3.  To access the production order output, choose the **Get Source Documents** action, and then select the released production order.  
4.  Fill in the put-away lines as appropriate.
5.  When the lines are ready for posting, choose the **Post** action. The posting will create the necessary warehouse entries and post the output of the items.  

You can also create an **Inventory Put-away** directly from the released production order. For more information, see [Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md).  

When you post an inventory put-away, it is assumed that all the operations are posted according to the standard routing, that is, output quantity is posted according to the last operation. You can use the output journal to post variances in output quantity and the setup and run times. If it is required to post partially after you have created the inventory put-away, you can do so on setup times and quantities for all operations except the last one. In that case, the last operation is controlled by the inventory put-away.  

If you only need to post setup or run time on the last operation, then set the output quantity on the last operation to 0. Alternatively, you can choose not to post the last line at all by simply deleting it  

## To put output away with a warehouse internal put-away
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Whse. Internal Put-away**, and then choose the related link.  
2. Choose the **New** action.
3. Fill in the header of a new internal put-away with at least the **Location Code**.  
4. Fill in a line for each item you wish to move to the warehouse. You only have to fill in the **Item No.** and the **Quantity** fields.  

    > [!NOTE]  
    >  When you select the **Item No.** field, the **Bin Contents List** opens instead of the **Item List**. This is because you want to put away an item that is in a particular bin - a Bin Content - not just an item, and you already know the bin the item should be taken from.  

4.  To fill the worksheet lines with the entire bin content or the filtered bin content of bins in the location, choose the **Get Bin Content** action.  
5.  Choose the **Create Put-away** action, and the items you want to move out of production are now on put-away instructions waiting to be stored in the warehouse.  

> [!NOTE]  
>  When your warehouse location is set up to use directed put-away and pick, the warehouse is linked to your manufacturing facility through the default production bins: the inbound and outbound production bins and the open shop bin, all of which you define on the **Bins** FastTab of the location card. When you post the output of a production order, the output is placed in the **Outbound Production Bin**. You follow the same procedure as described above to put-away the production output, except that instead of using the item's default bin, you will move or put-away the items from the **Outbound Production Bin** to the item's default bin.  

## To manually specify a bin to store items from production output  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Movement Worksheet**, and then choose the related link.  
2.  Fill in the header, and create a line for each item you wish to move to the warehouse.  
3.  Fill in both the **From Bin Code** and the **To Bin Code** fields, and enter the quantity in the **Quantity** field.  
4.  To fill the worksheet lines with the entire bin content or the filtered bin content of bins in the location, choose the **Get Bin Content** action.  
5. Choose the **Create Movement** action. The warehouse movement instructions are created with Take and Place lines for warehouse employees to perform.  

> [!NOTE]  
>  You cannot enter the source document number, such as the Production Order No., in the internal put-away, put-away, or movement documents for either of these procedures.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
