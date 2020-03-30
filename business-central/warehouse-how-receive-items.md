---
    title: How to Receive Items | Microsoft Docs
    description: When items arrive at a warehouse that is set up for warehouse receipt processing, you must retrieve the lines of the released source document that triggered their receipt.
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
# Receive Items
When items arrive at a warehouse that is not set up for warehouse receipt processing, you simply record the receipt on the related business document, such as a purchase order, a sales return order, or an inbound transfer order.

When items arrive at a warehouse that is set up for warehouse receipt processing, you must retrieve the lines of the released source document that triggered their receipt. If you have bins, you can either accept the default bin that is filled in, or if the item has never been used before in the warehouse, fill in the bin where the item should be put away. You must then fill in the quantities of the items you have received, and post the receipt.  

## To receive items with a purchase order
The following describes how to receive items with a purchase order. The steps are similar for sales return orders and transfer orders.  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Open an existing purchase order, or create a new one. For more information, see [Record Purchases](purchasing-how-record-purchases.md).
3. In the **Qty. to Receive** field, enter the received quantity.

  > [!NOTE]
  > If the received quantity is higher than ordered on the purchase order, per the **Quantity** field, and the vendor has been set up to allow over-receipts, then you use the **Over-Receive** field top handle the excess quantity. For more information, see [To receive more items than ordered](warehouse-how-receive-items.md#to-receive-more-items-than-ordered).
4. Choose the **Post** action.

  The value in the **Qty. Received** field is updated. If this is a partial receipt, then the value is lower than the value in the **Quantity** field.

> [!NOTE]
> If you use a warehouse document to post the receipt, then you cannot use the **Post** action on the purchase order. Instead, a warehouse worker has already posted the purchase order quantity as received. For more information, see [To receive items with a warehouse receipt](warehouse-how-receive-items.md#to-receive-items-with-a-warehouse-receipt).

## To receive items with a warehouse receipt
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Receipts**, and then choose the related link.  
2.  Choose the **New** action.  

    Fill in the fields on **General** FastTab. When you retrieve source document lines, some of the information is copied to each line.  

    For warehouse configuration with directed put-away and pick, if the location has a default zone and bin for receipts, the **Zone Code** and **Bin Code** fields are filled in automatically, but you can change them as appropriate.  

    > [!NOTE]  
    > If you wish to receive items with warehouse class codes other than the class code of the bin in the **Bin Code** field on the document header, you must delete the contents of the **Bin Code** field on the header before you retrieve source document lines for the items.  
3.  Choose the **Get Source Documents** action. The **Source Documents** page opens.

    From a new or an open warehouse receipt, you can use the **Filters to Get Source Docs.** page to retrieve the released source document lines that define which items to receive or ship.

    1. Choose the **Use Filters to Get Src. Docs.** action.  
    2. To set up a new filter, enter a descriptive code in the **Code** field, and then choose the **Modify** action.  
    3. Define the type of source document lines that you want to retrieve by filling in the relevant filter fields.  
    4. Choose the **Run** action.  

    All released source document lines that fulfill the filter criteria are now inserted in **Warehouse Receipt** page from which you activated the filter function.  

    The filter combinations that you define are saved on the **Filters to Get Source Docs.** page until the next time you need it. You can make an unlimited number of filter combinations. You can change the criteria at any time by choosing the **Modify** action.

4.  Select the source documents for which you want to receive items, and then choose the **OK** button.  

    The lines of the source documents appear on the **Warehouse Receipt** page. The **Qty. to Receive** field is filled with the quantity outstanding for each line, but you can change the quantity as necessary. If you deleted the contents of the **Bin Code** field on the **General** FastTab before getting the lines, you must fill in an appropriate bin code on each receipt line.  

    > [!NOTE]  
    >  To fill in the **Qty. to Receive** field on all the lines with zero, choose the **Delete Qty. to Receive** action. To fill it in once again with the quantity outstanding, choose the **Autofill Qty. to Receive** action.  

    > [!NOTE]  
    >  You cannot receive more items than the number in the **Qty. Outstanding** field on the source document line. To receive more items, retrieve another source document that contains a line for the item by using the filter function to get source documents with the item.  

5.  Post the warehouse receipt. The quantity fields are updated on the source documents, and the items are recorded as part of company inventory.  

If you are using warehouse put-away, the receipt lines are sent to the warehouse put-away function. The items, although received, cannot be picked until they have been put away. The received items are identified as available inventory only when the put-away has been registered.  

If you are not using warehouse put-away but you are using bins, the put-away of the items in the bin specified on the source document line is recorded.  

> [!NOTE]  
>  If you use the **Post and Print** function, you both post the receipt and print a put-away instruction that shows you where to place the items in storage.  
>   
>  If your location uses directed put-away and pick, then the put-away templates are used to calculate the best place to put the items away. This is then printed on the put-away instruction.

## To receive more items than ordered
When you receive more goods than you ordered, you may want to receive them instead of canceling the receipt. For example, it may be cheaper to keep the excess on your inventory than returning them or your vendor may offer you a discount for keeping them.

### To set up over-receipts
You must define a percentage by which you allow the ordered quantity to be exceeded when receiving. You define this under an over-receipt code, which contains the percentage in the **Over-Receipt Tolerance %** field. You then assign the code to the cards of relevant items and/or vendors.  

The following describes how to set up and assign an over-receipt code to an item. The steps are similar for a vendor.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
2. Open the card for an item that you suspect may sometimes be delivered with a higher quantity than ordered.
2. Choose the look-up button in the **Over-Receipt Code** field.
3. Choose the **New** action.
4. On the **Over-Receipt Codes** page, create one or more new lines that define different over-receive policies. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].
5. Select a line, and then choose the **OK** button.

The over-receipt code is assigned to the item. Any purchase order or warehouse receipt for the item now allows receiving more than the ordered quantity according to the specified over-receipt tolerance percentage.

> [!NOTE]
> You can set up an approval workflow to require that over-receipts must be approved before they can be handled. In that case, you must select the **Approval Required** check box on the **Over-Receipt Codes** page. A dedicated workflow response, **Approve Over-Receipt** exists in the standard workflow data for this purpose. For more information, see [Create Workflows](across-how-to-create-workflows.md).

### To perform an over-receipt
On purchase lines and warehouse receipt lines, the **Over-Receipt Quantity** field is used to record over-received quantities, meaning quantities that exceed the value in the **Quantity** field, the ordered quantity.

When you handle an over-receipt, you can either increase the value in the **Qty. to Receive** field to the actually received quantity. The **Over-Receipt Quantity** field is then updated to show the excess quantity. Alternatively, you can enter the excess quantity in the **Over-Receipt Quantity** field. The **Qty. to Receive** field is then updated to show the ordered quantity plus the excess quantity. The following procedure described how to fill in the **Qty. to Receive** field.  

1. On a purchase order or a warehouse receipt document where the received quantity is higher than ordered, enter the actually received quantity in the **Qty. to Receive** field.

    If the increase is within the tolerance specified by the assigned over-receipt code, the **Over-Receipt Quantity** field is updated to show the quantity by which the value in the **Quantity** field is exceeded.

    If the increase is above the specified tolerance, the over-receipt is not allowed. In that case, you can investigate if another over-receipt code exists that will allow it. Otherwise, only the ordered quantity can be received, and the excess quantity must be handled otherwise, for example, by returning it to the vendor.

2. Post the receipt as you would for any other receipt.

> [!NOTE]
> [!INCLUDE[d365fin](includes/d365fin_md.md)] does not include functionality to automatically initiate the financial administration of over-receipts. You must manually handle this in agreement with the vendor, for example, by the vendor forwarding a new or updated invoice.

## See Related Training at [Microsoft Learn](/learn/modules/receive-invoice-dynamics-d365-business-central/index)

## See Also  
[Warehouse Management](warehouse-manage-warehouse.md)  
[Inventory](inventory-manage-inventory.md)  
[Setting Up Warehouse Management](warehouse-setup-warehouse.md)     
[Assembly Management](assembly-assemble-items.md)    
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
