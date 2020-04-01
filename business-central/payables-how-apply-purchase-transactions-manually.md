---
title: Reconcile Vendor Payments with the Payment Journal or from Vendor Ledger Entries| Microsoft Docs
description: To process, match, or reconcile vendor payments or refunds manually, you apply the amount to one or more open vendor ledger entries.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment application, payment processing, match payments
ms.date: 04/01/2020
ms.author: sgroespe

---
# Reconcile Vendor Payments with the Payment Journal or from Vendor Ledger Entries
When you send a payment or receive a refund from a vendor, you must decide whether to apply the payment or refund to one or more open entries. You can specify the exact amount that you want to apply to the payment receipt or refund, and then only partially apply vendor ledger entries. You must apply all vendor ledger entries to obtain correct vendor statistics and reports of the account statements and finance charges.

> [!NOTE]  
>   Vendors may sometimes give a payment refund instead of a credit memo to offset against future invoices, especially when you return items that you have already paid for or when you have overpaid an invoice.

You can apply vendor ledger entries in three different ways:

* By entering information in dedicated pages, such as the **Payment Journal** page and the **Payment Reconciliation Journal** page.
* From purchase credit memo documents.
* From vendor ledger entries after purchase documents are posted but not applied.

> [!NOTE]  
>   If the **Application Method** field on the vendor card contains **Apply to Oldest**, then payments will automatically be applied to the oldest open credit entry if you do not manually specify which entry to apply to. If the application method for a customer is **Manual**, then you must apply entries manually.

You can apply vendor payments manually to their related purchase documents when you post the payments on the **Payment Journal** page. For information about filling the payment journal, see [Making Payments](payables-make-payments.md).

You can also apply vendor payments, and customer payments, after the payments appear as negative bank transactions in your bank. On the **Payment Reconciliation Journal** page, you can use functions for bank statement import, automatic application, and bank account reconciliation. For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).

## To apply a payment to a single or multiple vendor ledger entries
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journal**, and then choose the related link.
2. On the **Payment Journal** page, on the first journal line, enter the relevant information about the payment entry.
3. To apply a single vendor ledger entry:
   1. In the **Applies-to Doc. No.** field, choose the field to open the **Apply Vendor Entries** page.
   2. On the **Apply Vendor Entries** page, select the entry to apply the payment to.
   3. On the line in the **Amount to Apply** field, enter the amount to apply to the entry.
4. Or, to apply multiple vendor ledger entries:

   1. Choose the **Apply Entries** action.
   2. On the **Apply Vendor Entries** page, select the lines with the entries to apply the payment to.
   3. Choose the **Set Applies-to ID** action.  
   4. On each line in the **Amount to Apply** field, enter the amount to apply to the individual entry.

      If you do not enter an amount, then the maximum amount is automatically applied. At the bottom of the **Apply Vendor Entries** page, you can see the amount in the Applied Amount field, and you can see whether the application balances.
5. Choose the **OK** button.
6. Choose the **Post** action to post the payment journal.

## To apply a credit memo to a single or multiple vendor ledger entries
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Credit Memo**, and then choose the related link.
2. Open the credit memo that you want to apply.
3. Enter the relevant information in the header.
4. To apply a single vendor ledger entry, on the **Application** FastTab, in the **Applies-to Doc. No.** field, select the entry to apply the credit to, and then, in the **Amount to Apply** field, enter the amount to apply to the entry.
5. Or, to apply multiple vendor ledger entries:

   1. Choose the **Apply Entries** action.
   2. Select the lines with the entries to apply the credit memo to.
   3. Choose the **Set Applies-to ID** action.  
   4. On each line in the **Amount to Apply** field, enter the amount to apply to the individual entry.

       If you do not enter an amount, then the maximum amount is automatically applied. At the bottom of the **Apply Vendor Entries** page, you can see the amount in the **Applied Amount** field, and you can see whether the application balances.
6. Choose the **OK** button.  
   The **Purchase Credit Memo** page shows the entry that you have selected in the **Applies-to Doc. Type** field and the **Applies-to Doc. No.** field. The page also shows the amount of the credit memo to be posted, adjusted for any payment discounts.
7. Choose the **Post** button to post the purchase credit memo.

## To apply posted vendor ledger entries
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the relevant vendor with entries that have already been posted.
3. Choose the **Ledger Entries** action, and then choose the **Apply Entries** action.
4. On the **Apply Vendor Entries** page, you can see the open entries for the vendor.
5. Select the line with the entry that will be applied.
6. Choose the **Set Applies-to ID** action.

    The **Applies-to ID** field displays three asterisks if you work in a single-user system or your user ID if you work in a multiuser system.  
7. For each line in the **Amount to Apply** field, enter the amount to apply to the individual entry.

    If you do not enter an amount, then the maximum amount is automatically applied. You can see the amount in the **Applied Amount** field at the bottom of the **Apply Vendor Entries** page.
8. Choose the **Post Application** action.  

    The **Post Application** page opens with the document number of the applying entry and the posting date of the entry with the most recent posting date.
9. Choose the **OK** button to post the application.

## To apply vendor ledger entries in different currencies to one another
If you buy from a vendor in one currency and make payment in another currency, you can still apply the invoice to the payment.

If you apply an entry (Entry 1) in one currency to an entry (Entry 2) in a different currency, the posting date on Entry 1 is used to find the relevant exchange rate to convert amounts on Entry 2. The relevant exchange rate is found on the **Currency Exchange Rates** page. In that case, you must enable application of vendor ledger entries in different currencies. For more information, see [Enable Application of Ledger Entries in Different Currencies](finance-how-enable-application-ledger-entries-different-currencies.md)

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Journal**, and then choose the related link.
2. Open the journal you want, and fill in the first empty journal line using a currency code.
3. Choose the **Apply Entries** action.
4. Select the line with the entry you want to apply to the entry in the payment journal, choose the **Set Applies-to ID** action, and then select the entry you want to apply to.
5. Choose the **OK** button to return to the payment journal.
6. Post the payment journal.

> [!IMPORTANT]  
>   When you apply entries in different currencies to one another, the entries are converted to USD. Even though the exchange rates for the two relevant currencies are fixed, for example between USD and EUR, there may be a small residual amount when these foreign-currency amounts are converted to USD. These small residual amounts are posted as gains and losses to the account specified in the **Realized Gains Account** or **Realized Losses Account** field on the **Currencies** page. The **Amount (USD)** field is also adjusted on the relevant vendor ledger entries.

## To unapply an application of vendor entries
When you unapply an erroneous application, correcting entries that are identical to the original entry but with opposite sign in the amount field are created and posted for all entries, including all general ledger posting derived from the application, such as payment discount and currency gains/losses. The entries that were closed by the application are reopened.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the relevant vendor card.
3. Choose the **Ledger Entries** action.
4. Select the relevant ledger entry, and then choose the **Unapply Entries** action.
5. Alternatively, choose the **Detailed Ledger Entry** action.
6. Select the application entry, and then choose the **Unapply Entries** action.
7. Fill in the fields in the header, and then choose the **Unapply** action.

> [!IMPORTANT]  
>   If an entry has been applied by more than one application entry, you must unapply the latest application entry first.

## See Also
[Payables](payables-manage-payables.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
