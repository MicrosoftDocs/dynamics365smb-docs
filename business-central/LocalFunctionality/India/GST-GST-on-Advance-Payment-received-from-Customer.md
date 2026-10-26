---
title: GST on Advance Payment Received from Customer
description: Record customer advance receipts and review the related GST calculation and accounting entries in the India localization of Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, GST on advance payment, cash receipt voucher, advance payment reversal create general journal
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# GST on advance payment received from customer

The advance payments received from the customers might need to be reported in GSTR-1 along with GST Rates.

Process of GST calculation on advance payment from customer has been explained in this document.

## Create a general journal or a bank or cash receipt voucher

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **General Journals**, **Bank Receipt Voucher**, or **Cash Receipt Voucher**, and then choose the related link.
1. Set **Document Type** to **Payment** and **Account Type** to **Customer**, and then select the customer in **Account No.** The customer's **GST Customer Type** must be **Registered** or **Unregistered**.
1. Select **G/L Account** or **Bank Account** in balancing account type, and select the cash or bank account.
1. Enter **Location Code**, **GST Group Code**, **HSN/SAC Code**, and **GST Place of Supply**, and turn on **GST on Advance Payment**. Use a GST group of type **Service**. Business Central rejects this option for **Goods**.

For example, advance payment received from customer for INR 10,000 on which 18% GST (that is, 9% CGST and 9% SGST/UTGST) has to be charged.

- GST calculation appears in the Fact Box as follows:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Advance Payment**|10,000|
    |**GST Transactional Value**|8,474 (10000*100/118)|
    |**CGST**|763 (8,475*9%)|  
    |**SGST/UTGST**|763 (8,475*9%)|

- GL Entries for advance payment received from customer, as follows:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Account**|10,000|  
    |**CGST Payable (Interim) Account**|763|  
    |**SGST/UTGST Payable (Interim) Account**|763|
    |**CGST Payable Account**|-763|
    |**SGST/UTGST Payable Account**|-763|
    |**Customer Account**|-10000|

## Reversal of advance payment received from customer

If the customer advance needs to be corrected or the entry is wrongly posted, in such a case the entry can be reversed and new entry can be created.

- Reversal GL Entries for advance payment received from customer, as follows:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|10000|
    |**CGST Payable Account**|763|
    |**SGST/UTGST Payable Account**|763|
    |**CGST Payable (Interim) Account**|-763|  
    |**SGST/UTGST Payable (Interim) Account**|-763|
    |**Bank Account**|-10,000|  

> [!TIP]
> In case of Inter-State Advance Payment, IGST is calculated.

## Related information

[GST Application of Receipt and Invoice](GST-GST-on-Advance-Receipt-Application-to-Sales-Invoice.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
