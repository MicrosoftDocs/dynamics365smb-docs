---
title: Correct prepayments
description: You can make a correction to an order after you have posted a prepayment invoice for the order and add new lines to an order after issuing a prepayment.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 44, 48, 42, 50, 52, 9305, 9307
ms.date: 07/24/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Correct prepayments

You can make a correction to an order after you have posted a prepayment invoice for the order. You can add new lines to an order after issuing a prepayment, and then you can post another prepayment invoice, but you can't delete a line from an order after a prepayment has been invoiced for the line.  

> [!TIP]
> If you have posted a prepayment invoice for a sales invoice that you then correct or cancel, you must correct or cancel the prepayment as well.

## To correct a prepayment

The following procedure shows how to issue a prepayment credit memo to cancel all invoiced prepayments for a sales order.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then choose the related link.  
2. Open the relevant sales order.
3. Choose the **Prepayment** action, and then choose the **Post Prepayment Credit Memo** action or the **Post and Print Prepmt. Cr. Memo** action.  
4. On the **Sales Credit Memo** page, proceed to correct the relevant entries, as for any sales credit memo. For more information, see [Process Sales Returns or Cancellations](sales-how-process-sales-returns-cancellations.md).  

    > [!NOTE]  
    > To reduce the amount in the **Line Amount** field, you must first increase the prepayment percentage on the line so that the value in the **Prepmt. Line Amount** field is not decreased below the value in the **Prepmt. Amt. Inv.** field.

5. To make a prepayment invoice for any new lines in the sales credit memo, choose the **Prepayment** action, and then choose the **Post Prepayment Invoice** action or the **Post and Print Prepmt. Invoice** action.  
6. To issue an additional prepayment invoice, increase the prepayment amount on one or more lines and post the prepayment invoice. A new invoice will be created for the difference between the prepayment amounts invoiced and the new prepayment amounts.  

## Related information

[Invoicing Prepayments](finance-invoice-prepayments.md)  
[Walkthrough: Setting Up and Invoicing Sales Prepayments](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
