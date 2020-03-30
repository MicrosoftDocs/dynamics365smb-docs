---
title: Verify Automatically Applied Payments, and Reapply Payments Manually | Microsoft Docs
description: After payments are applied automatically, you can review all the entries for a payment and manually reapply those that were applied incorrectly.

author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, reconcile payment, expenses, cash receipts
ms.date: 04/01/2020
ms.author: sgroespe

---
# Review or Apply Payments Manually After Automatic Application
For each journal line representing a payment on the **Payment Reconciliation Journal** page, you can open the **Payment Application** page to see all candidate open entries for the payment and view detailed information for each entry about the data matching that a payment application is based on. Here, you can manually apply payments or reapply payments that were applied automatically to a wrong entry. For more information about automatic application, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).

> [!IMPORTANT]  
>   When the bank account that you are reconciling payments for is set up for the local currency, then the **Payment Application** page will show all open entries in the local currency, including open entries for documents that were originally invoiced in foreign currencies. Payments applied to entries with converted currencies may therefore be posted with different amounts than on the original document because of the potentially different exchange rates used by the bank and [!INCLUDE[d365fin](includes/d365fin_md.md)] respectively.

Therefore, we recommend that you look for foreign currency codes in the **Currency Code** field on the **Payment Application** page to check if applications are based on converted currencies. To review the original document amount in the foreign currency and to see the exchange rate used, choose the **Applies-to Entry No.** field, and then, on the shortcut menu, choose the drilldown button to open the **Customer Ledger Entries** or **Vendor Ledger Entries** page.

Any gains-and-loss adjustment required due to currency conversions is not handled automatically by [!INCLUDE[d365fin](includes/d365fin_md.md)].

> [!NOTE]  
>   You cannot apply entries with a different sign than the sign on the payment. For example, to close both a negative-sign credit memo and its related positive-sign invoice, you must first apply the credit memo to the invoice, and then apply the payment to the invoice with the reduced remaining amount.

> [!WARNING]  
>   If you use payment discounts, and if the payment date is before the payment due date, then the **Remaining Amt. Incl. Discount** field on the **Payment Application** page will be used for matching. Otherwise, the value in the **Remaining Amount** field will be used. If the payment was made with a discounted amount after the payment due date, or the full amount was paid but a discount was granted, then the amount will not be matched.

> [!NOTE]  
>   You can only apply a payment to one account. If you want to split the application on multiple open entries, for example to apply a lump-sum payment, then the open entries must be for the same account. For more information, see steps 7 and 8 in the procedure in this topic.

## To review or apply payments after automatic application
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Reconciliation Journals**, and then choose the related link.
2. Open the payment reconciliation journal for a bank account that you want to reconcile payments for. For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).
3. On the **Payment Reconciliation Journal** page, select a payment that you want to review or manually apply to one or more open entries, and then choose the **Apply Manually** action.
4. Select the **Applied** check box on the line for the open entry that you want to apply the payment to.
5. The payment amount, which is also shown in the **Transaction Amount** field on the **Payment Application** page, is inserted in the **Applied Amount** field, but you can modify the field, for example if you want to apply the amount to several open entries.
6. To apply a part of the paid amount to another open entry for the account, for example to apply a lump-sum payment, select the **Applied** check box for the line. The applied amount is automatically deducted from the transactions amount to reflect the distribution on the two open entries.
7. To apply a part of a payment to one or more open entries that does not exist in the database, create a new line under the line for the same account. In the **Applied Amount** field, enter the amount to apply on the new line, and then adjust the **Applied Amount** field on the existing line.
8. Repeat steps 5, 6, or 7 for other open entries that you want to apply a full or partial payment amount to.
9. When you have reviewed a payment application or manually applied to one or more open entries, choose the **Accept Application** action.

The **Payment Application** page  closes, and on the **Payment Reconciliation Journal** page, the value in the **Match Confidence** field is changed to **Accepted** to indicate to you that you have reviewed or manually applied the payment.

## See Also
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
