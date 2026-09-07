---
title: Review and apply payments manually after automatic application
description: After payments are applied automatically, you can review all the entries for a payment and manually reapply those that were applied incorrectly.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: payment process, reconcile payment, expenses, cash receipts
ms.search.form: 1290, 1294, 1287
ms.date: 09/07/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---
# Review and apply payments manually after automatic application

For each journal line that represents a payment on the **Payment Reconciliation Journal** page, you can open the **Payment Application** page to review all open entries that might apply to the payment. The page shows detailed information for each entry that the payment application can use for matching. You can apply or reapply payments that were applied automatically to the wrong entry. To learn more about automatic application, go to [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).

You can only apply a payment to one account. If you want to split the application on multiple open entries, for example to apply a lump-sum payment, then the open entries must be for the same account. To learn more, go to steps 7 and 8 in [To review or apply payments after automatic application](#to-review-or-apply-payments-after-automatic-application).

You can't apply entries with a different sign than the sign on the payment. For example, to close both a negative-sign credit memo and its related positive-sign invoice, you must first apply the credit memo to the invoice, and then apply the payment to the invoice with the reduced remaining amount.

> [!IMPORTANT]  
> When the bank account that you're reconciling payments for is set up for the local currency (LCY), the **Payment Application** page shows all open entries in LCY, including open entries for documents that were originally invoiced in foreign currencies. Because the exchange rates that [!INCLUDE [prod_short](includes/prod_short.md)] and your bank use might differ, payments applied to entries with converted currencies might post with different amounts than the amounts on the original document.
>
> Therefore, we recommend that you look for foreign currency codes in the **Currency Code** field on the **Payment Application** page to check whether applications are based on converted currencies. To review the original document amount in the foreign currency and to review the exchange rate that was used, choose the **Applies-to Entry No.** field, and then, on the shortcut menu, choose the drill-down button to open the **Customer Ledger Entries** or **Vendor Ledger Entries** page.
>
> [!INCLUDE[prod_short](includes/prod_short.md)] doesn't automatically handle gains-and-loss adjustments that are required due to currency conversions.

> [!WARNING]  
> If you use payment discounts, if the payment date is before the payment due date, [!INCLUDE [prod_short](includes/prod_short.md)] uses the **Remaining Amt. Incl. Discount** field on the **Payment Application** page for matching. Otherwise, it uses the value in the **Remaining Amount** field. If the payment was made with a discount after its due date, or the full amount was paid but a discount was granted, the amount won't be matched.

> [!TIP]
> When you use the **Apply Manually** action and you have a lot of open ledger entries, the **Payment Application** page might be a little slow to open. To help the page display faster, on the **Payment Application Settings** page, refine what the automatic matching loads and suggests. To open the page, [!INCLUDE [open-search-lowercase](includes/open-search-lowercase.md)], enter **Payment Application Settings**, and then choose the related link. The following settings can speed things up:
>
> - To limit ledger entries to those posted within a certain number of days before the *earliest* bank statement transaction date in the journal, enter a positive number in the **Candidate Lookback (Days)** field. That period applies to the whole journal, so the earliest line keeps all of its candidates. A positive value reduces how many entries are loaded, which improves performance. The default value **0** searches all open entries.
> - To skip the automatic match suggestions and select entries manually, turn on the **Disable Suggestions for Apply Manually page** toggle. This setting has the largest effect on how fast the page opens.
> - To load fewer entries, under **Ledger Entries in "Apply Manually" page**, clear the **Show...** checkboxes for the account types you don't want to apply (customer, vendor, employee, or bank).

## To review or apply payments after automatic application

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Payment Reconciliation Journals**, and then choose the related link.
1. Open the payment reconciliation journal for a bank account that you want to reconcile payments for. Learn more in [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).
1. On the **Payment Reconciliation Journal** page, select a payment that you want to review or manually apply to one or more open entries, and then choose the **Apply Manually** action.
1. Select the **Applied** checkbox on the line for the open entry that you want to apply the payment to.
1. The payment amount, which is also shown in the **Transaction Amount** field on the **Payment Application** page, is inserted in the **Applied Amount** field, but you can modify the amount. For example, if you want to apply the amount to several open entries.
1. To apply a part of the paid amount to another open entry for the account, for example to apply a lump-sum payment, select the **Applied** checkbox for the line. To reflect the distribution on the two open entries, the applied amount is automatically deducted from the transactions amount.
1. To apply a part of a payment to one or more open entries that doesn't exist in the database, create a new line under the line for the same account. In the **Applied Amount** field, enter the amount to apply on the new line, and then adjust the **Applied Amount** field on the existing line.
1. Repeat steps 5, 6, or 7 for other open entries that you want to apply a full or partial payment amount to.
1. After you review a payment application or manually apply it to one or more open entries, choose the **Accept Application** action.

   The **Payment Application** page closes, and on the **Payment Reconciliation Journal** page, the value in the **Match Confidence** field is **Accepted**. Accepted indicates that you have reviewed or manually applied the payment.

## Related information

[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
