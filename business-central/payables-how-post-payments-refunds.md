---
title: Apply Payments to Related Documents and Post Them| Microsoft Docs
description: Describes how to record payments that you make to vendors and refunds that you make to customers.  
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment journal, print check, vendor payment, customer refund, creditor, debt, balance due, AP
ms.date: 04/26/2018
ms.author: sgroespe

---
# Record Payments and Refunds
In the **Payment Journal** window, you record payments that you make to vendors and refunds that you make to customers. When you post a payment journal line, the paid amount is recorded on the specified system bank account. You must then take steps to perform the actual money transfer from the related bank account.

If you fill in the **Applies-to Doc. No.** field with the invoice or credit memo that must be paid, then the document in question is set to paid when you post. This is referred to as "applied". As an alternative to applying during payment posting, you can use the **Apply Vendor Entries** and **Apply Customer Entries** window after you have made the payment posting. For more information, see, for example, [Reconcile Vendor Payments Manually](payables-how-apply-purchase-transactions-manually.md).

The **Suggest Vendor Payments** function can help you fill payment journal lines automatically according to vendor prioritization and due dates. For more information, see [Suggest Vendor Payments](payables-how-suggest-vendor-payments.md). With this function, the **Applies-to Doc. No.** field is always filled in.

In addition to recording that the payment is made, you can also use the **Payment Journal** window to output the payment for further processing by your bank. For more information, see [Make Check Payments](payables-how-work-checks.md) and [Make Electronic Payments](payables-how-export-payments-bank-file.md).  

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.
2. Open the journal batch that is dedicated to payments.
3. If you know who to pay or refund, fill in the fields manually. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. To also apply the payment to the related invoice or credit memo, choose the **Applies-to Doc No.** field, in the **Apply Vendor Entries** window, select the relevant invoice, and then choose the **OK** button.

    Many fields, such as the **Amount** and **Due Date** fields, are now filled in with information from the selected document.
5. Alternatively, use the **Suggest Vendor Payments** function. All the applies-to information and amounts are then also entered on the journal lines. For more information, see [Suggest Vendor Payments](payables-how-suggest-vendor-payments.md).

    Messages will guide you to fill in the required fields correctly.
6.  When all payment journal lines are completed, choose the **Post** action.

## See Also
[Make Check Payments](payables-how-work-checks.md)  
[Make Electronic Payments](payables-how-export-payments-bank-file.md)  
[Managing Payables](payables-manage-payables.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Export a Positive Pay file](finance-how-positive-pay.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
