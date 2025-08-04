---
title: Record payments and refunds in payment journals
description: Read about how to record payments that you make to vendors, and refunds that you make to customers, on the Payment Journal page.  
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: payment journal, print check, vendor payment, customer refund, refund check, creditor, debt, balance due, AP
ms.search.form: 256, 233, 624, 1228
ms.date: 07/17/2024
ms.service: dynamics-365-business-central

---
# Record payments and refunds in the payment journal

On the **Payment Journals** page, you record payments that you make to vendors and refunds that you make to customers. When you post a payment journal line, the paid amount is recorded on the specified bank account. You must then take steps to perform the actual money transfer from the related bank account.  

Payment journals are general journals that are optimized for making payments. You can quickly add lines manually, you can let [!INCLUDE[prod_short](includes/prod_short.md)] suggest vendor payments, and you can apply the payment to posted documents. Although you're making payments, you enter a positive amount in the **Document Amount** field. Depending on the document type for the journal line, this amount is then converted to a negative amount in the underlying transactions. This way, it's faster for you to add journal lines manually. If you prefer to enter negative amounts, you can personalize the payment journal to show the **Amount** field instead. To learn more about personalizing pages, go to [Start personalizing by using the personalization mode](ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode).  

- Applying payments to invoices or credit memos

    If you fill in the **Applies-to Doc. No.** field with the invoice or credit memo to pay or refund, the document is set to **Paid** when you post the journal. This setting is referred to as "applied." As an alternative to applying when you post a payment, you can use the **Apply Vendor Entries** and **Apply Customer Entries** pages after you post the payment. To learn more, go to, for example, [Reconcile Vendor Payments with the Payment Journal or from Vendor Ledger Entries](payables-how-apply-purchase-transactions-manually.md).  

- Get suggested payments to vendors or employees

    The **Suggest Vendor Payments** and **Suggest Employee Payments** actions can help you fill in payment journal lines automatically according to vendor prioritization and due dates. To learn more, go to [Suggest Vendor Payments](payables-how-suggest-vendor-payments.md). With this function, the **Applies-to Doc. No.** field is always filled in.  

- Print checks and submit payments electronically to your bank

    In addition to recording that the payment is made, you can also use the **Payment Journal** page to output the payment for further processing by your bank. To learn more, go to [Make Check Payments](payables-how-work-checks.md) and [Make Electronic Payments](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).  

## To make payments in the payment journal

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.
2. Open the journal batch that you use for payments.
3. If you know who to pay, fill in the fields manually. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. To also apply the payment to the related invoice or credit memo, choose the **Applies-to Doc. No.** field, on the **Apply Vendor Entries** page, select the relevant invoice or credit memo, and then choose the **OK** button.

    Many fields, such as the **Document Amount** and **Due Date** fields, now contain information from the selected document.
5. Alternatively, use the **Suggest Vendor Payments** action. All the applies-to information and amounts are also entered on the journal lines. To learn more, go to [Suggest Vendor Payments](payables-how-suggest-vendor-payments.md).
6. After you complete all payment journal lines, choose the **Post** action.

## To issue a refund check

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journals**, and then choose the related link.
2. In the **Document Type** field, select **Refund**.  
3. In the **External Document No.** field, enter a reference for the refund check (for example, the return order number).  
4. In the **Account Type** field, select **Customer**.  
5. In the **Account No.** field, select the customer's account number that the refund check is being issued to.  
6. In the **Amount** field, enter the amount to be refunded.  
7. In the **Bal. Account Type** field, select **Bank Account**.  
8. In the **Bal. Account No.** field, select the bank account the check comes out of.  
9. In the **Applies To Doc. No.** field, select the documents that require a refund.  
10. After you complete all payment journal lines, choose the **Post/Print** action, choose the **Post and Print** action, and then choose **Yes**.  
  
## Related information

[Make Check Payments](payables-how-work-checks.md)  
[Make Electronic Payments](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file)  
[Managing Payables](payables-manage-payables.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Export a Positive Pay file](finance-how-positive-pay.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Personalize Your Workspace](ui-personalization-user.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
