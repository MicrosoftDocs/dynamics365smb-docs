---
title: Apply Payments to Unpaid Sales Documents | Microsoft Docs
description: You apply amounts paid by customers to related sales documents and post the payment to update the customer, general ledger, and bank ledger entries.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, cash receipts, customer payment
ms.date: 09/08/2017
ms.author: sgroespe

---
# Reconcile Customer Payments Manually From a List of Unpaid Sales Documents
When your customers have made payments to your electronic bank account, you must apply each amount paid to the related sales document and then post the payment to update the customer, general ledger, and bank ledger entries.

> [!NOTE]  
>   You can perform the same tasks, including vendor payments, in the **Payment Reconciliation Journal** window using functions for bank statement import, automatic application, and bank account reconciliation. For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).

The **Payment Registration** window is designed to support you in tasks involved in balancing internal accounts by using actual cash figures to make sure that payments are collected efficiently from customers. This payment processing tool enables you to quickly verify and post individual or lump payments, process discounted payments, and find specific unpaid documents for which payment is made.

Payments for different customers that have different payment dates must be posted as individual payments. Payments for the same customer that have the same payment date can be posted as a lump payment. This is useful, for example, when a customer has made a single payment that covers multiple sales invoices.

## To set up the payment registration journal
Because you can post different payment types to different balancing accounts, you must select a balancing account in the **Payment Registration Setup** window before you start processing customer payments. If you always post to the same balancing account, you can set that account as the default and avoid this step every time that you open the **Payment Registration** window.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Registration Setup**, and then choose the related link.

    Alternatively, in the **Payment Registration** window, choose the **Setup** action.    
2. Fill in the fields in the **Payment Registration Setup** window. Choose a field to read a short description of the field or link to related information.  

## To reconcile payments individually
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Registration**, and then choose the related link.  
2. Select the **Payment Made** check box on the line that represents the posted document for which a payment has been made.

    If the **Auto Fill Date Received** check box is selected in the **Payment Registration Setup** window, then the work date is entered in the **Date Received** field.  
3. In the **Date Received** field, enter the date when the payment was made. This date may be different from the work date.  
4. In the **Amount Received** field, enter the amount that has been paid.

    For full payments, this is the same as the amount in the **Remaining Amount** field on the line. For partial payments, this is lower than the amount in the **Remaining Amount** field on the line.    
5. Repeat steps 2-4 for other lines that represent posted documents for which payments are made.  
6. Choose the **Post Payments** action.  

The payment information is posted for documents represented by lines where the **Payment Made** check box is selected.  

Payments entries are posted to general ledger, bank, and customer accounts. Each payment is applied to the related posted sales document.  

## To reconcile lump payments
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Registration**, and then choose the related link.
2. Select the **Payment Made** check box on the lines that represent posted documents for the same customer for which a lump payment has been made.  

    > [!NOTE]  
    >   The customer in the **Name** field must be the same on all lines that will be posted as a lump payment.  

    If the **Auto Fill Date Received** check box is selected in the **Payment Registration Setup** window, then the work date is filled in the **Date Received** field.  
3. In the **Date Received** field, enter the date when the payment was made. This date may be different from the work date.  

    > [!NOTE]  
    >   This date must be the same on all lines that will be posted as a lump payment.  
4. In the **Amount Received** field, enter amounts on multiple lines that sum up to the lump payment amount.  

    > [!TIP]  
    >   Try to post as many full payments as possible with the lump amount. Enter amounts that are the same as the amount in the **Remaining Amount** field on as many lines as possible.  
5. Repeat steps 2-4 for other lines that represent posted documents for the same customer for which a lump payment has been made.  
6. Choose the **Post As Lump Payment** action. The entered payment information is posted for documents represented by lines where the **Payment Made** check box is selected.  

Payment entries are posted to general ledger, bank, and customer accounts. Each payment is applied to the related posted sales document.  

If a payment in the bank is not represented by line in the **Payment Registration** window, it may be because the related document has not yet been posted. In that case, you can use a search function to quickly find the document and post it to process the payment. For more information, see the "To find a specific sales document that is not fully invoiced" section.  

If a payment in the bank is not represented by any document in [!INCLUDE[d365fin](includes/d365fin_md.md)], then you can open a prefilled general journal from the **Payment Registration** window to post the payment directly to the balancing account without applying the payment to a document. Alternatively, you may want to record the payment in the journal until the origin of the payment has been resolved. For more information, see the "To record or post a payment without a related document" section.  

## To process customer payments with discounts manually
If you have agreed on a payment discount with your customer, then the payment amounts can be lower than the invoice amounts if payment occurs before the agreed discount date.  

The following procedures explains four different ways to post discounted payments in the **Payment Registration** window.  

* The payment amount is equal to the remaining discounted amount, and the payment date is before the discount date. You post the payment as is.  
* The payment amount is equal to the remaining discounted amount, but the payment date is after the discount date. You post the payment as partial. The document remains open to collect/pay the remaining amount. Alternatively, you set the discount date later to allow the payment in full.  
* The payment amount is lower than the remaining discounted amount. You post the payment as partial. The document remains open to collect/pay the remaining amount.  
* The payment amount is more than the remaining discounted amount. You post the payments as is. Only the remaining amount is posted. The additional amount is credited to the customer.  

### To process a payment amount that is equal to the discounted amount and where the payment date is before the discount date
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Registration**, and then choose the related link.  
2. Enter the payment amount in the **Amount Received** field. The amount is equal to the amount in the **Rem. Amt. after Discount** field.

    The **Payment Made** check box is automatically selected, and the **Date Received** field is filled with the work date.    
3. In the **Date Received** field, enter the payment date. The date is before the date in the **Pmt. Discount Date** field.
4. Verify that the **Remaining Amount** field contains zero (0).  
5. Choose the **Post Payments** action to post the full payment to general ledger, bank, and customer accounts.

### To process a payment amount that is equal to the discounted amount but where the payment date is after the discount date
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Registration**, and then choose the related link.  
2. Enter the payment amount in the **Amount Received** field. The amount is equal to the amount in the **Rem. Amt. after Discount** field.

    The **Payment Made** check box is automatically selected, and the **Date Received** field is filled with the work date.
3. In the **Date Received** field, enter a payment date that is after the date in the **Pmt. Discount Date** field. Date fields change to red font, and an error message is shown at the bottom of the window.

    > [!TIP]  
    >   If you want to make an exception and grant the discount even though the payment is late, follow these steps:
4. Choose the **Details** action.  
5. In the **Payment Registration Details** window, in the **Pmt. Discount Date** field on the **Payment Discount** FastTab, enter a date that is after the date in the **Date Received** field in the **Payment Registration** window.  

    The error message and the red font disappear, and you can proceed to process the discounted payment.    
6. Verify that the **Remaining Amount** field contains the amount that remains to pay the full invoice amount.  
7. Choose the **Post Payments** action to post the partial payment to general ledger, bank, and customer accounts.  

The related document remains open.

### To process a payment that is lower than the remaining discounted amount
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Registration**, and then choose the related link.  
2. Enter the payment amount in the **Amount Received** field. The amount is lower than the amount in the **Rem. Amt. after Discount** field.

    The **Payment Made** check box is automatically selected, and the **Date Received** field is filled with the work date.  
3. In the **Date Received** field, enter the payment date. The date is before the date in the **Pmt. Discount Date** field.
4. Verify that the **Remaining Amount** field contains the amount that remains to pay the discounted amount.  
5. Choose the **Post Payments** action to post the partial payment to general ledger, bank, and customer accounts.  

The related document remains open.

### To process a payment that is more than the remaining discounted amount
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Registration**, and then choose the related link.  
2. Enter the payment amount in the **Amount Received** field. The amount is more than the amount in the **Rem. Amt. after Discount** field.  

    The **Payment Made** check box is automatically selected, and the **Date Received** field is filled with the work date.    
3. In the **Date Received** field, enter the payment date. The date is before the date in the **Pmt. Discount Date** field.
4. Verify that the **Remaining Amount** field contains zero (0).  
5. Choose the **Post Payments** action to post the full payment to general ledger, bank, and customer accounts.  

The related document is closed, and the customer is credited the excess payment amount.  

## To find a specific sales document that is not fully invoiced
The **Payment Registration** window supports you in tasks needed to balance internal accounts with actual cash figures to ensure effective collection from customers. It shows outstanding incoming payments as lines that represent sales documents where an amount is due for payment.  

Typically, when a payment has been made, recorded in the bank or otherwise, the related sales or purchase document is represented as a line in the **Payment Registration** window because the document in question is waiting for the payment to be posted against the outstanding amount. However, sometimes a payment that has been made is not represented by a line in the **Payment Registration** window, typically because the document in question has not been fully invoice posted.

In the **Document Search** window, you can search among documents that are not fully invoiced. You can search based on one or more of the following criteria:  

* Document number  
* Amount or amount range  

The following procedure explains how to find a specific document by using both search criteria.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Registration**, and then choose the related link.
2. With the pointer on any line, Choose the **Search Documents** action.
3. In the **Document Search** window, enter a search value in the **Document No.** field.  

    > [!NOTE]  
    >   The value that you enter in this field is enclosed in hidden wildcard characters. This means that the function searches for all document numbers that contain the entered value.    
4. In the **Amount** field, enter the specific amount that exists on the document that you want to find.  
5. In the **Amount Tolerance %** field, enter a percentage value to define the range of amounts that you want to search to find the open document.  

    If you enter 10, then the function will search for amounts in a range between ten percent lower and ten percent higher than the value in the **Amount** field.    
6. Choose the **Search** action.  

The Search function searches among documents that are not fully invoiced based on the specified criteria.  

If one or more documents match the criteria, then the **Document Search Result** window opens to display lines that represent those documents. Each line contains a document number, description, and amount so that you can easily find a specific document, for example based on information on your bank statement.  

If a payment in the bank is not represented by any document in [!INCLUDE[d365fin](includes/d365fin_md.md)], then you can open a prefilled general journal from the **Payment Registration** window to post the payment directly to the balancing account without applying the payment to a document. Alternatively, you may want to record the payment in the journal until the origin of the payment has been resolved.  

## To record or post a payment without a related document
If a payment in the bank is not represented by any document [!INCLUDE[d365fin](includes/d365fin_md.md)], then you can open a prefilled general journal line from the **Payment Registration** window to post the payment directly to the balancing account without applying the payment to a document. Alternatively, you may want to record the payment in the journal until the origin of the payment has been clarified.  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Registration**, and then choose the related link.  

Proceed to record an undocumented payment.  

1. Choose the **General Journal** action.  

    The **General Journal** window opens with one line prefilled with the balancing account of the journal batch that is set up in the **Payment Registration Setup** window.  
2. Fill in the remaining fields on the general journal line, such as the amount and the customer number or other information from the bank statement. For more information, see [Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).  

You can either post the journal line to update the total on the balancing account. Alternatively, you can leave the journal line unposted, and perhaps append it with a note that the payment needs more analysis.  

If you leave the journal line unposted, it will add to the value in the **Unposted Balance** field at the bottom of the **Payment Registration** window.  

## See Also
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
