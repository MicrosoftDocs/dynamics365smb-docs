---
    title: How to Put Items Away with Inventory Put-aways | Microsoft Docs
    description: When your location is setup to require put-away processing but not receive processing, you use the **Inventory Put-away** document to record and post put-away and receipt information for your source documents. The inbound source document can be a purchase order, a sales return order, an inbound transfer order, or a production order whose output is ready for put-away.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 08/16/2017
    ms.author: sgroespe

---
# How to: Put Items Away with Inventory Put-aways
When your location is setup to require put-away processing but not receive processing, you use the **Inventory Put-away** document to record and post put-away and receipt information for your source documents. The inbound source document can be a purchase order, a sales return order, an inbound transfer order, or a production order whose output is ready for put-away.  

You have three options for creating an inventory put-away:  

    -   Create the put-away in two steps by first creating a warehouse request from the source document, which acts as a signal to the warehouse that the source document is ready for put-away. The inventory put-away can then be created from the **Inventory Put-away** window based on the source document.  
    -   Create the inventory put-away directly from the source document itself.  
    -   You can create inventory put-aways for several source documents at once by using the batch job.  

Each of these three methods is described below.  

## To request an inventory put-away by releasing the source document
In the case of purchase orders, sales return orders, and inbound transfer orders, you create the warehouse request by releasing the order. The following describes how to do this from a purchase order.  

1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Orders**, and then choose the related link.
2. Open the purchase order that you want to release.  
3.  Choose the **Release** action.  

    In the case of production orders, you create the warehouse request by creating an inbound request from the released production order.  
4.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Released Production Orders**, and then choose the related link.  
5. Choose the **Create Inbound Whse. Request** action.  

> [!NOTE]  
>  You can also create the inbound warehouse request by selecting the **Create Inbound Request** check box when you refresh the production order. For more information, see [How to: Refresh Production Orders](production-how-to-refresh-production-orders.md).  

When the warehouse request is created, someone working in the warehouse creating put-aways can see that the source document is ready and can create an inventory put-away document.  

## To create an inventory put-away based on the source document  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Inventory Put-away**, and then select the related link.  
2. Choose the **New** action.  
3. In the **Source Document** field, select the type of source document you are putting away from.  
4. In the **Source No.** field, select the source document.  
5. Alternatively, choose the **Get Source Document** action to select the document from a list of inbound source documents that are ready for put-away at the location.  
6. Choose the **OK** button to fill the put-away lines according to the selected source document.  

## To create an inventory put-away from the source document  
1.  In the source document, which can be a purchase order, sales return order, inbound transfer order, or production order, choose the **Create Inventory Put-away/Pick** action.  
2. Select the **Create Invt. Put-away** check box.
3. Choose the **OK** button. A new inventory put-away is created.

## To create several inventory put-aways with a batch job  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Create Invt. Put-away / Pick**, and then choose the related link.  
2.  On the **Warehouse Request** FastTab of the request window, use the **Source Document** and **Source No.** fields to filter on certain types of documents or ranges of document numbers.  
3.  On the **Options** FastTab, select the **Create Invt. Put-away** check box.
4.  Choose the **OK** button. The specified inventory put-aways are be created.

## To record the inventory put-away  
1. Open a previously created put-away document by selecting one from the **Inventory Put-aways** window.  
2. On the put-away lines, if you are using bins, the bin is specified to which the item should be picked by suggesting the item's default bin in the **Bin Code** field. You can change the bin in this window if necessary.  
3. Perform the put-away and enter the information for the actual quantity put away in the **Qty. to Handle** field.  

    If it is necessary to place the items for one line in more than one bin, use the **Split Line** function on the **Lines** FastTab. For more information about splitting lines, see [How to: Split Warehouse Activity Lines](warehouse-how-to-split-warehouse-activity-lines.md).  
4. When you have performed the put-away, choose the **Post** action.  

The posting process will post the receipt, or for production orders, the output, of the source document lines that have been put away, and if the location uses bins, the posting will also create warehouse entries to post the bin quantity changes.

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
