---
title: Synchronize and transactions and payouts
description: Set up and run import of transactions and payouts from Shopify.
ms.date: 06/06/2023
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: 30124, 30125, 30130, 30131, 30132, 30133, 30134, 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
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

## See also

[Get Started with the Connector for Shopify](get-started.md)  
