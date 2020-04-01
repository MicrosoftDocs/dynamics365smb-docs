---
    title: How to Quote an Assemble-to-Order Sale | Microsoft Docs
    description: You can use assembly management to customize an assembly item to a customer’s request during the sales process.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: kit, kitting
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Quote an Assemble-to-Order Sale
You can use assembly management to customize an assembly item to a customer’s request during the sales process. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  

As when you sell any other type of item, you can also create a sales quote for a customized assembly item before converting it to a sales order. This process involves several extra steps when you compare it to creating a regular sales quote, and it uses a variation of a linked assembly order, which is an assembly quote.

> [!NOTE]  
>  Like all types of quotes, the quantities on assembly quotes are not used in availability, planning, or reservations.  

## To create a sales quote for an assemble-to-order item  
1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Quote**, and then choose the related link.  
2.  Create a sales quote line with one line for an assembly item. For more information, see [Make Sales Quotes](sales-how-make-offers.md).  
3.  In the **Qty. to Assemble to Order** field, enter the full quantity.

    > [!NOTE]  
    >  You should not quote a partial quantity. Therefore, you must enter the same quantity that you entered in the **Quantity** field on the sales quote line.  

4.  On the **Lines** FastTab, choose **Line**, choose **Assemble to Order**, and then choose **Assemble-to-Order Lines**. Alternatively, choose the **Qty. to Assemble to Order** field on the line.  
5.  On the **Assemble-to-Order Lines** page, review or modify the assembly order lines according to the quote that the customer is requesting. If you want to view more information, choose the **Show Document** action to open the complete blanket quote order. You cannot change the contents of most fields, and you cannot post.  
6.  When you have adjusted the assembly order lines according to the quote, close the **Assemble-to-Order Lines** page to return to the **Sales Quote** page.  
7.  If the customer accepts the quote, then create a sales order for the quoted assembly item. For more information, see [Make Sales Quotes](sales-how-make-offers.md). The linked assembly quote and any customizations are linked to that new sales order to prepare for assembly of the item or items to be sold.  

## See Also  
[Assembly Management](assembly-assemble-items.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  
[Inventory](inventory-manage-inventory.md)  
[Design Details: Warehouse Management](design-details-warehouse-management.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
