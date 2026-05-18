---
title: Order subcontracting from production orders
description: Learn how to create subcontracting purchase orders directly from released production orders and print subcontracting dispatch lists.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, production order, purchase order, dispatch list
ms.search.form: 99000886
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Order subcontracting from production orders

You can create subcontracting purchase orders directly from released production orders. This article describes how to order subcontracting operations and print dispatch lists to send with unfinished products.

## Create a subcontracting purchase order from a production order

The following steps describe how to create a subcontracting purchase order from a released production order.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then choose the related link.
2. Open the production order.
3. On the production order lines, select the line for which you want to order subcontracting.
4. Choose the **Routing** action to view the operations.
5. Select the routing line that contains the subcontracting operation you want to order.
6. Choose the **Order Subcontracting** action.
7. On the confirmation page, choose **Yes**.

[!INCLUDE [prod_short](includes/prod_short.md)] creates a purchase order with the information and descriptions from the **Subcontracting Setup** page. The subcontractor prices are also transferred. You can send or print the purchase document to your vendor.

## Use the Subcontracting Details FactBox

On the purchase order, the **Subcontracting Details** FactBox shows related production orders, transfer orders, routing operations, components, and subcontractor prices for the selected purchase line. Choose a value to open the related document or list.

## View subcontracting purchase orders

You can view the purchase order lines for a subcontracting operation directly from the routing.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Released Production Orders**, and then choose the related link.
2. Open the production order.
3. On the production order lines, select the line.
4. Choose the **Routing** action to view the operations.
5. Select the routing line that contains the subcontracting operation.
6. Choose **Subcontracting Order Lines** action.
7. To view the purchase order, choose the **Show Document** action.

## Print a subcontracting dispatch list

In addition to the purchase order and production order, you can print a subcontracting dispatch list to send with the unfinished product.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. Open the purchase order for subcontracting.
3. Choose the **Print Subcontracting Dispatch List** action.
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

> [!NOTE]
> Expected costs are only managed for item transactions, not for immaterial transaction types such as capacity posted via subcontract purchase orders. Posting a receipt might trigger posting of output, but these transactions are separate, and the expected cost of output is calculated independently.

## Related information

[Subcontracting overview](production-how-to-subcontract-manufacturing.md)  
[Use the subcontracting worksheet](subcontract-worksheet.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]