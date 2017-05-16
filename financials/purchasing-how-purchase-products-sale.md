---
title: 'How to: Purchase Products for a Sale| Microsoft Docs'
description: 'To replenish items as soon as you sell them, or to fullfill an open sales demand, you can use the Create Purchase Orders function as a simple supply planning feature.'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: supply planning, sales demand, replenish
ms.date: 05/16/2017
ms.author: sgroespe

---
# How to: Purchase Products for a Sale
From sales orders and sales invoices, you can use functions to quickly create purchase documents for missing item quantities that are required by the sale. You can use two different functions depending on the document type.
|Function|Description|
|--------|-----------|
|**Create Purchase Orders**|From a sales order, this function creates a purchase order for each different item on the sales order lines, addressed to the items' assigned vendors. You can edit the purchase quantity before you create the purchase orders. Only unavailable sales quantities are suggested.
|**Create Purchase Invoice**|From a sales order and from a sales invoice, this function creates a purchase invoice for a selected vendor for all lines or selected lines on the sales document. The full sales quantity is suggested.|

**Note**: This functionality requires that your experience is set to **Suite**. For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).

## To create one or more purchase orders from a sales order
To create a purchase order for each unavailable item quantity on the sales order, you use the **Create Purchase Orders** function. 

**Note**. This function creates a purchase order for each assigned vendor of each different item on the sales order lines. If an item does not have a vendor assigned, you must select one before you create the purchase order.

1. On the Home page, choose the **Ongoing Sales Orders** tile.
2. Open a sales order that you want to purchase items for.
3. Choose the **Create Purchase Orders** action.

    The **Create Purchase Orders** window opens showing a line for each different item on the sales order. Lines for both fully available sales quantities and unavailable sales quantities (grayed) are shown by default. You can choose the **Show Unavailable** action to only see lines for unavailable sales quantities.

    The **Quantity to Purchase** field contains the unavailable sales quantity by default.
4. To purchase another quantity than the unavailable sales quantity, edit the value in the **Quantity to Purchase** field.

    **Note**: You can also change the **Quantity to Purchase** field on grayed lines even though they represent fully available sales quantities.
5. Choose the **OK** button. 
    
    A purchase order is created for each different item on the sales order, including any quantity changes that you made in the **Create Purchase Orders** window.
7. Proceed to process the purchase order or orders, for example, by editing or adding purchase order lines. For more information, see [How to: Record Purchases](purchasing-how-record-purchases.md).


## To create a purchase invoice from a sales order or sales invoice
To create a single purchase invoice for one or more lines on a sales document by first selecting which vendor to buy from, you use the **Create Purchase Invoice** function. 

**Note**: This function creates a purchase invoice for the exact item quantity on the selected sales document. To change the purchase quantity, you must edit the purchase invoice after it is created.  

1. On the Home page, choose the **Ongoing Sales Invoices** tile.
2. Open a sales invoice that you want to purchase items for.
3. Select one or more sales invoice lines that you want to use on the purchase invoice. To use all the sales invoice lines, select either all of them or do not select any lines.
4. Choose the **Create Purchase Invoice** action.
5. Select either **All Lines** or **Selected Lines**, and then choose the **OK** button.  
6. In the list of vendors that appears, select the vendor that you want to buy all the items from, and then choose the **OK** button.

    A purchase invoice is created that contains one, more, or all the lines on the sales invoice.
7. Proceed to process the purchase invoice, for example, by editing or adding purchase invoice lines. For more information, see [How to: Record Purchases](purchasing-how-record-purchases.md).

## See Also
[Purchasing](purchasing-manage-purchasing.md)  
[How to: Record Purchases](purchasing-how-record-purchases.md)  
[How to: Invoice Sales](sales-how-invoice-sales.md)  
[How to: Register New Vendors](purchasing-how-register-new-vendors.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
