---
    title: How to Create Put-aways from Internal Put-aways | Microsoft Docs
    description: After items have been put away and before they are picked to fulfill the needs of a production order or shipment, they are stored in the warehouse as part of available inventory.
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
# Pick and Put Away Without a Source Document
After items have been put away and before they are picked to fulfill the needs of a production order or shipment, they are stored in the warehouse as part of available inventory.  

Situations can arise where items must be taken out of the warehouse pick bins temporarily, perhaps to serve as demonstration models in a sales presentation. These items are still owned by the company and are part of inventory, but they are not available for picking. They are registered in a special purpose bin that you create for this purpose; technically, the items are in the warehouse, but physically, they could be in a conference or demonstration room.  

In other situations, the production unit might unexpectedly need a few parts for a process. You can pick items for the production bins using the internal pick. When the process is over and output is created, you post the consumption of the items and empty the production bin, which in turn decreases the quantity of the item at your location.  

Likewise, items can be returned to the warehouse to be put away. The items may have been taken out of available inventory for a production order, and then not used at all. To make them part of available inventory again, they must be put away in the bin.  

The **Internal Put-aways** enables you to perform put-aways without having to refer to a particular source document. You can easily set up all the information you need to create a put-away warehouse instruction.  

> [!NOTE]  
>  If you are not using internal picks and internal put-aways, these adjustments can be performed using the methods to move items from bin to bin or to post quantity adjustments in a bin.  
>   
>  When the location uses directed put-away and pick, and therefore uses bin types, you cannot manually move items in or out of a bin of bin type RECEIVE, because items that are in a RECEIVE-type bin must be registered as being put away before they are part of available inventory.  

## To create an internal pick  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Whse. Internal Pick**, and then choose the related link.  
2.  Fill in the **No.** field and the **To Bin Code** field on the **General** FastTab. The **To Bin Code** field specifies the bin from which you want to get the items. For production purposes, this bin would be the inbound production bin or the open shop bin. For other purposes, choose a To Bin Code of a bin type that is not used for picking, most likely a staging, shipping or special purpose bin.  
3.  Select an item in the **Item No.** field, and fill in the quantities you want to pick.  
4. Choose the **Create Pick** action. A warehouse pick instruction is now ready for a warehouse employee to perform.  

## To create an internal put-away  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Whse. Internal Put-away**, and then choose the related link.  
2.  Fill in the **No.** and **From Bin Code** fields on the **General** FastTab. The **From Bin Code** field specifies the bin where the items being returned to the warehouse, perhaps from production, are located.  
3.  Fill in the item numbers and quantities on the lines.  
4.  Choose the **Create Put-away** action. A warehouse put-away instruction is now ready for a warehouse employee to perform.  

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
