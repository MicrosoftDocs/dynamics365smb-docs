---
title: Electronic banking in Finland
description: The electronic banking feature allows processing domestic and foreign payments. Set up bank reference files first to export or import electronic payments.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: electronic banking, customer payments, vendor payments, reference number
ms.search.form: 32000000, 32000001, 32000002, 32000004, 32000005, 32000006
ms.date: 02/12/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Electronic banking in Finland

The [!INCLUDE[prod_short](../../includes/prod_short.md)] electronic banking feature allows you to process electronic customer and vendor payments. This feature supports domestic payments (LM03) and foreign payments (LUM2) for transferring electronic bank payments. To export or import electronic payments, you must first set up bank reference files to determine how payment files are processed.  

## Customer payments

Domestic customer payments can be imported from the bank and linked to the associated accounts receivable entry with a reference number. This type of automation enables incoming payments to be linked directly to open receivables without a delay in manual processing. The following steps explain how to import customer payments into a file from the bank and how to link these payments to invoices through their reference numbers.  

1. Create a sales invoice and assign a unique reference number to the invoice. This reference number is used by the customer when paying the invoice.  
1. Import the payment files that contain customer payments into the cash receipt journal. These files contain the reference numbers received from the bank. The payments are linked to the accounts receivable entry through their reference numbers.  
1. Post the cash receipt journal and close the open accounts receivable entries with the applied payments from the file.  

## Reference number

A reference number is automatically created when an invoice is posted or when an order is posted for invoicing. However, you can enter a reference number manually on a sales journal transaction. This reference number isn't based on the reference number options on the **Sales & Receivables Setup** page. If you enter a reference number for the sales journal, only the validity of the reference number is checked.  

## Vendor payments

To send electronic bank payments to vendors, you can export domestic or foreign vendor payments into a transfer file that can be sent to the bank. The following steps show how to export vendor payments.  

1. Use the **Bank Payments to Send** page to select the vendors for which you want to create payment files.  
1. Enter payment information for each transaction in the payment journal or use **Suggest Vendor Payments** to create suggested payments.  
1. Generate and preview the payment report.  
1. Create a transfer file for domestic or foreign vendor payments.  
1. Send the payment transfer file to the bank.  

## See also

- [Finland Local Functionality](finland-local-functionality.md)
- [Set Up Bank Reference Files](how-to-set-up-bank-reference-files.md)
- [Generate Payment Files](how-to-generate-payment-files.md)
- [Disregard Payment Discounts](how-to-disregard-payment-discounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
