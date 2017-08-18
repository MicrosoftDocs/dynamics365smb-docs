---
    title: How to Create Inventory Picks | Microsoft Docs
    description: When your location is set up to require pick processing but not shipment processing, you use the **Inventory Pick** document to organize and record your picking activity.
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
# How to: Create Inventory Picks
When your location is set up to require pick processing but not shipment processing, you use the **Inventory Pick** document to organize and record your picking activity.  
  
 You have the following options for creating an inventory pick:  
  
-   Create the pick in two steps by first requesting an inventory pick by releasing the source document. This signals to the warehouse that the source document is ready for picking. The inventory pick can then be created in the **Inventory Pick** window.  
  
-   Create the inventory pick directly from the source document itself.  
  
-   You can create inventory picks for several source documents at the same time by using the batch job.  
  
 Each of these three methods is described in this topic.  
  
## To request an inventory pick by releasing the source document  
  
-   For sales orders, purchase return orders, and outbound transfer orders, you create the warehouse request by releasing the order. To do this, on the **Actions** tab, in the **Release** group, choose **Release**.  
  
-   For production orders, you create the warehouse request for the picking of components when the production order status is changed to **Released** or when the released production order is created.  
  
-   After the warehouse request has been created, someone working in the warehouse creating picks can see that the source document is ready to be picked and can create a new pick document based on the warehouse request.  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Inventory Picks**, and then choose the related link.  
  
2.  Create a new pick.  
  
3.  Select a source document for the inventory pick by filling in the **Location Code** and **Source Document** fields, and then select a source document in the **Source No.** field.  
  
     To select a source document, on the **Home** tab, in the **Process** group, choose **Get Source Document** to see a list of outbound source documents available for picking in the location. This list will include all released source documents for the location. Select the document that you want to work with and then choose the **OK** button.  
  
 The pick lines will fill with the lines for the source document that are ready for picking from the location specified.  
  
### To create an inventory pick from the source document  
  
1.  In the source document, which can be a sales order, purchase return order, outbound transfer order, or production order, on the **Actions** tab, in the **Warehouse** group, choose **Create Inventory Put-away/Pick/Movement**.  
  
2.  In the **Create Invt. Put-away/Pick/Movement** window, select the **Create Invt. Pick** field. If you want to create a pick list, select the **Print Document** field.  
  
3.  Choose the **OK** button. The inventory pick will be created, and if you selected the **Print Document** field, the pick list will be printed.  
  
### To create multiple inventory picks with the batch job  
  
1.  Open the ![Shortcut icon](../media/shortcutcoldicon.gif "shortcutColdIcon")**Create Invt. Put-away / Pick** window.  
  
2.  In the **Options** FastTab, select the **Create Invt. Pick** field. If you want to print a pick list, select in the **Print Document** field.  
  
3.  On the **Warehouse Request** FastTab, use the **Source Document** and **Source No.** fields to filter on certain types of documents  or ranges of document numbers. For example, you can create picks only for sales orders.  
  
4.  Choose the **OK** button. The inventory picks will be created, and if you selected the **Print Document** field, the pick list will be printed.  
  
> [!NOTE]  
>  In basic warehouse configurations, assembly components are picked with inventory movements. For more information see [How to: Move Components to an Operation Area in Basic Warehouse Configurations](../how-to-move-components-to-an-operation-area-in-basic-warehousing.md).  
>   
>  In basic warehouse configurations, items that are assembled to sales orders are picked from the related sales order, as explained in this topic. For more information, see “Handling Assemble-to-Order Items in Inventory Picks” in Inventory Pick.  
  
## See Also  
 Inventory Pick   
 [Pick Items](../pick-items.md)   
 [How to: Pick Items with Inventory Picks](../how-to-pick-items-with-inventory-picks.md)   
 [How to: Pick Items for Warehouse Shipment](../how-to-pick-items-for-warehouse-shipment.md)   
 [Design Details: Warehouse Management](../../design-details-warehouse-management.md)