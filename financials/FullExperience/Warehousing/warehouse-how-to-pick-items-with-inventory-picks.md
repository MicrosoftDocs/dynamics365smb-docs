---
    title: How to Pick Items with Inventory Picks | Microsoft Docs
    description: If a location is set up to require pick processing but not shipment processing, you use the inventory pick documents to record and post picking and shipping information for your source documents.
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
# How to: Pick Items with Inventory Picks
If a location is set up to require pick processing but not shipment processing, you use the inventory pick documents to record and post picking and shipping information for your source documents.  
  
 The source document can be a sales order, purchase return order, outbound transfer order, or production order with components ready to be picked.  
  
 Components for assembly orders cannot be picked or posted with inventory picks. Instead, use inventory movements. For more information, see Inventory Movement.  
  
> [!NOTE]  
>  If picking and shipping sales line quantities that are assembled to the order you should follow certain rules when creating the inventory pick lines. For more information, see “Handling Assemble-to-Order Items in Inventory Picks” in Inventory Pick.  
  
### To pick items with inventory picks  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Inventory Pick**, and then choose the related link.  
  
2.  To begin working on the pick document, you can either open a pick document that has already been created, or you can create a new document. For more information, see [How to: Create Inventory Picks](../how-to-create-inventory-picks.md).  
  
     To open a previously created pick document, on the **Navigate** tab, choose **List**, and then select the pick that you would like to work with.  
  
3.  In the pick lines, if you are using bins, ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> specifies the bin from which the item should be picked by suggesting the item's default bin in the **Bin Code** field. You can change the bin in this window if necessary.  
  
4.  To create a printed picking list for the lines in the window, on the **Actions** tab, choose **Print** to open the **Picking List** report window.  
  
5.  Perform the pick, and enter the actual quantity picked in the **Qty. to Handle** field.  
  
     If it is necessary to take the items for one line from more than one bin, on the **Lines** FastTab, choose **Functions**, and then select **Split Line**. For more information, see [Splitting Lines](../how-to-split-warehouse-activity-lines.md).  
  
6.  When you have performed the pick, post the pick document.  
  
 The posting process will post the shipment of the source document lines that have been picked, or in the case of production orders, the posting process will post the consumption. If the location uses bins, the posting will also create warehouse entries to post the bin quantity changes.  
  
 You can see the posted pick information in the **Posted Invt. Picks** window.  
  
#### To delete inventory pick lines  
 If items on the inventory pick are not available, then you can delete those inventory pick lines after posting and then delete the inventory pick document. The source document, such as sales order or a production order, will have remaining items to be picked, which can be obtained through a new inventory pick later when the items become available.  
  
> [!WARNING]  
>  This process is not possible if serial/lot numbers are specified on the source document. For example, if a sales order line contains a serial/lot number, then that item tracking specification will be deleted if an inventory pick line for the serial/lot number is deleted.  
>   
>  If inventory pick lines have serial/lot numbers that are not available, you must not delete the lines in question. Instead, you must change the **Qty. to Handle** field to zero, post the actual picks, and then delete the inventory pick document. This ensures that the inventory pick lines for those serial/lot numbers can be recreated from the sales order later.  
  
## See Also  
 Inventory Pick   
 Inventory Movement   
 [Picking by FEFO](../picking-by-fefo.md)   
 [How to: Move Components to an Operation Area in Basic Warehousing](../how-to-move-components-to-an-operation-area-in-basic-warehousing.md)   
 [How to: Pick for Production in Basic Warehousing](../how-to-pick-for-production-in-basic-warehousing.md)   
 [How to: Pick for Internal Operations in Advanced Warehousing](../how-to-pick-for-internal-operations-in-advanced-warehousing.md)   
 [How to: Pick Items for Warehouse Shipment](../how-to-pick-items-for-warehouse-shipment.md)   
 [Pick Items](../pick-items.md)   
 [Design Details: Warehouse Management](../design-details-warehouse-management.md)