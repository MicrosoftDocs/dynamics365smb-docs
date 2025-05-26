---
title: Scenario 3 - Foreign Payment (LCY to FCY) [NL]
description: This article describes a third scenario where you can use telebanking for trade with domestic and foreign customers and vendors.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: domestic payments, domestic payments example, Dutch version, Netherlands
ms.date: 03/19/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Payment scenario 3 - Foreign payment (LCY  to FCY) in the Dutch version

You can use telebanking for trade with domestic and foreign customers and vendors. This article describes a scenario where the trade is with foreign customers and vendors that use a different currency than your local currency.  

1. Create Vendor/Customer.  
1. Create Vendor/Customer Bank Account.  
1. Create and Post Purchase Invoice for Vendor or Sales Invoice for Customer.  
1. Create Proposal.  
1. Create Payment History.  
1. Export Payment History.  
1. Import Bank Statement.  

> [!NOTE]  
> In the following examples, some standard CRONUS data is being used. Likewise, instead of creating a vendor/customer and a vendor/customer bank account you could use existing data.  

## Create vendor/customer

Create vendor/customer and enter all necessary information. Special attention should be paid to the following fields:  

- **Currency Code**: Set it to the foreign currency (FCY).  
- **Transaction Mode**: Select an appropriate, default transaction mode - that is, one that can deal with foreign currency payments for your local bank.  
- **Preferred Bank Account**: Select an appropriate, default vendor/customer bank account having the same Currency Code as the vendor/customer itself.  

> [!NOTE]  
> To enter a bank account in the **Bank Account**, vendor/customer bank accounts must be available. See below.  

### Example

Hernandez Ortiz (code **ORTIZ**) is one of our Mexican vendors. Purchase invoices are paid through our national bank account (code **ABN**) to their bank account (code **HOBA**). While our bank account ABN is denominated in local currency (LCY), Hernandez Ortiz's bank account HOBA is denominated in Mexican peso (MXN). Therefore, on Hernandez Ortiz's vendor card, we set the **Currency Code** field to **MXN**, fill the **Transaction Mode** field with **ABN** that is linked to our bank account, ABN, and set the **Bank Account** field to **HOBA**.  

## Create vendor/customer bank account

Create vendor/customer bank account and enter all necessary information. Special attention should be paid to the following fields:  

- **Preferred Bank Account**: Enter a valid bank account number.  
- **Currency Code**: Set it to the foreign currency (FCY).  
- **Owner Information**: Be sure all owner information is entered.  

### Example

Hernandez Ortiz's bank account (code **HOBA**) is denominated in **MXN**. Therefore, on Hernandez Ortiz's vendor bank account card, we enter a valid number in the **Bank Account No.** field, set the **Currency Code** field to **MXN**, and fill the fields on the **Owner Information** FastTab with appropriate values.  

## Create and post purchase invoice for vendor or sales invoice for customer

Create a purchase/sales invoice and enter all necessary information. Special attention should be paid to the following fields:  

- **Currency Code**: Set it to the foreign currency (FCY).  
- **Transaction Mode**: Select an appropriate, default transaction mode - that is, one that can deal with local currency payments for your local bank.  
- **Preferred Bank Account**: Select an appropriate, default vendor/customer bank account having the same Currency Code is the vendor/customer itself.  

By default these three fields are populated with values taken from the vendor/customer card.  

When the invoice is finished, it can be posted.  

### Example

When creating a purchase invoice for Hernandez Ortiz, we enter **ORTIZ** in the **Buy-from Vendor No.** field. By default, the **Currency Code**, **Transaction Mode**, and **Bank Account** fields are populated with values taken from the Hernandez Ortiz's vendor card. Therefore, the **Currency Code**, **Transaction Mode**, and **Bank Account** fields are **MXN**, **ABN**, and **HOBA** respectively. Nevertheless, these values can be changed.  

## Create proposal

Open the **Telebank - Bank Overview** page and browse to the bank through which we want to perform our payment. Open the **Proposal** page and generate payment proposals using the **Get Proposal Entries** batch job.  

### Example

Through the **Telebank - Bank Overview** page, we open the **Proposal** page for our bank, ABN. Using the batch job, one proposal line is created for the purchase invoice we just created and posted for the vendor ORTIZ. The amount of the payment is in local currency (LCY).  

## Create payment history

From the **Proposal** page, we process our proposal into a payment history. The proposal disappears and can be found on the **Payment History Overview** page for the same bank.  

### Example

We process our proposal concerning the payment to the vendor ORTIZ and open the **Payment History Overview** page for our bank, ABN. The last payment history is the one we just created.  

## Export payment history

Open the **Payment History Overview** page, browse to the relevant payment history, and then choose the **Export** action. The export batch job appears for the export protocol that is linked to this payment. For this export, the system already has entered appropriate filters. Check, if wanted, any of the fields on the **Options** FastTab, and choose the **OK** button to export the payment. The system generates a text file using a filename as defined in the **Default File Names Field** field of the export protocol, which now is ready to be sent to our bank.  

### Example

As the transaction mode associated with our payment is **ABN**, the **BBV** or **PAYMUL** batch job appears.  

## Import bank statement

After receiving electronic bank statements from our bank, we can import them by running the appropriate import protocol from the **Import Protocol List** page.  

### Example

The bank statement containing our payment to Hernandez Ortiz is sent to us by our bank, ABN. Therefore, we should choose **OFFICE NET EXTRA** as the appropriate import protocol.  

## Related information

- [Create Proposals](how-to-create-proposals.md)   
- [Create and Export Payment History](how-to-create-and-export-payment-history.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
