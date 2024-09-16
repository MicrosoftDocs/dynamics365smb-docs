---
title: Synchronize and transactions and payouts
description: Set up and run import of transactions and payouts from Shopify.
ms.date: 09/16/2024
ms.topic: article
ms.service: dynamics-365-business-central
ms.search.form: 30124, 30125, 30130, 30131, 30132, 30133, 30134, 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Transactions and payouts

When a customer completes their checkout in the online store, the information about payments is saved as a **Transaction**. There might be multiple transactions linked to the order, such as when a customer uses a gift card to pay some of the cost and then uses a credit card or PayPal for the remaining amount.

If you use Shopify Payment as a payment provider, then in addition to information about money received from the customer by the payment provider, you can also see payouts from Shopify to your bank account.

## Transactions

The payment transactions that take place in Shopify are synchronized with the orders and can be viewed on the **Shopify Orders** page.

To review all transactions, choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transactions**, and select the related link.

The **Posted Invoice No.** field can be helpful in the reconciliation process.

If you configured a payment method mapping then the created sales document will have a Payment Method Code assigned. Learn more at [Payment Method Mapping](#payment-method-mapping).

## Payouts

If your store uses Shopify Payment, you'll receive payments through **Shopify Payouts** when a customer pays using Shopify Payments and accelerated checkouts.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, then choose the related link.
2. Select the shop for which you want to synchronize payouts to open the **Shopify Shop Card** page.
3. Choose the **Sync Payouts** action.

To review all payouts, choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payouts**, and select the related link.

**Payouts** are for information purposes only and don't impact the General Ledger or Bank Ledger, though they can be helpful when you process your bank account statement.

## Payment method mapping

To fill in the **Payment method code** for sales documents imported from Shopify automatically, you need to configure **Payment method mapping**.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, then choose the related link.
2. Select the shop for which you want to define a mapping to open the **Shopify Shop Card** page.
3. Choose the **Payment Method Mapping** action.
4. In the **Gateway** and **Credit Card Company** fields, enter the name of the payment method from Shopify. The record gets created automatically when you import Shopify orders.
5. Enter the **Payment Method Code** with the corresponding payment method in [!INCLUDE[prod_short](../includes/prod_short.md)].
6. Set the **Priority** for cases when the customer uses multiple means of payment. The payment method with the highest priority gets selected in the sales document. If both payment methods have the same priority, the payment method with the highest amount is used.

> [!NOTE]  
> If the corresponding payment method in [!INCLUDE[prod_short](../includes/prod_short.md)] has **Bal. Account Type** and **Bal. Account No.** populated, then during posting the invoice system will create a balancing entry of the *Payment* type and apply it to the *Invoice* type in the customer ledger entry.

## Use cases
  
Parties:

* Buyer - person who buys goods from Shopify online store.
* Merchant - your company.
* Payment provider - company that facilitates payment processing for you. Can be Shopify Payments or a third party.

### How money flows

The Buyer buys goods in online store. The last stage is to process payment.

>[!NOTE]
> This example doesn't cover cases when payment is completed outside Shopify checkout, which is valid for B2B scenarios.
  
The Buyer pays with Credit Card, PayPal, or some local payment method like MobilePay in Denmark. The Payment provider takes the full amount from the Buyer. At this moment the Buyers' money is moved to the Payment Provider.

Depending on the Payment provider, the Merchant might see this money in their account on the Payment Provider - both received amounts, as well as deducted commissions. Payment providers often take a commission from each transaction, and in some cases they can have a fixed fee as well.
  
Depending on the Payment provider, the Merchant either triggers a transfer of the money to their Bank Account (payout) manually or that happens automatically within a defined period - once per day, once per month, and so on.
  
Depending on the bank, the Merchant can see this incoming transaction at their bank account via online banking or in the bank statement.

There are several options on how to handle payment transactions in [!INCLUDE[prod_short](../includes/prod_short.md)]
  
### Option 1: reconcile incoming transfers to bank account against original invoices
  
Merchant imports sales order to [!INCLUDE[prod_short](../includes/prod_short.md)] and post shipment and invoice.

Result: system creates a **Customer Ledger Entry** of type *Invoice* with the full amount, the **Open** is set to Yes. The **Remaining Amount** is equal to the invoiced amount.

Merchant imports bank statement using payment reconciliation journal.

Issues:

1. Can be difficult if there are multiple invoices (and credit memos), but one payout from the payment provider with a lump sum.
2. Amount usually doesn't match due to commission. You can use payment tolerance or/and payment discounts to handle fees.

### Option 2: reconcile incoming transfers to bank account against interim account representing money at the payment provider
  
Merchant imports sales order to [!INCLUDE[prod_short](../includes/prod_short.md)] and post shipment and invoice.
  
Result: system creates a customer ledger entry of the type **Invoice** with the full amount, and **Open** is set to Yes. The **Remaining Amount** is equal to the invoiced amount.

However, because the sales order has a payment method code where the **Bal. Account Type** and  **Bal. Account No.** fields are filled in, the system automatically creates another customer ledger entry of the type **Payment** and applies it to the customer ledger entry created earlier.

>[!NOTE]
> The system populates the Payment Method Code field based on payment method mapping. Learn more at [Payment Method Mapping](#payment-method-mapping).
  
You can define balancing accounts for payment methods in two ways:

* **Bal. Account Type** set as *Bank*, and **Bal Account No.** fill in the special bank account that represents your account at the payment provider.
* **Bal. Account Type** set as *G/L Account** and **Bal Account No.** fill in the G/L account that represents your account at the payment provider.

It makes sense to use a Bank account if the payment provider exports some kind of account statement, which you can import into the payment reconciliation journal.

The merchant imports bank statement using payment reconciliation journal. The incoming payout can be processed:

* as a transfer from another bank. If the transfer takes a few days or involves currency exchange you may want to use an interim G/L Account.
* as a difference on the G/L Account that represents your account at the payment provider.
  
The remaining balance on the G/L or bank account that represents your account at the payment provider can be written off as "Fees/Commissions"

Issues:

1. You can create multiple G/L or bank accounts if you're dealing with multiple payment providers. However, sales orders in [!INCLUDE[prod_short](../includes/prod_short.md)] support only one payment method code, which makes it difficult to handle cases when a buyer uses multiple payment methods for an order.

## Reconcile payments in Shopify with invoices

When a customer completes their checkout in the online store, the information about their payment is saved as a Transaction. There can be multiple transactions linked to an order— for example, a customer might use a gift card to pay some of the cost and then use a credit card or PayPal for the remaining amount. The payment transactions in Shopify synchronize with the orders and you can view them on the Shopify Orders page.

There are several options for processing imported payment transactions in Business Central. This release offers an extra option that's helpful in cases where several payment methods are involved. The gift card scenario is probably the most common, but there are also store credits, which were recently added to the Shopify admin.

### Sample scenario

This sample scenario involves the following parties:

* The buyer, who is the person who buys goods from your Shopify online store.
* The merchant, which is your company.
* The payment provider, which is the company that facilitates payment processing for you. * The provider can be Shopify Payments or a third party.

### How the money flows

The buyer buys goods from an online store. The last stage is to process their payment.

> [!NOTE] 
> This example doesn't cover cases where payment is completed outside Shopify checkout, which is valid for B2B scenarios.

The buyer pays part of the amount with a gift card (or store credit), and the remaining amount with a credit card, PayPal, or a local payment method such as MobilePay in Denmark.

The merchant can access the issued gift card and information about its use in Business Central.

Depending on the payment provider, the merchant might see the money in their account with the payment provider, including both the amount received and the amount deducted for the provider's commissions. Payment providers often take a commission from each transaction, and in some cases they also have a fixed fee.

Depending on the payment provider, the merchant either transfers the money to their bank account (payout) manually or automatically within a defined period. For example, one time per day, per month, and so on.

Depending on the bank, the merchant can see the incoming transaction in their bank account via online banking or their bank statement.

### Reconcile transactions and bank statements

The merchant imports a sales order to [!INCLUDE [prod_short](../includes/prod_short.md)] and posts the shipment and invoice. [!INCLUDE [prod_short](../includes/prod_short.md)] creates a customer ledger entry of the type **Invoice** with the full amount, and sets **Open** to **Yes**. The remaining amount equals the invoiced amount.

The merchant processes the imported Shopify transactions in the **Transactions** list. They apply filters, and then use the **Suggest Shopify Payments** action to transfer the transactions to the general journal. Alternatively, the merchant can use the **Suggest Shopify Payments** action on the **Cash Receipt Journal** page.

The merchant reviews the lines, and notices that the applied documents are selected automatically. They post the journal, and [!INCLUDE [prod_short](../includes/prod_short.md)] creates a customer ledger entry of the type **Payment** and applies it to the corresponding entry of the type **Invoice**.

> [!NOTE] 
> If you configured a payment method mapping, make sure the payment method doesn't have the **Bal. Account Type** and **Bal. Account No.** fields filled in. If they are, when you post the invoice [!INCLUDE [prod_short](../includes/prod_short.md)] creates a balancing entry of the **Payment** type and applies it to the **Invoice** type on the customer ledger entry. You can't create a journal line and apply it to the sales invoice.

Instead, create a **Journal Batch** for each payment method, and fill in the **Bal. Account Type** and **Bal. Account No.** fields.

The merchant imports their bank statement using a payment reconciliation journal or bank reconciliation journal with one or more transactions that represent the transfer from the payment provider to bank account.

### Handle currency

The Shopify connector imports orders and transactions in **Shop Currency**. If you configure Shopify to use different currencies based on country, that might lead to some differences. For example, in a store where the local currency is Danish Krone (DKK), an order for a German customer totaling 13.95 EUR converts to 409.53 DKK in sales. However, the payment transaction shows 409.48 DKK.

## See also

[Get Started with the Connector for Shopify](get-started.md)  
