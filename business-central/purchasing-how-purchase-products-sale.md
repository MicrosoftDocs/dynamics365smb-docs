---
title: Purchase Items for a Sale by Creating Purchase Invoices | Microsoft Docs
description: From a sales invoice, to purchase products, you can create a purchase invoice for a vendor or supplier.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: supply planning, sales demand, replenish
ms.date: 04/01/2020
ms.author: sgroespe

---
# Purchase Items for a Sale
From sales orders and sales invoices, you can use functions to quickly create purchase documents for missing item quantities that are required by the sale. You can use two different functions depending on the document type.

> [!Note]
> This functionality is for replenishing sales items into your own inventory. To purchase items for direct delivery from your vendor to your customer, you must create a drop shipment. For more information, see [Make Drop Shipments](sales-how-drop-shipment.md).   

|Function|Description|
|--------|-----------|
|**Create Purchase Orders**|From a sales order, this function creates a purchase order for each vendor of items on the sales order. You can edit the purchase quantity before you create the purchase orders. Only unavailable sales quantities are suggested.
|**Create Purchase Invoice**|From a sales order and from a sales invoice, this function creates a purchase invoice for a selected vendor for all lines or selected lines on the sales document. The full sales quantity is suggested.|

## To create one or more purchase orders from a sales order
To create a purchase order for each unavailable item quantity on the sales order, you use the **Create Purchase Orders** function.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Open a sales order that you want to purchase items for.
3. Choose the **Create Purchase Orders** action.

    The **Create Purchase Orders** page opens showing a line for each different item on the sales order. Lines for both fully available sales quantities and unavailable sales quantities (grayed) are shown by default. You can choose the **Show Unavailable** action to only see lines for unavailable sales quantities.

    The **Quantity to Purchase** field contains the unavailable sales quantity by default.
4. To purchase another quantity than the unavailable sales quantity, edit the value in the **Quantity to Purchase** field.

    > [!NOTE]  
    >   You can also change the **Quantity to Purchase** field on grayed lines even though they represent fully available sales quantities.
5. Choose the **OK** button.

    A purchase order is created for each vendor of items on the sales order, including any quantity changes that you made on the **Create Purchase Orders** page.
7. Proceed to process the purchase order or orders, for example, by editing or adding purchase order lines. For more information, see [Record Purchases](purchasing-how-record-purchases.md).


## To create a purchase invoice from a sales order or sales invoice
To create a single purchase invoice for one or more lines on a sales document by first selecting which vendor to buy from, you use the **Create Purchase Invoice** function.

> [!NOTE]  
>   This function creates a purchase invoice for the exact item quantity on the selected sales document. To change the purchase quantity, you must edit the purchase invoice after it is created.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.
2. Open a sales invoice that you want to purchase items for.
3. Select one or more sales invoice lines that you want to use on the purchase invoice. To use all the sales invoice lines, select either all of them or do not select any lines.
4. Choose the **Create Purchase Invoice** action.
5. Select either **All Lines** or **Selected Lines**, and then choose the **OK** button.  
6. In the list of vendors that appears, select the vendor that you want to buy all the items from, and then choose the **OK** button.

    A purchase invoice is created that contains one, more than one, or all the lines on the sales invoice.
7. Proceed to process the purchase invoice, for example, by editing or adding purchase invoice lines. For more information, see [Record Purchases](purchasing-how-record-purchases.md).

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[Record Purchases](purchasing-how-record-purchases.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Register New Vendors](purchasing-how-register-new-vendors.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
