---
title: Reconcile customer payments with the cash receipt journal or from customer ledger entries
description: Apply customer cash receipts or refunds to one or more open customer ledger entries.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: payment process, cash receipt
ms.search.form: 25, 255
ms.date: 06/17/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Reconcile customer payments with a cash receipt journal or from customer ledger entries

When you receive a cash payment from a customer or give a cash refund, you can apply the payment or refund to close open debits or credits. You can specify the amount to apply. For example, you can apply partial payments to customer ledger entries. Closing customer ledger entries keeps customer statistics, account statements, finance charges, and so on, up-to-date.

> [!TIP]  
> On the **Customer Ledger Entries** page, red font means that the related payment is past its due date. If overdue payments are becoming a problem, we can help you reduce their frequency. You can enable the **Late Payment Prediction Setup** extension, which uses a predictive model that we built in Azure Machine Learning to predict the timing of payments. These predictions help you reduce outstanding receivables and fine-tune your collections strategy. For example, if a payment is predicted to be late, you can adjust the terms of payment or the payment method for the customer. To learn more, go to [Late Payment Predictions](ui-extensions-late-payment-prediction.md).  

You can apply customer ledger entries in several ways:

* Enter information on the following pages:
   * The **Payment Reconciliation Journals** page. To learn more, go to [Applying Payments Automatically and Reconciling Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).
   * The **Payment Registration Setup** page. To learn more, go to [Reconcile Customer Payments from a List of Unpaid Sales Documents](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md).
   * The **Cash Receipt Journals** page. To learn more, go to [To fill and post a cash receipt journal](#to-fill-and-post-a-cash-receipt-journal).
* By filling in the **Applies-to Doc. No.** field on sales credit memo documents. To learn more, go to [To apply a credit memo to a single customer ledger entry](#to-apply-a-credit-memo-to-a-single-customer-ledger-entry).
* By using the **Set Applies-to ID** action on a customer ledger entry. To learn more, go to [To apply a payment to a single customer ledger entry](#to-apply-a-payment-to-a-single-customer-ledger-entry).
* By using the **Apply Entries** action on the **Bank Deposit** page, and then entering the invoice number in the **Applies-to ID** field. To learn more, go to [Create Bank Deposits](bank-create-bank-deposits.md).

> [!NOTE]  
> If the **Application Method** field on the customer card contains **Apply to Oldest**, payments are applied to the oldest open credit entry, unless you manually specify an entry. If the application method is **Manual**, you always apply entries manually.

## To fill and post a cash receipt journal

A cash receipt journal is a type of general journal. You can use it to post transactions to general ledger, bank, customer, vendor, and fixed assets accounts. You can apply the payment to one or more debit entries when you post the payment. You can also apply from the posted entries later.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Cash Receipt Journals**, and then choose the related link.
2. Choose the **Edit Journal** action.
3. Select the relevant batch in the **Batch Name** field.
4. Fill in the **Posting Date** field.  
5. In the **Document Type** field, select **Payment**.

    The **Document No.** field is filled by the number series assigned to the batch.  
6. Use the **External Document No.** field to store an identifier, such as the customer's check number.

   > [!NOTE]
   > By default, the External Document No. field is hidden. If it is, and you want to use it, you can use personalization to add it. To learn more, go to [Personalize your workspace](ui-personalization-user.md).

7. In the **Account Type** field, select **Customer**.
8. In the **Account No.** field, select the customer.
9. To post the application at the same time as you post the journal, fill in the following fields:
   1. In the **Bal. Account Type** field, select **G/L Account** for cash payments, and **Bank Account** for other payments.
   2. In the **Bal. Account No.** field, select the cash account for cash payments, or the relevant bank account for other payments.
10. Post the journal.

## To apply a payment to a single customer ledger entry

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Cash Receipt Journal**, and choose the related link.
2. Choose the **Edit Journal** action.
3. On the first journal line, enter the relevant information about the entry to be applied.
4. In the **Document Type** field, enter **Payment**.
5. In the **Account Type** field, enter **Customer**.
6. In the **Bal. Account Type** field, enter **Bank Account**.
7. In the **Applies-to Doc. No.** field, choose the field to open the **Apply Customer Entries** page.
8. On the **Apply Customer Entries** page, select the entry to apply the payment to.
9. In the **Amount to Apply** field, enter the amount you want to apply to the entry. If you don't enter an amount, the maximum amount is applied.

    The **Apply Customer Entries** page shows the specific amount in the **Applied Amount** field, and whether the application balances.  
10. Choose the **OK** button. The **Cash Receipt Journal** page now shows the entry in the **Applies-to Doc. Type** and **Applies-to Doc. No.** fields.
11. Post the cash receipt journal.

## To apply a payment to multiple customer ledger entries

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Cash Receipt Journal**, and then choose the related link.
2. Choose the **Edit Journal** action.
3. On the first journal line, enter the relevant information about the entry to be applied.
4. In the **Document Type** field, enter **Payment**.
5. In the **Account Type** field, enter **Customer**.
6. In the **Bal. Account Type** field, enter **Bank Account**.
7. In the **Amount** field, enter the full payment as a negative amount.
8. To apply the payment to multiple customer ledger entries when posting, choose the **Apply Entries** action.  
9. Select the lines with the entries that you want the applying entry to be applied to, and then choose the **Set Applies-to ID** action.  
10. On each line, in the **Amount to Apply** field, enter the amount you want to apply to the individual entry. If you don't enter an amount, the maximum amount is applied.

    The **Apply Customer Entries** page shows the specific amount in the **Applied Amount** field, and whether the application balances.  
11. Choose the **OK** button.
12. Post the cash receipt journal.

## To apply a credit memo to a single customer ledger entry

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Credit Memos**, and then choose the related link.
2. Open the relevant sales credit memo.
3. To apply the credit memo to a single customer ledger entry when posting, in the **Applies-to Doc. No.** field, select the entry to which you want to apply the payment.
4. On the line in the **Amount to Apply** field, enter the amount you want to apply to the entry.  

    If you don't enter an amount, application automatically applies the maximum amount. The **Apply Customer Entries** page shows the specific amount in the **Applied Amount** field, and whether the application balances.  
5. Choose the **OK** button. The **Sales Credit Memo** page now shows the entry you selected in the **Applies-to Doc. Type** and **Applies-to Doc. No.** fields. And the amount of the credit memo to be posted, adjusted for any possible payment discounts.
6. Post the credit memo.

## To apply a credit memo to multiple customer ledger entries

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales Credit Memos**, and then choose the related link.
2. Open the relevant sales credit memo.
3. To apply the credit memo to multiple customer ledger entries when posting, choose the **Apply Entries** action.
4. Select the lines with the entries that you want the applying entry to be applied to, and then choose the **Set Applies-to ID** action.
5. On each line, in the **Amount to Apply** field, enter the amount you want to apply to the individual entry. If you don't enter an amount, the maximum amount is applied.  

    The **Apply Customer Entries** page shows the specific amount in the **Applied Amount** field, and whether the application balances.  
6. Choose the **OK** button. The **Sales Credit Memo** page now shows the amount of the credit memo to be posted, adjusted for any possible payment discounts.
7. Post the credit memo.

## To apply posted customer ledger entries

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers**, and then choose the related link.
2. Open the customer card for the customer with entries that you want to apply.
3. Choose the **Ledger Entries** action from the **Related** tab, and then select the line with the entry that is the applying entry.
4. Choose the **Apply Entries** action. The **Apply Customer Entries** page opens showing the open entries for the customer.
5. Select the lines with the entries that you want the applying entry to be applied to, and then choose the **Set Applies-to ID.** action.
6. For each line in the **Amount to Apply** field, enter the amount you want to apply to the individual entry. If you don't enter an amount, the maximum amount is applied.  

    The **Apply Customer Entries** page shows the specific amount in the **Applied Amount** field.  
7. Choose the **Post Application** action. The **Post Application** page appears with the document number of the applying entry and the posting date of the entry with the most recent posting date.  
8. Choose the **OK** button to post the application.

    If the posted application resulted in closed customer ledger entries, the **Open** field is cleared for these ledger entries.  
9. To access the ledger entries, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Customers**, and then choose the related link. Browse to the card for the customer to access the ledger entries.  

On the ledger entry list, on the line that contains the ledger entry that was fully applied to, notice that the **Open** checkbox isn't selected.  

> [!NOTE]  
> After you select an entry on the **Apply Customer Entries** page, or several entries by setting the **Applies-to ID**, the **Applied Amount** field on the journal line contains the sum of the remaining amounts for the posted entries you selected, unless the field contains something already. If you select **Apply to Oldest** in the **Application Method** field on the customer card, the application occurs automatically.

## To apply customer ledger entries in different currencies to one another

If you sell to a customer in one currency and receive payment in another currency, you can still apply the invoice to the payment.  

Here's an example. You apply Entry A in one currency to Entry B in another currency. The posting date on Entry A is used to find the exchange rate to use to convert amounts on Entry B. The exchange rate is found on the **Currency Exchange Rates** page.  

Applying customer ledger entries in different currencies must be enabled. To learn more, go to [Enable Application of Ledger Entries in Different Currencies](finance-how-enable-application-ledger-entries-different-currencies.md).  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Cash Receipts Journal**, and then choose the related link.
2. Open the journal you want, and fill in the first empty journal line using a currency code.
3. Choose the **Apply Entries** action.
4. Select the line with the entry you want to apply to the entry in the cash receipt journal, choose the **Set Applies-to ID** action, and then select the entry you want to apply to.
5. Choose the **OK** button to return to the cash receipt journal.
6. Post the sales journal.  

> [!IMPORTANT]  
> When you apply entries in different currencies, the entries are converted to USD. Although the exchange rates for the two currencies are fixed, for example between USD and EUR, there might be a small residual amount when they convert to USD. These small residual amounts are posted as gains and losses to the account specified in the **Realized Gains Account** or **Realized Losses Account** fields on the **Currencies** page. The **Amount (USD)** field is also adjusted on the vendor ledger entries.  

## To correct an application of customer entries

When you correct an application, correcting entries are created and posted for all entries. The correcting entries are the same as the originals but have an opposite sign in the **Amount** field. The correcting entries include all general ledger entries derived from the application. For example, the payment discount and currency gains/losses. The entries that the application closed are reopened.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers**, and then choose the related link.
2. Open the relevant customer card.
3. Choose the **Ledger Entries** action.
4. Select the relevant ledger entry, and then choose the **Unapply Entries** action.
5. Alternatively, choose the **Detailed Ledger Entry** action.
6. Select the application entry, and then choose the **Unapply Entries** action.
7. Fill in the fields in the header, and then choose the **Unapply** action.  

> [!IMPORTANT]  
> If an entry was applied by more than one application entry, unapply the latest application entry first.  

## Related information

[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
