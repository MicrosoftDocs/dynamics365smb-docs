---
title: Create Prepayment Invoices
description: Handle situations where you or your vendor require prepayment. Use the default percentages for each sales or purchase line or adjust the amount as necessary.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 42, 50, 9305, 9307
ms.date: 12/02/2021
ms.author: edupont

---
# Create Prepayment Invoices

If you require your customers to submit payment before you ship an order to them, you can use the prepayment functionality. The same applies if your vendor requires you to submit payment before they ship an order to you.  

You can start the prepayment process when you create a sales or purchase order. If you have a default prepayment percentage for a given item on the order, or for the customer or vendor, that will be included automatically in the resulting prepayment invoice. You can also specify a prepayment percentage to the entire document.

After you create a sales or purchase order, you can create a prepayment invoice. You can use the default percentages for each sales or purchase line, or you can adjust the amount as necessary. For example, you can specify a total amount for the entire order.  

The following procedure describes how to invoice a prepayment for a sales order. The steps are similar for purchase orders.  

## To create a prepayment invoice

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2. Create a new sales order for the relevant customer. For more information, see [Sell Products](sales-how-sell-products.md).  

    On the **Prepayment** FastTab, the **Prepayment %** field specifies the percentage to use to calculate the prepayment amount. If there is a default prepayment percentage on the customer card, the field is filled in automatically. You can change the percentage. <!--This percentage is applied to lines where the item on that line does not already specify a prepayment percentage. The prepayment percentage is only copied from the header to lines that do not copy the default prepayment percentage from the item.-->  

    Choose the **Compress Prepayment** field if you want to create lines on the prepayment invoice that combine lines from the sales order if:  

    - They have the same general ledger account for prepayments as determined by the general posting setup.  
    - They have the same dimensions.  

    If you want to specify a prepayment invoice with one line for each sales order line that has a prepayment percentage, then do not choose the **Compress Prepayment** field.  

    The due date for the prepayment is calculated automatically based on the value of the **Prepmt. Payment Terms Code**.

3. Fill in the sales lines.  

    If you have specified a default prepayment percentage either for the customer or on the **Prepayment** FastTab on this document, this value is copied to each line. You can change the contents of the **Prepayment %** field on the line.  

    > [!TIP]
    > If you do not see the **Prepayment %** field, you can add it through personalization.  For more information, see [Personalize Your Workspace](ui-personalization-user.md).

4. To view the total prepayment amount, choose the **Statistics** action.

    If you want to adjust the total prepayment amount for the order, you can change the contents of the **Prepayment Amount** field on the **Sales Order Statistics** page.  

    If the **Prices Including VAT** field is selected, the **Prepayment Amount Incl. VAT** field is editable.  

    If you change the contents of the **Prepayment Amount** field, the amount will be distributed proportionately between all lines, except those that have **0** in the **Prepayment %** field.  

5. To print a test report before posting the prepayment invoice, choose the **Prepayment** action, and then choose the **Prepayment Test Report** action.  
6. To post the prepayment invoice, choose the **Prepayment** action, and then choose the **Post Prepayment Invoice** action.  

    To post and print the prepayment invoice, choose the **Post and Print Prepmt. Invoice** action.  

You can issue additional prepayment invoices for the order. To do this, increase the prepayment amount on one or more lines, adjust the document date if necessary, and post the prepayment invoice. A new invoice will be created for the difference between the prepayment amounts invoiced so far and the new prepayment amount.  

> [!NOTE]  
> If you are located in North America, you cannot change the prepayment percentage after the prepayment invoice has been posted. This is prevented in the North American version of [!INCLUDE[prod_short](includes/prod_short.md)] because the calculation of sales tax will otherwise be incorrect.  

 When you are ready to post the rest of the invoice, post it as you would post any invoice, and the prepayment amount will automatically be deducted from the amount due.  

## See Also

[Invoicing Prepayments](finance-invoice-prepayments.md)  
[Walkthrough: Setting Up and Invoicing Sales Prepayments](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Personalize Your Workspace](ui-personalization-user.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]