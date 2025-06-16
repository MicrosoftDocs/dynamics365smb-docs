---
title: Record purchases with purchase invoices
description: Describes how to purchase inventory, noninventory items, or resources by creating and posting purchase invoices or orders.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: procurement
ms.search.form: 50 ,51, 53, 56, 146, 147, 9307, 9309, 9306, 9308, 9310
ms.date: 05/19/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Record purchases with purchase invoices and orders

You create a purchase invoice or purchase order to record the cost of purchases and to track accounts payable. Purchase invoices and purchase orders are also used to dynamically update inventory levels, meaning you can minimize inventory costs and provide better customer service. The purchasing costs, including service expenses, and inventory values that result from posting purchase invoices or orders contribute to profit figures and financial key performance indicators (KPIs).

## Record purchases with purchase invoices

When you receive the inventory items or the purchased service is complete, post the purchase invoice to update inventory and financial records and to activate payment to the vendor according to the payment terms. [Making Payments](payables-make-payments.md).

> [!CAUTION]  
> Don't post a purchase invoice for physical items until you receive the items and know the final cost of the purchase, including any extra charges. Otherwise, your inventory value and profit figures might be skewed.

### Create and post a purchase invoice

The following steps describe how to create a purchase invoice. The steps for creating a purchase order are similar. The main difference is that purchase orders have some extra fields and actions for physical handling of items.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**,  then choose the related link.  
2. In the **Vendor Name** field, enter the name of an existing vendor.

    Other fields on the **Purchase Invoice** page are now filled with standard information for the selected vendor. If the vendor isn't registered, follow these steps:

    1. In the **Vendor Name** field, enter the name of the new vendor.
    2. In the dialog box about registering the new vendor, choose **Yes**.
    3. To learn more on how to fill in the vendor card, go to [Register New Vendors](purchasing-how-register-new-vendors.md).  
    4. When you complete the vendor card, choose **OK** to return to the **Purchase Invoice** page.

3. Fill in the remaining fields on the **Purchase Invoice** page as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    You're now ready to fill in the purchase invoice lines with items or resources purchased from the vendor.

    > [!NOTE]  
    > If you set up recurring purchase lines for the vendor, such as a monthly replenishment order, you can add these lines on the invoice by choosing the **Get Recurring Purchase Lines** action.
4. On the **Lines** FastTab, in the **Item No.** field, enter the number of an inventory item or a service.
5. In the **Quantity** field, enter the number of items to purchase.

    The **Line Amount** field is updated to show the value in the **Direct Unit Cost** field multiplied by the value in the **Quantity** field.

    The price and line amount are shown with or without sales tax depending on what you select in the **Prices Including Tax** field on the vendor card.

    The totals fields under the lines are automatically updated as you create or modify lines to display the amounts posted to the ledgers.

6. In the **Inv. Discount Amount** field, enter an amount that should be deducted from the value shown in the **Total Incl. Tax** field at the bottom of the invoice.

    > [!NOTE]  
    > If you set up invoice discounts for the vendor, the percentage value is automatically inserted in the **Vendor Invoice Discount %** field if the criteria are met. The related amount is inserted in the **Inv. Discount Amount** field.
7. When you receive the purchased items or services, choose **Post**.

The purchase is now reflected in inventory, resource ledgers, and financial records, and the vendor payment is activated. The purchase invoice is removed from the list of purchase invoices and replaced with a new document in the list of posted purchase invoices. For more information on what happens when you post purchase documents, see [Posting Purchases](purchasing-how-record-purchases.md#posting-purchases).

> [!NOTE]
> In rare cases, the posted amounts might differ from what is displayed in the totals fields. Typically, the difference is due to rounding calculations for value-added tax (VAT) or sales tax.
>
> To check the amounts before you post, go to the **Statistics** page, which takes the rounding calculations into account. Also, if you choose the **Release** action, the totals fields update to include rounding calculations.

## Posted invoices

[!INCLUDE [posted-invoices](includes/posted-invoices.md)]

You can easily correct or cancel a posted purchase invoice before you pay the vendor. For example, if you need to correct a typo or change the purchase early in the order process. Learn more at [Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md). To reverse a purchase for items or services on a posted purchase invoice for which the payment is processed, create a purchase credit memo. Learn more at [Process Purchase Returns or Cancellations](purchasing-how-process-purchase-returns-cancellations.md).

[Open the **Posted Purchase Invoices** list](https://businesscentral.dynamics.com/?page=146) in [!INCLUDE [prod_short](includes/prod_short.md)].

## Purchasing noninventory items

The lines on a purchase invoice can be of the **Resource** or **Item** type. Item cards can be further classified as of the **Inventory**, **Service**, or **Non-Inventory** type, which specifies if the item is a physical inventory unit, a labor time unit (also applicable for resources), or a physical unit that isn't kept in inventory. Learn more at [Register New Items](inventory-how-register-new-items.md). The purchase invoice process is the same for all mentioned types.

> [!NOTE]
> With the **Resource** purchase line type, you can also purchase external resources, for example, to invoice a vendor for work delivered. Learn more at [Set Up Resources](projects-how-setup-resources.md).
>
> To use a purchased resource, you might need to set the resource's capacity, and manually assign it to a project. Purchasing a resource creates a resource ledger entry; however, resource ledger entries aren't tracked for quantity and value as, for example, items are. If quantity and value tracking is required, then consider using other line item types.

## When to use purchase orders

Use purchase orders if you need to record partial receipts of an order quantity. For example, because the full quantity isn't available at the vendor. If you deliver sold items directly from your vendor to your customer as a drop shipment, you must also use purchase orders. Learn more at [Make Drop Shipments](sales-how-drop-shipment.md).

In all other aspects, purchase orders work the same as purchase invoices. The following procedure is based on a purchase invoice. The steps are similar for a purchase order.

<br><br>

> [!Video https://learn-video.azurefd.net/vod/player?id=f04b1ed3-5cb0-4fa8-8cd0-24069ee893d2]

## Receive items with a purchase order

The following steps describe how to receive items with a purchase order. 

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, then choose the related link.
2. Open an existing purchase order, or create a new one.
3. In the **Qty. to Receive** field, enter the received quantity.

   > [!NOTE]
   > If the received quantity is more than the quantity on the purchase order, and the vendor is set up to allow over-receipts, use the **Over-Receive** field to handle the excess quantity. Learn more in the [To receive more items than you ordered](purchasing-how-record-purchases.md#receive-more-items-than-you-ordered) section.
4. Choose the **Post** action.

  The value in the **Qty. Received** field is updated. If this receipt is partial, the value is lower than the value in the **Quantity** field.

> [!NOTE]
> If you use warehouse handling, you can't use the **Post** action on the purchase order to register the receipt. A warehouse employee already posted the purchase order quantity as received. Learn more at [Design Details - Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md).

## Receive more items than you ordered

When more goods arrive than were ordered, you might want to receive them instead of canceling the receipt. For example, it might be cheaper to keep the excess items in inventory than return them, or your vendor might offer a discount for keeping them.

The following video shows how to work with over-receipts.

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=61ce06f8-b3e7-42fd-b332-85f09d65a4e1]

<!--move the over-receipt setup info to an article about purchasing. Keep the concept info here and link to the steps-->
### Set up over-receipts

Create over-receipt codes to define a percentage by which a received quantity can exceed the ordered quantity. Specify the percentage in the **Over-Receipt Tolerance %** field. You then assign the code on the Item Card or Vendor Card pages for items and vendors.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Over-Receipt Codes**, then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

### Assign the over-receipt code to an item

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, then choose the related link.
2. Open the **Item Card** page for the item.
3. In the **Over-Receipt Code** field, choose the code that contains the percentage you want to allow for over-receipts.

The over-receipt code is assigned to the item. Purchase orders or warehouse receipts for the item now allow you to receive more than the ordered quantity within the over-receipt tolerance percentage.

> [!NOTE]
> You can set up an approval workflow requiring over-receipts to be approved before they can be handled. Select the **Approval Required** checkbox on the **Over-Receipt Codes** page. Learn more at [Create Workflows](across-how-to-create-workflows.md).

### Over-receive an order

On purchase lines and warehouse receipt lines, the **Over-Receipt Quantity** field is used to record over-received quantities, meaning quantities exceeding the ordered-quantity value in the **Quantity** field.

When you handle an over-receipt, you can increase the value in the **Qty. to Receive** field to the quantity received. The **Over-Receipt Quantity** field updates to show the excess quantity. Alternatively, you can enter the excess quantity in the **Over-Receipt Quantity** field. The **Qty. to Receive** field updates to show the ordered quantity plus the excess quantity. The following procedure described how to fill in the **Qty. to Receive** field.  

1. On a purchase order or a warehouse receipt document where the received quantity is higher than ordered, enter the quantity received in the **Qty. to Receive** field.

    If the increase is within the tolerance specified by an assigned over-receipt code, the **Over-Receipt Quantity** field updates to show the quantity by which the value in the **Quantity** field is exceeded.

    If the increase is over the tolerance, the over-receipt isn't allowed. Investigate whether another over-receipt code allows it. Otherwise, only the ordered quantity can be received, and the excess quantity must be handled another way, such as returning it to the vendor.

2. Post the receipt as you would any other receipt.

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)] doesn't automatically handle financial aspects of over-receipts. You must manually handle over-receipts in agreement with the vendor, for example, by the vendor forwarding a new or updated invoice.

## External document number

[!INCLUDE [ext-doc-no-purch](includes/ext-doc-no-purch.md)]

## Posting purchases

On a purchase document, you can choose between the following posting actions:

* **Post**
* **Preview Posting**
* **Post and Print**
<!--* **Test Report**-->
* **Post Batch**

When a purchase document is posted, the vendor's account, the general ledger (G/L), the item ledger entries, and the resource ledger entries are updated.

For each purchase document, a purchase entry is created in the **G/L Entry** table. An entry is also created in the vendor's account in the **Vendor Ledger Entry** table and a G/L entry is created in the relevant payables account. In addition, posting the purchase can result in a value-added tax (VAT) entry and a G/L entry for the discount amount. Whether an entry for the discount is posted depends on the contents of the **Discount Posting** field on the **Purchases & Payables Setup** page.

For each purchase line, as applicable, entries are created in the:

* **Item Ledger Entry** table if the purchase line is of the **Item** type.
* **G/L Entry** table if the purchase line is of the **G/L Account** type.
* **Resource Ledger Entry** table if the purchase line is of the **Resource** type.

In addition, purchase documents are always recorded in the **Purch. Recpt. Header** and **Purch. Inv. Header** tables.

You can always review various ledger entries that are created as a result of postings. Choose **Preview Posting** to validate document and inspect expected ledger entries.

> [!IMPORTANT]  
> When you post a purchase order for items, you can create both a receipt and an invoice simultaneously or independently. You can also create a partial receipt and a partial invoice by completing the **Qty. to Receive** and **Qty. to Invoice** fields on the individual purchase order lines before you post. You can't create a purchase invoice from a purchase order for products or services that aren't received. That is, before you can invoice, you must record a receipt, or you must choose to receive and invoice at the same time.

You can either post or post and print. If you choose to post and print, a report is printed when the order is posted. You can also choose the **Post Batch** action to post several orders at the same time. Learn more at [Post Multiple Documents at the Same Time](ui-batch-posting.md).

## Viewing ledger entries

When the posting is completed, the posted purchase lines are removed from the order. A message tells you when the posting is completed. Afterward, the posted entries are available on various pages, including the **Vendor Ledger Entries**, **G/L Entries**, **Item Ledger Entries**, **Resource Ledger Entries**, **Purchase Receipts**, and **Posted Purchase Invoices** pages.

In most cases, you can open ledger entries from the affected card or document. For example, on the **Vendor Card** page, choose the **Entries** action.

## Editing ledger entries

You can edit certain fields on posted purchase documents, such as the **Payment Reference** field. Learn more at [Edit Posted Documents](across-edit-posted-document.md). For more critical fields that affect the auditing trail, you must reverse or undo posting. Learn more at [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).

## Related information

[Request Quotes](purchasing-how-request-quotes.md)  
[Purchase Items for a Sale](purchasing-how-purchase-products-sale.md)  
[Prepare Drop Shipments](sales-how-drop-shipment.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Setting Up Purchasing](purchasing-setup-purchasing.md)  
[Set Up Resources](projects-how-setup-resources.md)  
[Register New Vendors](purchasing-how-register-new-vendors.md)  
[Edit Posted Documents](across-edit-posted-document.md)  
[Post Multiple Documents at the Same Time](ui-batch-posting.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Posting Documents and Journals](ui-post-documents-journals.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
