---
    title: How to: Receive Items | Microsoft Docs
    description: When items arrive at a warehouse that is set up for warehouse receipt processing, you must retrieve the lines of the released source document that triggered their receipt. If you have bins, you can either accept the default bin that is filled in, or if the item has never been used before in the warehouse, fill in the bin where the item should be put away. You must then fill in the quantities of the items you have received, and post the receipt. A source document for a receipt can be a purchase order, a sales return order, or an inbound transfer order.
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
# How to: Receive Items
When items arrive at a warehouse that is set up for warehouse receipt processing, you must retrieve the lines of the released source document that triggered their receipt. If you have bins, you can either accept the default bin that is filled in, or if the item has never been used before in the warehouse, fill in the bin where the item should be put away. You must then fill in the quantities of the items you have received, and post the receipt. A source document for a receipt can be a purchase order, a sales return order, or an inbound transfer order.  
  
### To receive items  
  
1.  In the **Search** box, enter **Warehouse Receipts**, and then choose the related link.  
  
2.  On the **Home** tab, in the **New** group, choose **New**.  
  
     Fill in the fields on **General** FastTab. When you retrieve source document lines, some of the information is copied to each line.  
  
     For directed put-away and pick, if the location has a default zone and bin for receipts, the **Zone Code** and **Bin Code** fields are filled in automatically, but you can change them as appropriate.  
  
    > [!NOTE]  
    >  If you wish to receive items with warehouse class codes other than the class code of the bin in the **Bin Code** field on the document header, you must delete the contents of the **Bin Code** field on the header before you retrieve source document lines for the items.  
  
3.  On the **Actions** tab, in the **Functions** group, choose **Get Source Documents**. The **Source Documents** window opens. You can also use filters to get source documents to narrow the results to a more specific set of source documents. For more information, see [How to: Use Filters to Get Source Documents](../how-to-use-filters-to-get-source-documents.md).  
  
4.  Select the source documents for which you want to receive items and choose the **OK** button.  
  
     The lines of the source documents appear in the **Warehouse Receipt** window. The **Qty. to Receive** field is filled with the quantity outstanding for each line, but you can change the quantity as necessary. If you deleted the contents of the **Bin Code** field on the **General** FastTab before getting the lines, you must fill in an appropriate bin code on each receipt line.  
  
    > [!NOTE]  
    >  To fill in the **Qty. to Receive** field on all the lines with zero, on the **Actions** tab, in the **Functions** group, choose **Delete Qty. to Receive**. To fill it in once again with the quantity outstanding, choose **Autofill Qty. to Receive**.  
  
    > [!NOTE]  
    >  You cannot receive more items than the number in the **Qty. Outstanding** field on the source document line. To receive more items, retrieve another source document that contains a line for the item by using the filter function to get source documents with the item.  
  
5.  Post the warehouse receipt. The quantity fields are updated on the source documents, and the items are recorded as part of company inventory.  
  
 If you are using warehouse put-away, the receipt lines are sent to the warehouse put-away function. The items, although received, cannot be picked until they have been put away. The received items are identified as available inventory only when the put-away has been registered.  
  
 If you are not using warehouse put-away but you are using bins, the put-away of the items in the bin specified on the source document line is recorded.  
  
> [!NOTE]  
>  If you use the **Post and Print** function, you both post the receipt and print a put-away instruction that shows you where to place the items in storage.  
>   
>  If your location uses directed put-away and pick, then the put-away templates are used to calculate the best place to put the items away. This is then printed on the put-away instruction.  
  
## See Also  
 [Receiving](../receiving.md)   
 [Design Details: Warehouse Management](design-details-warehouse-management.md)   
 [How to: Put Items Away with Warehouse Put-aways](../how-to-put-items-away-with-warehouse-put-aways.md)   
 [How to: Cross-Dock Items](../how-to-cross-dock-items.md)   
 [How to: Use Filters to Get Source Documents](../how-to-use-filters-to-get-source-documents.md)