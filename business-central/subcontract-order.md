---
title: Order subcontracting
description: Learn how to create subcontracting purchase orders from production orders or by using the subcontracting worksheet, and how to print dispatch lists.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, production order, purchase order, dispatch list, worksheet
ms.search.form: 99001504, 99000886, 50, 99000831
ms.date: 09/04/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Order subcontracting

You can create subcontracting purchase orders in two ways:

- **Directly from a production order routing**, when you want to order a specific operation right away.
- **Using the subcontracting worksheet**, when you want to review and batch-create purchase orders for multiple production orders at once.

Both approaches produce the same result: a purchase order linked to the production order routing.

## Create a subcontracting purchase order from a production order

The following steps describe how to create a subcontracting purchase order from a released production order.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then choose the related link.
2. Open the production order.
3. On the production order lines, select the line for which you want to order subcontracting.
4. Choose the **Routing** action to view the operations.
5. Select the routing line that contains the subcontracting operation you want to order. You can select multiple routing lines.
6. Choose the **Create Subcontracting Order** action.
7. On the confirmation page, choose **Yes**.

[!INCLUDE [prod_short](includes/prod_short.md)] creates a purchase order with the information from your setup. The subcontractor prices are also transferred. You can send or print the purchase document to your vendor.

> [!NOTE]
> If you select multiple routing lines, each line creates its own purchase order. Purchase orders aren't consolidated, even when two lines share the same subcontractor.

## Create subcontracting purchase orders with the worksheet

The subcontracting worksheet lets you find production orders with material ready to send to a subcontractor and batch-create purchase orders for subcontracted operations. The worksheet functions like the planning worksheet: it calculates the needed supply (purchase orders), which you review and then create with the **Carry Out Action Message** action.

> [!NOTE]
> Only production orders with a status of **Released** can be accessed and used from the subcontracting worksheet.

### Calculate the subcontracting worksheet

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Worksheets**, and then choose the related link.
2. To calculate the worksheet, choose the **Calculate Subcontracts** action.
3. On the **Calculate Subcontracts** page, set filters for the subcontracted operations, or the work centers where they're performed, to calculate only the relevant production orders.
4. Choose the **OK** button.

    Review the lines on the **Subcontracting Worksheets** page. The information in this worksheet comes from the production order and production order routing lines and flows to the purchase order when that document is created. You can delete a row from the worksheet without affecting the original information, just as you can with the other worksheets. The information reappears the next time you run the **Calculate Subcontracts** action.

### Create purchase orders from the worksheet

1. On the **Subcontracting Worksheets** page, choose the **Carry Out Action Message** action.
2. Select the **Print Orders** field to print the purchase order as it's created.
3. Choose the **OK** button.

If all subcontracted operations are sent to the same vendor location, then only one purchase order is created.

The worksheet line that was turned into a purchase order is deleted from the worksheet. After a purchase order is created, it doesn't appear in the worksheet again.

## Review comments for subcontracting orders

When you calculate or refresh a production order, comments on subcontracting routing operations transfer to the corresponding production order routing operations. You can review and adjust the comments before you create the subcontracting purchase order. To learn how to define reusable comments and add them to routing operations, go to [Add comments to subcontracting operations](subcontract-setup.md#add-comments-to-subcontracting-operations).

1. Open the production order, select the production order line, and then choose the **Routing** action.
2. Select the subcontracting operation, and then choose the **Subcontracting Comments** action.
3. Review or change the comments for the production order.

Whether you create the purchase order [directly from the released production order](#create-a-subcontracting-purchase-order-from-a-production-order) or [with the subcontracting worksheet](#create-subcontracting-purchase-orders-with-the-worksheet), [!INCLUDE [prod_short](includes/prod_short.md)] inserts the production routing comments as zero-quantity text lines attached to the corresponding subcontracting purchase line. The text lines keep the same order as the comments. Running direct order creation again doesn't duplicate comment lines that already exist.

Routing attachments that are set up to flow to production and purchase transactions also transfer to the related subcontracting purchase line. To learn more about how to set up routing attachments for subcontracting purchase orders, go to [Set up routing attachments for subcontracting purchase orders](subcontract-setup.md#set-up-routing-attachments-for-subcontracting-purchase-orders).

## Use the Subcontracting Details FactBox

On the purchase order, the **Subcontracting Details** FactBox shows related production orders, transfer orders, routing operations, components, and subcontractor prices for the selected purchase line. Choose a value to open the related document or list.

## View subcontracting purchase orders

You can view the purchase order lines for a subcontracting operation directly from the routing.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then choose the related link.
2. Open the production order.
3. On the production order lines, select the line.
4. Choose the **Routing** action to view the operations.
5. Select the routing line that contains the subcontracting operation.
6. Choose **Subcontracting Purchase Order Lines** action.
7. To view the purchase order, choose the **Show Document** action.

## Print a subcontracting dispatch list

In addition to the purchase order and production order, you can print a subcontracting dispatch list to send with the unfinished product.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Open the purchase order for subcontracting.
3. Choose the **Print Subcontractor Dispatching List** action.
4. On the request page, specify your selection and output options.
5. Choose **Print** or **Preview** to print or send the report.

## Post subcontracting purchase orders

After subcontracting purchase orders are created, they can be posted. Receiving the order posts a capacity ledger entry to the production order, and invoicing the order posts the direct cost of the purchase order to the production order.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then select the related link.
2. Open a purchase order that was created from a production order routing or from the subcontracting worksheet.

    On the purchase order lines, the **Prod. Order No.**, **Prod. Order Line No.**, **Operation No.**, and **Work Center No.** fields are filled in with information from the source production order.

3. Choose the **Post** action.

When the purchase is posted as received, an output journal entry is automatically posted for the production order if the subcontract operation is the last operation on the production order routing.

> [!CAUTION]
> Posting output automatically for an ongoing production order when subcontracted items are received might not be desired. The expected output quantity that is posted might differ from the actual quantity, and the posting date of the automatic output can be misleading.
>
> To avoid that the expected output of a production order is posted when subcontract purchases are received, make sure the subcontracted operation isn't the last one. Alternatively, insert a new last operation for the final output quantity.

When the purchase order is posted as invoiced, the direct cost of the purchase order is posted to the production.

> [!IMPORTANT]
> You must invoice subcontracting purchase orders from the order itself. You can't use the **Get Receipt Lines** or **Get Order Lines** actions on a separate purchase invoice to invoice subcontracting orders. This restriction ensures that costs are assigned correctly to the production order.

> [!NOTE]
> Expected costs are only managed for item transactions, not for immaterial transaction types such as capacity posted via subcontract purchase orders. Posting a receipt might trigger posting of output, but these transactions are separate, and the expected cost of output is calculated independently.

### Receive subcontracting output with a warehouse receipt

Use a warehouse receipt when the purchase order location requires receipt processing. Release the subcontracting purchase order, and then select **Create Whse. Receipt** on the order or use the **Get Source Documents** action on the **Warehouse Receipt** page to retrieve the order. Enter the quantity to receive and post the warehouse receipt. Learn more at [Receive items with warehouse receipts](warehouse-how-receive-items.md).

If the item uses serial or lot tracking, assign or verify the tracking information for the final-operation output before you post the warehouse receipt. Intermediate operations don't support item tracking.

The posting result depends on the routing operation:

- For the final operation, posting records the production output and capacity. It also creates the related item ledger entries, value entries, and warehouse entries. If the location requires put-away processing, complete the warehouse put-away or use the put-away worksheet, depending on the location setup.
- For an intermediate operation, posting records capacity only. It doesn't create item ledger entries, value entries, warehouse entries, or put-away lines.

### Receive subcontracting output with an inventory put-away

Use an inventory put-away when the purchase order location requires put-away processing but doesn't require warehouse receipts.

1. Open the released subcontracting purchase order.
2. Select the **Create Inventory Put-away/Pick...** action.
3. Open the inventory put-away that [!INCLUDE [prod_short](includes/prod_short.md)] creates.
4. Enter the quantity in the **Qty. to Handle** field. If the location uses bins, verify or assign the **Bin Code**. You can split the quantity across multiple put-away lines to use more than one bin.
5. For the final routing operation, if the item uses serial or lot tracking, verify the tracking information that comes from the production order. Intermediate-operation lines don't support item tracking.
6. Select the **Post** action.

You can post part of the quantity and create another inventory put-away for the remainder.

The posting result depends on the routing operation:

- For the final operation, posting records the production output and capacity. It also creates the related item ledger entries, value entries, and warehouse entries.
- For an intermediate operation, posting records capacity only. The put-away line retains its displayed quantity but has a zero base quantity. Posting doesn't create item ledger entries, value entries, or warehouse entries.

## Undo subcontracting receipts

You can undo subcontracting receipts before you post them as invoiced. To undo a subcontracting receipt, follow these steps:

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Purchase Receipts**, and then choose the related link.
2. Open the posted purchase receipt that contains the subcontracting line.
3. Select the line, and then choose the **Undo Receipt** action.

This action creates an identical line with the opposite sign in the **Quantity** field, along with the capacity ledger entry. If the canceled receipt line links to the last routing operation, the undo action also creates an item ledger entry of the type **Output**.

> [!NOTE]
> You can't undo a receipt if it's invoiced or if the production order is finished.

> [!IMPORTANT]
> If posting the subcontracting receipt consumed components because of the flushing method, the undo action doesn't revert the consumption transactions. To reverse these transactions, use an output journal or the **Reverse Production Order Transaction** action. Learn more in [Reverse and correct production order transactions](production-cancel-production-orders-that-have-consumption.md).

## Restrictions and validations

[!INCLUDE [prod_short](includes/prod_short.md)] protects fields on subcontracting purchase orders after components or WIP items have been transferred to the subcontractor (or while transfer orders exist). This prevents inventory discrepancies between what is physically at the vendor and what the documents show.

### Purchase line restrictions

When transfer orders exist for the linked production order, or stock remains at the subcontractor location, you can't change the following fields on a subcontracting purchase line:

- **Quantity**
- **No.**
- **Location Code**
- **Bin Code**
- **Unit of Measure Code**

You also can't delete the purchase line.

The **Variant Code** field is always locked on a subcontracting purchase line that is linked to a production order, regardless of whether transfer orders or stock exist at the subcontractor.

### Purchase order deletion

You can't delete a subcontracting purchase order if components or WIP items have been transferred to the subcontractor location for any of its lines.

## Related information

[Subcontracting overview](production-how-to-subcontract-manufacturing.md)  
[Manage components in subcontracting](subcontract-components.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
