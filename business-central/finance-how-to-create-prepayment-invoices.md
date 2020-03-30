---
    title: How to Create Prepayment Invoices | Microsoft Docs
    description: Learn how to handle situations where you require prepayment, or your vendor does.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Create Prepayment Invoices
If you require your customers to submit payment before you ship an order to them, or if your vendor requires you to submit payment before they ship an order to you, you can use the prepayment functionality.  

After you create a sales or purchase order, you can create a prepayment invoice. You can use the default percentages for each sales or purchase line, or you can adjust the amount as necessary. For example, you can specify a total amount for the entire order.  

The following procedure describes how to invoice a prepayment for a sales orders. The steps are similar for purchase orders.  

## To create a prepayment invoice  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.  
2. Create a new sales order. For more information, see [sell Products](sales-how-sell-products.md).  

    On the **Prepayment** FastTab, the **Prepayment %** field will be filled in automatically if there is a default prepayment percentage on the customer card. You can change the contents of the field. The prepayment percentage is only copied from the header to lines that do not copy the default prepayment percentage from the item.  

    If the **Compress Prepayment** field is selected, lines will be combined on the invoice if:  
    - They have the same general ledger account for prepayments as determined by the general posting setup.  
    - They have the same dimensions.  

    Leave the field blank if you want to specify a prepayment invoice with one line for each sales order line that has a prepayment percentage.  

3. Fill in the sales lines.  

    If default prepayment percentages have been set up for your items, they are automatically copied to the **Prepayment %** field on the line. Otherwise, the prepayment percentage is copied from the header. You can change the contents of the **Prepayment %** field on the line.  
4. If you want to apply one prepayment percentage to the entire order, change the **Prepayment %** field on the header after filling in the lines.  
5. To view the total prepayment amount, choose the **Statistics** action.

    If you want to adjust the total prepayment amount for the order, you can change the contents of the **Prepayment Amount** field on the **Sales Order Statistics** page.  

    If the **Prices Including VAT** field is selected, the **Prepayment Amount Incl. VAT** field is editable.  

    If you change the contents of the **Prepayment Amount** field, the amount will be distributed proportionately between all lines, except those that have **0** in the **Prepayment %** field.  
6. To print a test report before posting the prepayment invoice, choose the **Prepayment** action, and then choose the **Prepayment Test Report** action.  
7. To post the prepayment invoice, choose the **Prepayment** action, and then choose the **Post Prepayment Invoice** action.  

    To post and print the prepayment invoice, choose the **Post and Print Prepmt. Invoice** action.  

You can issue additional prepayment invoices for the order. To do this, increase the prepayment amount on one or more lines, adjust the document date if necessary, and post the prepayment invoice. A new invoice will be created for the difference between the prepayment amounts invoiced so far and the new prepayment amount.  

> [!NOTE]  
>  If you are located in North America, you cannot change the prepayment percentage after the prepayment invoice has been posted. This is prevented in the North American version of [!INCLUDE[d365fin](includes/d365fin_md.md)] because the calculation of sales tax will otherwise be incorrect.  

 When you are ready to post the rest of the invoice, post it as you would post any invoice, and the prepayment amount will automatically be deducted from the amount due.  

## See Also  
[Invoicing Prepayments](finance-invoice-prepayments.md)  
[Walkthrough: Setting Up and Invoicing Sales Prepayments](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
