---
title: Create prepayment invoices
description: Handle situations where you or your vendor require prepayment. Use the default percentages for each sales or purchase line or adjust the amount as necessary.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 10/13/2025
ms.custom: bap-template
ms.search.form: 42, 50, 9305, 9307
ms.service: dynamics-365-business-central
---
# Create prepayment invoices

If you require customers to pay before you'll ship their order, you can use the prepayment features. The same applies if your vendor requires you to pay before they ship an order to you.  

You can start the prepayment process when you create a sales or purchase order. The default prepayment percentage for an item on the order, or for the customer or vendor, will be included in the prepayment invoice. You can also specify a prepayment percentage to the entire document.

After you create a sales or purchase order, you can create a prepayment invoice for it. Either use the default percentages for each sales or purchase line, or adjust the amount. For example, you might specify a total amount for the entire order.  

The following procedure describes how to invoice a prepayment for a sales order. The steps are similar for purchase orders.  

## To create a prepayment invoice

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Orders**, and then choose the related link.  
2. Create a new sales order for the relevant customer. For more information, see [Sell Products](sales-how-sell-products.md).  

    On the **Prepayment** FastTab, the **Prepayment %** field specifies the percentage to use to calculate the prepayment amount. If there's a default prepayment percentage on the customer card, the field is filled in automatically. You can change the percentage. <!--This percentage is applied to lines where the item on that line does not already specify a prepayment percentage. The prepayment percentage is only copied from the header to lines that do not copy the default prepayment percentage from the item.-->  

    Choose the **Compress Prepayment** field if you want to create lines on the prepayment invoice that combine lines from the sales order if:  

    - They have the same general ledger account for prepayments as determined by the general posting setup.  
    - They have the same dimensions.  

    If you want to specify a prepayment invoice with one line for each sales order line that has a prepayment percentage, don't choose the **Compress Prepayment** field.  

    The due date for the prepayment is calculated automatically based on the value of the **Prepmt. Payment Terms Code**.

    > [!NOTE]
    > When some lines on an invoice require 100% prepayment and other lines don't, and there's VAT on the prepayment account, the rounded amount might cause an error when you create a prepayment invoice. The error occurs because the prepayment invoice amount is higher than the amounts on the document lines. To fix the problem, change the amounts on one or all of the lines that require 100% prepayment. The change will recalculate the VAT amount rounding and use the accumulated rounding difference on the last modified line.
    >
    > Two more ways to fix the problem are:
    >
    > * Create a separate VAT product posting group and a VAT posting setup with a separate VAT identifier and use that for the items or lines that require 100% prepayment. Rounding is done for each VAT identifier, so separate rounding will be done for items that are assigned to the VAT product posting group.
    > * Use a separate invoice for the items or lines that do and don't require 100% prepayments.

3. Fill in the sales lines.  

    If you've specified a default prepayment percentage either for the customer or on the **Prepayment** FastTab on this document, this value is copied to each line. You can change the contents of the **Prepayment %** field on the line.  

    > [!TIP]
    > If you do not see the **Prepayment %** field, you can add it through personalization.  For more information, see [Personalize Your Workspace](ui-personalization-user.md).

4. To view the total prepayment amount, choose the **Statistics** action.

    If you want to adjust the total prepayment amount for the order, you can change the contents of the **Prepayment Amount** field on the **Sales Order Statistics** page.  

    If the **Prices Including VAT** field is selected, the **Prepayment Amount Incl. VAT** field is editable.  

    If you change the contents of the **Prepayment Amount** field, the amount will be distributed proportionately between all lines, except lines that have **0** in the **Prepayment %** field.  

5. To print a test report before posting the prepayment invoice, choose the **Prepayment** action, and then choose the **Prepayment Test Report** action.  
6. To post the prepayment invoice, choose the **Prepayment** action, and then choose the **Post Prepayment Invoice** action.  

    To post and print the prepayment invoice, choose the **Post and Print Prepmt. Invoice** action.  

You can issue other prepayment invoices for the order. To issue another invoice, increase the prepayment amount on one or more lines, adjust the document date if necessary, and post the prepayment invoice. A new invoice will be created for the difference between the prepayment amounts invoiced so far and the new prepayment amount.  

> [!NOTE]  
> If you are located in North America, you cannot change the prepayment percentage after the prepayment invoice has been posted. This is prevented in the North American version of [!INCLUDE[prod_short](includes/prod_short.md)] because the calculation of sales tax will otherwise be incorrect.  

 When you're ready to post the rest of the invoice, post it as you would post any invoice, and the prepayment amount will automatically be deducted from the amount due.  

## Update the status of prepaid orders and invoices automatically

You can speed up order and invoice processing by setting up job queue entries that automatically update the status of those documents. When a prepayment invoice is paid, the job queue entries can automatically change the document status from **Pending Prepayment** to **Released**. When you set up the job queue entries, the codeunits you'll need to use are **383 Upd. Pending Prepmt. Sales** and **384 Upd. Pending Prepmt. Purchase**. We recommend that you schedule the entries to run frequently, for example, every minute. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## Related information

[Invoicing Prepayments](finance-invoice-prepayments.md)  
[Walkthrough: Setting Up and Invoicing Sales Prepayments](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Personalize Your Workspace](ui-personalization-user.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
