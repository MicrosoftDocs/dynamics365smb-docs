---
title: Quote an Assemble-to-Order Sale
description: You can use assembly management to customize an assembly item to a customer's request during the sales process.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: kit, kitting
ms.search.form: 900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Quote an Assemble-to-Order Sale

You can use assembly management to customize an assembly item to a customer's request during the sales process. For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).  

As when you sell any other type of item, you can also create a sales quote for a customized assembly item before converting it to a sales order. This process involves several extra steps when you compare it to creating a regular sales quote, and it uses a variation of a linked assembly order, which is an assembly quote.

> [!NOTE]  
>  Like all types of quotes, the quantities on assembly quotes are not used in availability, planning, or reservations.  

## To create a sales quote for an assemble-to-order item

1.  [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Quote**, and then choose the related link.  
2.  Create a sales quote line with one line for an assembly item. For more information, see [Make Sales Quotes](sales-how-make-offers.md).  
3.  In the **Qty. to Assemble to Order** field, enter the full quantity.

    > [!NOTE]  
    >  You should not quote a partial quantity. Therefore, you must enter the same quantity that you entered in the **Quantity** field on the sales quote line.  

4.  On the **Lines** FastTab, choose **Line**, choose **Assemble to Order**, and then choose **Assemble-to-Order Lines**. Alternatively, choose the **Qty. to Assemble to Order** field on the line.  
5.  On the **Assemble-to-Order Lines** page, review or modify the assembly order lines according to the quote that the customer is requesting. If you want to view more information, choose the **Show Document** action to open the complete blanket quote order. You cannot change the contents of most fields, and you cannot post.  
6.  When you have adjusted the assembly order lines according to the quote, close the **Assemble-to-Order Lines** page to return to the **Sales Quote** page.  
7.  If the customer accepts the quote, then create a sales order for the quoted assembly item. For more information, see [Make Sales Quotes](sales-how-make-offers.md). The linked assembly quote and any customizations are linked to that new sales order to prepare for assembly of the item or items to be sold.  

## Related information

[Assembly Management](assembly-assemble-items.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Inventory](inventory-manage-inventory.md)  
[Warehouse Management Overview](design-details-warehouse-management.md)
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
