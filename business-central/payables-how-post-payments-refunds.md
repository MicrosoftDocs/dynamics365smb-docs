---
title: Record Payments and Refunds in Payment Journal
description: Read about how to record payments that you make to vendors, and refunds that you make to customers, on the Payment Journal page.  
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment journal, print check, vendor payment, customer refund, refund check, creditor, debt, balance due, AP
ms.search.form: 256, 233, 624, 1228
ms.date: 07/09/2021
ms.author: bholtorf

---
# Record Payments and Refunds in the Payment Journal

On the **Payment Journal** page, you record payments that you make to vendors and refunds that you make to customers. When you post a payment journal line, the paid amount is recorded on the specified system bank account. You must then take steps to perform the actual money transfer from the related bank account.  

The payment journal is a general journal that is optimized for making payments. You can quickly add lines manually, you can let [!INCLUDE[prod_short](includes/prod_short.md)] suggest vendor payments, and you can apply the payment to posted documents. Even though you are making payments, you enter a positive amount in the **Document Amount** field. Depending on the document type for the journal line, this amount is then converted to a negative amount in the underlying transactions. This way, it's faster for you to add journal lines manually. If you prefer to enter negative amounts, you can personalize the payment journal to show the **Amount** field instead.  

- Applying payments to invoices or credit memos

    If you fill in the **Applies-to Doc. No.** field with the invoice or credit memo that must be paid or refunded, then the document in question is set to paid when you post the journal. This is referred to as "applied". As an alternative to applying during payment posting, you can use the **Apply Vendor Entries** and **Apply Customer Entries** page after you have made the payment posting. For more information, see, for example, [Reconcile Vendor Payments with the Payment Journal or from Vendor Ledger Entries](payables-how-apply-purchase-transactions-manually.md).  

- Get suggested payments to vendors or employees

    The **Suggest Vendor Payments** and **Suggest Employee Payments** functions can help you fill payment journal lines automatically according to vendor prioritization and due dates. For more information, see [Suggest Vendor Payments](payables-how-suggest-vendor-payments.md). With this function, the **Applies-to Doc. No.** field is always filled in.  

- Print checks and submit payments electronically to your bank

    In addition to recording that the payment is made, you can also use the **Payment Journal** page to output the payment for further processing by your bank. For more information, see [Make Check Payments](payables-how-work-checks.md) and [Make Electronic Payments](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).  

## To make payments in the payment journal

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.
2. Open the journal batch that is dedicated to payments.
3. If you know who to pay, fill in the fields manually. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. To also apply the payment to the related invoice or credit memo, choose the **Applies-to Doc No.** field, on the **Apply Vendor Entries** page, select the relevant invoice or credit memo, and then choose the **OK** button.

    Many fields, such as the **Document Amount** and **Due Date** fields, are now filled in with information from the selected document.
5. Alternatively, use the **Suggest Vendor Payments** function. All the applies-to information and amounts are then also entered on the journal lines. For more information, see [Suggest Vendor Payments](payables-how-suggest-vendor-payments.md).

    Messages will guide you to fill in the required fields correctly.
6. When all payment journal lines are completed, choose the **Post** action.


## To issue a refund check

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.
2. In the **Document Type** field, select **Refund**.  
3. In the **External Document No.** field, use this as a reference for the refund check (for example, return order number).  
4. In the **Account Type** field, select **Customer**.  
5. In the **Account No.** field, select the customer's account number that the refund check is being issued to.  
6. In the **Amount** field, enter the amount to be refunded.  
7. In the **Bal Account Type** field, select **Bank Account**.  
8. In the **Bal Account No.** field, select the bank account the check will come out of.  
9. In the **Applies To Doc. No.** field, select the documents requiring a refund.  
10. When all payment journal lines are completed, choose the **Post/Print** action, then choose the **Post and Print** action, and select **Yes**.  
  

## See Also
[Make Check Payments](payables-how-work-checks.md)  
[Make Electronic Payments](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file)  
[Managing Payables](payables-manage-payables.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Export a Positive Pay file](finance-how-positive-pay.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Personalize Your Workspace](ui-personalization-user.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
