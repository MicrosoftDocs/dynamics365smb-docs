---
title: Using the Transfer Difference to Account Feature to Reconcile Payments | Microsoft Docs'
description: Describes how to process payments that cannot be applied to a document, for example, when an exchange rate causes amounts to differ.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, cash receipts
ms.date: 04/01/2020
ms.author: sgroespe

---
# Reconcile Payments that Cannot be Applied Automatically
You may sometimes have to handle payments to your bank account that cannot be applied to a related open customer, vendor or bank account ledger entry. Reasons may be that no document exists in [!INCLUDE[d365fin](includes/d365fin_md.md)] that the payment can be applied to, or the related document in [!INCLUDE[d365fin](includes/d365fin_md.md)] has a different amount than the transaction amount, for example, because of currency exchange. On the **Payment Reconciliation Journal** page, all transaction amounts for payments that are not yet applied appear in the **Difference** field, including amounts that cannot be applied because of reasons such as the above.

Payments that cannot be applied can appear on payment reconciliation journal lines in the following different ways:

* The value in the **Difference** field is equal to the value in the **Transaction Amount** field, which indicates that no part of the payment can be applied to a related open customer, vendor, or bank account ledger entry.
* The value in the **Difference** field is lower than the value in the **Transaction Amount** field, which indicates that a part of the payment can be applied to a related open customer, vendor, or bank account ledger entry. The remaining part of the payment cannot be applied and must be reconciled manually or by posting it directly to an account.

To reconcile such payments, you can choose the **Transfer Difference to Account** button and then specify to which account the amount in the **Difference** field will be posted when you post the payment reconciliation journal.

> [!TIP]  
>   Similar functionality exists to set up automatic reconciliation of recurring payments that cannot be applied to related open customer, vendor, or bank account ledger entries. For more information, see [Map Text on Recurring Payments to Accounts for Automatic Reconciliation](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

## To reconcile payments that cannot be applied automatically
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Reconciliation Journals**, and then choose the related link.
2. Open a payment reconciliation journal. For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).
3. Choose the **Transfer Difference to Account**. The **Transfer Difference to Account** page opens.
4. In the **Account Type** field, specify if the type of account that the payment amount will be posted to.
5. In the **Account No.** field, specify the account that the payment amount will be posted to.
6. In the **Description** field, specify text that describes this direct payment posting. By default, the text in the **Transaction Text** field on the payment reconciliation journal line is inserted.
7. Choose the **OK** button.

If the value in the **Difference** field was equal to the value in the **Transaction Amount** field when you post the payment reconciliation journal, the whole payment on the journal line will be posted directly to the specified balancing account.

If the value in the **Difference** field was lower than the value in the **Transaction Amount** field, then an additional journal line will be created with the same text and date and with the difference inserted in the **Transaction Amount** field. On the original journal line, the difference will be deducted from the value in the **Transaction Amount** field, and the payment will remain applied to its related customer, vendor, or bank account ledger entry. When you post the payment reconciliation journal, one part of the payment will be posted as an applied payment. The other part of the payment will be posted directly to the specified account.

## See Also
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
