---
title: Synchronize and transactions and payouts
description: Set up and run import of transactions and payouts from Shopify.
ms.date: 07/14/2025
ms.topic: how-to
ms.service: dynamics-365-business-central
ms.search.form: 30124, 30125, 30130, 30131, 30132, 30133, 30134, 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Transactions and payouts

When a customer completes their checkout in the online store, the information about payments is saved as a **Transaction**. There might be multiple transactions linked to the order, such as when a customer uses a gift card to pay some of the cost and then uses a credit card or PayPal for the remaining amount.

If you use Shopify Payment as a payment provider, you can also see payouts from Shopify to your bank account. The payouts are in addition to information about money received from the customer.

## Transactions

The payment transactions that take place in Shopify are synchronized with the orders and can be viewed on the **Shopify Orders** page.

To review all transactions, choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transactions**, and select the related link.

The **Posted Invoice No.** field can be helpful in the reconciliation process.

If you configured a payment method mapping, the created sales document is assigned a **Payment Method Code**. Learn more at [Payment Method Mapping](#payment-method-mapping).

## Payouts

If your store uses Shopify Payment, you receive payments through **Shopify Payouts** when a customer pays using Shopify Payments and accelerated checkouts.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, then choose the related link.
2. Select the shop for which you want to synchronize payouts to open the **Shopify Shop Card** page.
3. Choose the **Sync Payouts** action.

To review all payouts, choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payouts**, and select the related link.

**Payouts** are for information purposes only and don't affect the General Ledger or Bank Ledger, though they can be helpful when you process your bank account statement.

## Payment method mapping

To fill in the **Payment method code** for sales documents imported from Shopify automatically, you need to configure **Payment method mapping**.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shops**, then choose the related link.
2. Select the shop for which you want to define a mapping to open the **Shopify Shop Card** page.
3. Choose the **Payment Method Mapping** action.
4. In the **Gateway** and **Credit Card Company** fields, enter the name of the payment method from Shopify. The record gets created automatically when you import Shopify orders.
5. Enter the **Payment Method Code** with the corresponding payment method in [!INCLUDE[prod_short](../includes/prod_short.md)].

> [!NOTE]  
> If the corresponding payment method in [!INCLUDE[prod_short](../includes/prod_short.md)] has **Bal. Account Type** and **Bal. Account No.** populated, then during posting the invoice system will create a balancing entry of the *Payment* type and apply it to the *Invoice* type in the customer ledger entry.

## Basic use case
  
Parties:

* Buyer - person who buys goods from Shopify online store.
* Merchant - your company.
* Payment provider - company that facilitates payment processing for you. Can be Shopify Payments or a third party.

### How money flows

The Buyer buys goods in online store. The last stage is to process payment.

>[!NOTE]
> This example doesn't cover cases when payment is completed outside Shopify checkout, which is valid for B2B scenarios.
  
The Buyer pays with a credit card, PayPal, or a local payment method like MobilePay in Denmark. The Payment Provider takes the full amount from the Buyer. The Buyers' money moves to the Payment Provider.

Depending on the Payment Provider, the Merchant might see this money in their account with the Payment Provider, including received amounts and deducted commissions. Payment providers often take a commission from each transaction, and in some cases they can have a fixed fee as well.
  
Depending on the Payment provider, the Merchant either triggers a transfer of the money to their Bank Account (payout) manually or that happens automatically within a defined period - once per day, once per month, and so on.
  
Depending on the bank, the Merchant can see this incoming transaction at their bank account via online banking or in the bank statement.

There are several options on how to handle payment transactions in [!INCLUDE[prod_short](../includes/prod_short.md)]
  
### Option 1: reconcile incoming transfers to bank account against original invoices
  
Merchant imports sales order to [!INCLUDE[prod_short](../includes/prod_short.md)] and post shipment and invoice.

Result: system creates a **Customer Ledger Entry** of type **Invoice** with the full amount, **Open** is set to Yes. The **Remaining Amount** is equal to the invoiced amount.

Merchant imports bank statement using payment reconciliation journal.

Issues:

1. You might have difficulty if there are multiple invoices (and credit memos), but one lump sum payout from the Payment Provider.
2. Amount usually doesn't match due to commission. You can use payment tolerance or/and payment discounts to handle fees.

### Option 2: reconcile incoming transfers to bank account against interim account representing money at the payment provider
  
Merchant imports sales order to [!INCLUDE[prod_short](../includes/prod_short.md)] and post shipment and invoice.
  
Result: system creates a customer ledger entry of the type **Invoice** with the full amount, and **Open** is set to Yes. The **Remaining Amount** is equal to the invoiced amount.

However, because the sales order has a payment method code where the **Bal. Account Type** and  **Bal. Account No.** fields are filled in, the system automatically creates another customer ledger entry of the type **Payment** and applies it to the customer ledger entry created earlier.

>[!NOTE]
> [!INCLUDE [prod_short](../includes/prod_short.md)] fills in the **Payment Method Code** field based on the payment method mapping. Learn more at [Payment Method Mapping](#payment-method-mapping).
  
You can define balancing accounts for payment methods in two ways:

* **Bal. Account Type** set as **Bank**, and **Bal Account No.** 

   Fill in the special bank account that represents your account at the payment provider.
* **Bal. Account Type** set as **G/L Account** and **Bal Account No.** 
   Fill in the G/L account that represents your account at the payment provider.

It makes sense to use a bank account if the payment provider exports some kind of account statement, which you can import into the payment reconciliation journal.

The merchant imports bank statement using payment reconciliation journal. The incoming payout can be processed:

* As a transfer from another bank. If the transfer takes a few days or involves currency exchange, you might want to use an interim G/L account.
* As a difference on the G/L account that represents your account at the payment provider.
  
The remaining balance on the G/L or bank account that represents your account at the payment provider can be written off as "Fees/Commissions"

Issues:

1. You can create multiple G/L or bank accounts if you're dealing with multiple payment providers. However, sales orders in [!INCLUDE[prod_short](../includes/prod_short.md)] support only one payment method code, which makes it difficult to handle cases when a buyer uses multiple payment methods for an order.

## Reconcile payments in Shopify with invoices

When a customer completes their checkout in the online store, the information about their payment is saved as a Transaction. There can be multiple transactions linked to an order. For example, a customer might use a gift card to pay some of the cost and then use a credit card or PayPal for the remaining amount. The gift card scenario is probably the most common, but there are also store credits, which were recently added to the Shopify admin.

### Sample scenario

This sample scenario involves the following parties:

* The Buyer, who is the person who buys goods from your Shopify online store.
* The Merchant, which is your company.
* The Payment Provider, which is the company that facilitates payment processing for you. The provider can be Shopify Payments or a third party.

### How the money flows

The Buyer buys goods from an online store. The last stage is to process their payment.

The Buyer pays part of the amount with a gift card (or store credit), and the remaining amount with a credit card, PayPal, or a local payment method such as MobilePay in Denmark.

The Merchant can access the issued gift card and information about its use in [!INCLUDE [prod_short](../includes/prod_short.md)].

Depending on the Payment Provider, the Merchant might see the money in their account with the Payment Provider, including both the amount received and the amount deducted for the provider's commissions. Payment providers often take a commission from each transaction, and in some cases they also have a fixed fee.

Depending on the Payment Provider, the Merchant either transfers the money to their bank account (payout) manually or automatically within a defined period. For example, one time per day, per month, and so on.

Depending on the Bank, the Merchant can access the incoming transaction in their bank account via online banking or their bank statement.

### Reconcile transactions and bank statements

The Merchant imports a sales order to [!INCLUDE [prod_short](../includes/prod_short.md)] and posts the shipment and invoice. [!INCLUDE [prod_short](../includes/prod_short.md)] creates a customer ledger entry of the type **Invoice** with the full amount, and sets **Open** to **Yes**. The remaining amount equals the invoiced amount.

The Merchant processes the imported Shopify transactions in the **Transactions** list. They apply filters, and then use the **Suggest Shopify Payments** action to transfer the transactions to the general journal. Alternatively, the Merchant can use the **Suggest Shopify Payments** action on the **Cash Receipt Journal** page.

The Merchant reviews the lines, and notices that the applied documents are selected automatically. They post the journal, and [!INCLUDE [prod_short](../includes/prod_short.md)] creates a customer ledger entry of the type **Payment** and applies it to the corresponding entry of the type **Invoice**.

> [!NOTE] 
> If you configured a payment method mapping, make sure the payment method doesn't have the **Bal. Account Type** and **Bal. Account No.** fields filled in. If they are, when you post the invoice [!INCLUDE [prod_short](../includes/prod_short.md)] creates a balancing entry of the **Payment** type and applies it to the **Invoice** type on the customer ledger entry. You can't create a journal line and apply it to the sales invoice.
>
> Instead, create a **Journal Batch** for each payment method, and fill in the **Bal. Account Type** and **Bal. Account No.** fields.

The Merchant imports their bank statement using a payment reconciliation journal or bank reconciliation journal with one or more transactions that represent the transfer from the Payment Provider to the bank account.

### Handle currency

The Shopify connector imports orders and transactions in **Shop Currency**. If you configure Shopify to use different currencies based on country, that might lead to some differences. For example, in a store where the local currency is Danish Krone (DKK), an order for a German customer totaling 13.95 EUR converts to 409.53 DKK in sales. However, the payment transaction shows 409.48 DKK.

## Related information

[Shopify Connector overview](shopify-connector-overview.md)  
[FAQ for the Shopify connector](shopify-faq.md)  
[Troubleshoot the Shopify Connector](troubleshoot.md)  
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)  
