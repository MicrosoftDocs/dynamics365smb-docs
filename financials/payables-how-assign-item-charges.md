---
title: 'How to: Use Item Charges to Account for Additional Trade Costs| Microsoft Docs'
description: 'If you want your inventory items to carry added costs, such as freight, physical handling, insurance, and transportation that you incur when purchasing or selling items, you can use the Item Charges feature.'
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: transportation, added cost
ms.date: 04/23/2017
ms.author: sgroespe

---
# How to: Use Item Charges to Account for Additional Trade Costs
Your inventory items should carry added costs, such as freight, physical handling, insurance, and transportation that you incur when purchasing or selling the items. for purchases, the landed cost of a purchased item consists of the vendor's purchase price and all additional direct item charges that can be assigned to individual receipts or return shipments. For sales, knowing the cost of shipping sold items can be as vital to your company as knowing the landed cost of purchased items.

In addition to recording the added cost in you inventory value, you can use the Item Charges feature for the following:

- Identifying the landed cost of an item for making more accurate decisions on how to optimize the distribution network.
- Breaking down the unit cost / unit price of an item for analysis purposes.
- including purchase allowances into the unit cost and sales allowances into the unit price.

Before you can assign item charges, you must set up item charge numbers for the different types of item charges and then determine to which accounts costs related to sales, purchases, and inventory adjustments they will be posted. An item charge number contains a combination of general product posting group, tax group code, VAT product posting group, and item charge. When you enter the item charge number on a purchase or sales document, the relevant G/L account is retrieved based on the setup of the item charge number and the information on the document.

For both purchase and sales documents, you can assign an item charge in two ways:
- On the document where the items that the item charge relates to are listed. This you typically do for documents that are not yet fully posted.
- On a separate invoice where you link the item charge to a posted receipt or shipment where the items that the item charge relate to are listed.

**Note**: You can assign item charges to quotes, orders, invoices, and credit memos, for both sales and purchases. The following procedures describe how to work with item charges for a purchase invoice.

## To set up item charge numbers
You use item charge numbers to distinguish between the different kinds of item charges that are used in your company.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Item Charges**, and then choose the related link.
2. In the **Item Charges** window, choose the **New** action to create a new line.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## To assign an item charge to the original purchase invoice
If you receive the purchased items and the invoice for the item charge at the same time, or if the original purchase document has not been posted in full yet, then follow this procedure.

1. In the top right corner, choose the **Search for Page or Report** icon, enter **Purchase Invoices**, and then choose the related link.
2. Create a new purchase invoice. For more information, see [How to: Record Purchases](purchasing-how-record-purchases.md).
3. In the **Type** field, select **Charge (Item)**.
4. In the **No.** field, select the relevant item charge number.
5. On the **Lines** tab, choose the **Item Charge Assignment** action.
6. **wait for UI**  





## See Also
[Managing Payables](payables-manage-payables.md)  
[How to: Record Purchases](purchasing-how-record-purchases.md)  
[How to: Invoice Sales](sales-how-invoice-sales.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
