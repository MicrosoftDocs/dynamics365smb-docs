---
title: Dutch Payment Scenario 1 - Domestic Payments (LCY to LCY)
description: This article describes a scenario where you can use telebanking for trade with domestic and foreign customers and vendors.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: domestic payments, domestic payments example, Dutch version, Netherlands
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Payment scenario 1 - domestic payments (LCY to LCY) in the Dutch version

You can use telebanking for trade with domestic and foreign customers and vendors. This article describes a scenario where the trade is with domestic customers and vendors.  

The following list describes the main steps:  

1. Create Vendor/Customer.  
1. Create Vendor/Customer Bank Account.  
1. Create and Post Purchase Invoice for Vendor or Sales Invoice for Customer.  
1. Create Proposal.  
1. Create Payment History.  
1. Export Payment History.  
1. Import Bank Statement.  

> [!NOTE]  
> In the following examples, some standard CRONUS data is being used. Likewise, instead of creating a vendor/customer and a vendor/customer bank account, you can use existing data.  

## Create vendor/customer

Create vendor/customer and enter all necessary information. Special attention should be paid to the following fields:  

- **Currency Code**: Leave empty - that is, it's set to the local currency (LCY).  
- **Transaction Mode Code**: Select a transaction mode for local currency payments through your bank.
- **Preferred Bank Account Code**: Select the default vendor or customer bank account in the same currency.

> [!NOTE]  
> To enter a bank account in the **Preferred Bank Account Code** vendor/customer bank accounts must be available. See below.  

### Example

Olek Johansson (code **OLEK**) is one of our local vendors. Purchase invoices are paid through our national bank account (code **ABN**) to their bank account (code **OJBA**). Both bank account ABN and OJBA are denominated in local currency (LCY). Therefore, on Olek Johansson's vendor card, we leave the **Currency Code** field empty, fill the **Transaction Mode Code** field with **ABN** that is linked to our bank account, ABN, and set the **Preferred Bank Account Code** field to **OJBA**.  

## Create vendor/customer bank account

Create vendor/customer bank account and enter all necessary information. Special attention should be paid to the following fields:  

- **Bank Account No.**: Enter a valid bank account number.
- **Currency Code**: Leave empty - that is, it's set to the local currency (LCY).  
- **Account Holder**: Complete the account holder information.

### Example

Olek Johansson's bank account (code **OJBA**) is denominated in local currency (LCY). Therefore, on Olek Johansson's vendor bank account card, we enter a valid number in the **Bank Account No.** field, leave the **Currency Code** field empty, and fill the fields on the **Account Holder** FastTab with appropriate values.

## Create and post purchase invoice for vendor or sales invoice for customer

Create a purchase/sales invoice and enter all necessary information. Special attention should be paid to the following fields:  

- **Currency Code**: Leave empty - that is, it's set to the local currency (LCY).  
- **Transaction Mode Code**: Select a transaction mode for local currency payments through your bank.
- **Bank Account Code**: Select the vendor or customer bank account for the payment.

By default these three fields are populated with values taken from the vendor/customer card.  

When the invoice is finished, it can be posted.  

### Example

When creating a purchase invoice for Olek Johansson, we enter **OLEK** in the **Buy-from Vendor No.** field. By default the **Currency Code**, **Transaction Mode Code** and **Bank Account Code** fields are populated with values taken from the Olek Johansson's vendor card. Therefore, the **Currency Code**, **Transaction Mode Code**, and **Bank Account Code** fields are **\<empty\>**, **ABN**, and **OJBA** respectively. Nevertheless, these values can be changed.  

## Create proposal

Open the **Telebank - Bank Overview** page and browse to the bank through which we want to perform our payment. Open the **Telebank Proposal** page and generate payment proposals using the **Get Proposal Entries** batch job.  

### Example

Through the **Telebank - Bank Overview** page, we open the **Telebank Proposal** page for our bank, ABN. Using the batch job, one proposal line is created for the purchase invoice we just created and posted for vendor OLEK.  

## Create payment history

From the **Telebank Proposal** page, choose **Check** and resolve any errors. Choose **Process** to create the payment history, which is available on the **Payment History List** page for the same bank.

### Example

We process our proposal concerning the payment to vendor OLEK and open the **Payment History List** page for our bank, ABN. The last payment history is the one we created.

## Export payment history

Open the **Payment History List** page, select the payment history, and choose **Export**. Complete any options for the linked export protocol. The protocol determines the file format and uses **Default File Names** to generate the file name. Submit the exported file to your bank.

## Import bank statement

After receiving electronic bank statements from our bank, we can import them by running the appropriate import protocol from the **Import Protocol List** page.  

### Example

The bank statement containing our payment to Olek Johansson is sent to us by our bank, ABN. Therefore, we should choose **OFFICE NET EXTRA** as the appropriate import protocol.  

## Related information

- [Create Proposals](how-to-create-proposals.md)   
- [Create and Export Payment History](how-to-create-and-export-payment-history.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
