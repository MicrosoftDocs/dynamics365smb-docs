---
title: Apply payments to unpaid sales documents
description: You apply amounts paid by customers to related sales documents and post the payment to update the customer, general ledger, and bank ledger entries.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: payment process, cash receipts, customer payment
ms.search.form: 1290, 1294, 1287
ms.date: 07/08/2024
ms.service: dynamics-365-business-central
---

# Reconcile customer payments from a list of unpaid sales documents

After customers make electronic payments to your bank account, you must take the following actions:

* Apply each paid amount to the related sales document.
* Post the payment to update the customer, general ledger, and bank ledger entries.

Depending on your business needs, you can register payments manually, automatically, and through payment services.  

> [!NOTE]  
> You can do the same tasks, including vendor payments, on the **Payment Reconciliation Journal** page. For example, you can import bank statements, use automatic application, and reconcile bank accounts. For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).

Use the **Register Customer Payments** page to balance internal accounts by using actual cash figures to ensure that payments are collected. You can quickly verify and post individual or lump-sum payments, process discounted payments, and find the unpaid documents.

You must post payments for different customers that have different payment dates as individual payments. Payments for the same customer that have the same payment date can be posted as a lump-sum payment. Lump-sum payments are useful, for example, when a customer made a single payment that covers multiple sales invoices.

## To set up the payment registration journal

Because you can post different payment types to different balancing accounts, you must select a balancing account on the **Payment Registration Setup** page before you start processing customer payments. If you always post to the same balancing account, you can set that account as the default and avoid this step every time that you open the **Register Customer Payments** page.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Payment Registration Setup**, and then choose the related link. You can also choose the **Setup** action on the **Register Customer Payments** page.
2. Fill in the fields on the **Payment Registration Setup** page. [!INCLUDE [tooltip-inline-tip_md](../archive/SetupAndAdministration/includes/tooltip-inline-tip_md.md)].  

> [!TIP]
> To make it easier to later identify entries that were posted through the journal, you can assign a specific number series to the payment journal. The number series is useful if you use payment reconciliation journals to register and apply payments.

## To register customer payments individually

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Register Customer Payments**, and then choose the related link.  

    The **Register Customer Payments** page shows all posted documents for which a payment can be registered. You can also open the page from the **Customers** and **Customer Card** pages, filtered for the specified customer.  
2. Select the **Payment Made** checkbox on the line that represents the posted document for which a payment was made.
3. In the **Date Received** field, enter the date when the payment was made. This date might be different from the work date.  

   If the **Auto Fill Date Received** checkbox is selected on the **Payment Registration Setup** page, the **Date Received** field contains the work date.  
4. In the **Amount Received** field, enter the amount that was paid.

    For full payments, this amount is the same as the amount in the **Remaining Amount** field on the line. For partial payments, this amount is lower than the amount in the **Remaining Amount** field on the line.
5. Repeat steps 2-4 for other lines for posted documents for which payments are made.  
6. Choose the **Post Payments** action.  

The payment information is posted for documents on lines where the **Payment Made** checkbox is selected. Payments entries are posted to general ledger, bank, and customer accounts.

## To reconcile lump-sum payments

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Register Customer Payments**, and then choose the related link.
2. Select the **Payment Made** checkbox on the lines for posted documents for the same customer and for which a lump-sum payment was made.  

    > [!NOTE]  
    > The customer in the **Name** field must be the same on all lines to include in the lump-sum payment.  

    If the **Auto Fill Date Received** checkbox is selected on the **Payment Registration Setup** page, the **Date Received** field contains the work date.  
3. In the **Date Received** field, enter the date when the payment was made. This date might be different from the work date.  

    > [!NOTE]  
    > This date must be the same on all lines that will be posted as a lump-som payment.  
4. In the **Amount Received** field, enter amounts on multiple lines that sum up to the lump payment amount.  

    > [!TIP]  
    > Try to post as many full payments as possible with the lump-sum amount. Enter amounts that are the same as the amount in the **Remaining Amount** field on as many lines as possible.  
5. Repeat steps 2-4 for other lines that represent posted documents for the same customer for which a lump-sum payment was made.  
6. Choose the **Post As Lump Payment** action.

   The payment information is posted for documents on lines where the **Payment Made** checkbox is selected. Payment entries are posted to general ledger, bank, and customer accounts. Each payment is applied to the related posted sales document.  

If a payment in the bank isn't represented by a line on the **Register Customer Payments** page, it might be because the related document isn't posted. In that case, you can use a search function to quickly find the document and post it to process the payment. For more information, see [To find a specific sales document that isn't fully invoiced](#to-find-a-specific-sales-document-that-isnt-fully-invoiced).  

If a payment in the bank isn't represented by a document, you can open a prefilled general journal from the **Register Customer Payments** page to post the payment directly to the balancing account without applying the payment to a document. Alternatively, you might want to record the payment in the journal until the origin of the payment is resolved. For more information, see [To record or post a payment without a related document](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md#to-record-or-post-a-payment-without-a-related-document).  

## To process customer payments with discounts manually

If you agree on a payment discount with your customer, payment amounts can be lower than the invoice amounts if payment occurs before the agreed discount date.  

The following procedures explain ways to post discounted payments on the **Payment Registration** page.  

* The payment amount is equal to the remaining discounted amount, and the payment date is before the discount date. You post the payment as is.  
* The payment amount is equal to the remaining discounted amount, but the payment date is after the discount date. You post the payment as partial. The document remains open to collect/pay the remaining amount. You can also set the discount date later to allow the payment in full.  
* The payment amount is lower than the remaining discounted amount. You post the payment as partial. The document remains open to collect/pay the remaining amount.  
* The payment amount is more than the remaining discounted amount. You post the payments as is. Only the remaining amount is posted. The extra amount is credited to the customer.  

### To process a payment amount that is equal to the discounted amount and where the payment date is before the discount date

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Register Customer Payments**, and then choose the related link.  
2. Enter the payment amount in the **Amount Received** field. The amount is equal to the amount in the **Rem. Amount Incl. Discount** field.

    The **Payment Made** checkbox is automatically selected, and the **Date Received** field is filled with the work date.
3. In the **Date Received** field, enter the payment date. The date is before the date in the **Pmt. Discount Date** field.
4. Verify that the **Remaining Amount** field contains zero (0).  
5. Choose the **Post Payments** action to post the full payment to general ledger, bank, and customer accounts.

### To process a payment amount that is equal to the discounted amount but where the payment date is after the discount date

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Register Customer Payments**, and then choose the related link.  
2. Enter the payment amount in the **Amount Received** field. The amount is equal to the amount in the **Rem. Amount Incl. Discount** field.

    The **Payment Made** checkbox is automatically selected, and the **Date Received** field is filled with the work date.
3. In the **Date Received** field, enter a payment date that is after the date in the **Pmt. Discount Date** field.

   Date fields change to red font, and an error message is shown at the bottom of the page. The next two steps fix that.
4. Choose the **Details** action.  
5. On the **Payment Registration Details** page, in the **Pmt. Discount Date** field on the **Payment Discount** FastTab, enter a date that is after the date in the **Date Received** field on the **Payment Registration Setup** page.  

    The error message and the red font disappear, and you can continue to process the discounted payment.
6. Verify that the **Remaining Amount** field contains the amount that remains to pay the full invoice amount.  
7. Choose the **Post Payments** action to post the partial payment to general ledger, bank, and customer accounts.  

The related document remains open.

### To process a payment that is lower than the remaining discounted amount

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Register Customer Payments**, and then choose the related link.  
2. Enter the payment amount in the **Amount Received** field. The amount is lower than the amount in the **Rem. Amount Incl. Discount** field.

    The **Payment Made** checkbox is automatically selected, and the **Date Received** field is filled with the work date.  
3. In the **Date Received** field, enter the payment date. The date is before the date in the **Pmt. Discount Date** field.
4. Verify that the **Remaining Amount** field contains the amount that remains to pay the discounted amount.  
5. Choose the **Post Payments** action to post the partial payment to general ledger, bank, and customer accounts.  

The related document remains open.

### To process a payment that is more than the remaining discounted amount

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Register Customer Payments**, and then choose the related link.  
2. Enter the payment amount in the **Amount Received** field. The amount is more than the amount in the **Rem. Amount Incl. Discount** field.  

    The **Payment Made** checkbox is automatically selected, and the **Date Received** field is filled with the work date.
3. In the **Date Received** field, enter the payment date. The date is before the date in the **Pmt. Discount Date** field.
4. Verify that the **Remaining Amount** field contains zero (0).  
5. Choose the **Post Payments** action to post the full payment to general ledger, bank, and customer accounts.  

The related document is closed, and the customer is credited the excess payment amount.  

## To find a specific sales document that isn't fully invoiced

The **Register Customer Payments** page supports you in tasks needed to balance internal accounts with actual cash figures to ensure effective collection from customers. It shows outstanding incoming payments as lines that represent sales documents where an amount is due for payment.  

Typically, when a payment is made, recorded in the bank or otherwise, the sales or purchase document is represented as a line on the **Register Customer Payments** page. The document is waiting for you to post the payment to the outstanding amount. However, sometimes a payment that was made isn't represented by a line on the **Register Customer Payments** page, typically because the document isn't fully invoiced.

Use the **Search Documents** action to search for documents that aren't fully invoiced. You can search based on one or more of the following criteria:  

* Document number  
* Amount or amount range  

The following procedure explains how to find a specific document by using both search criteria.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Register Customer Payments**, and then choose the related link.
2. With the pointer on any line, Choose the **Search Documents** action.
3. On the **Document Search** page, enter a search value in the **Document No.** field.  

    > [!NOTE]  
    > The value that you enter in this field is enclosed in hidden wildcard characters. This means that the action searches for all document numbers that contain the entered value.
4. In the **Amount** field, enter the specific amount on the document you want to find.  
5. In the **Amount Tolerance %** field, enter a percentage value to define the range of amounts that you want to search to find the open document.  

    If you enter 10, the action searches for amounts in a range of plus or minus 10 percent of the value in the **Amount** field.
6. Choose the **Search** action.  

If one or more documents match the criteria, the **Document Search Result** page opens to display lines that represent those documents. Each line contains a document number, description, and an amount.

If a payment in the bank isn't represented by a document, you can use the  open a prefilled general journal from the **Register Customer Payments** page to post the payment directly to the balancing account without applying the payment to a document. Alternatively, you might want to record the payment in the journal until the origin of the payment is resolved.  

## To record or post a payment without a related document

If a payment in the bank isn't represented by a document, you can use the **General Journal** action to open a prefilled general journal line from the **Register Customer Payments** page. Use the journal to post the payment directly to the balancing account without applying the payment to a document. Alternatively, you might want to record the payment in the journal until the origin of the payment is resolved.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Register Customer Payments**, and then choose the related link.
2. Choose the **General Journal** action.  

    The **General Journal** page opens with one line that contains the balancing account of the journal batch that is set up on the **Payment Registration Setup** page.  
3. Fill in the remaining fields on the general journal line. For example, provide the amount, customer number, or information from the bank statement. For more information, see [Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).  

You can post the journal line to update the total on the balancing account. You can also leave the journal line unposted, and perhaps append it with a note that the payment needs more analysis.  

If you don't post the journal line, its value is added to the value in the **Rem. Amount Incl. Discount** field on the **Payment Registration** page.  

## Related information

[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
