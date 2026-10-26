---
title: GST on Advance Payment and Application with Sales Invoice
description: Apply customer advance receipts to sales invoices and review related GST adjustment and accounting examples in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, GST on advance payment, GST GL entries
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# GST on advance payment and application with sales invoice

GST can also be liable at the time of receiving advance payment from customer. If advance payment is applied to an invoice in the same month, then such applications need not be disclosed in GSTR-1. However, if advance payment is paid in a month and is applied to invoice in the subsequent month, then this application needs to be reported in GSTR-1.

Process of application of advance payment from customer and sale invoice has been explained in this document.

## Apply a customer advance

1. Create the service advance receipt as described in [GST on advance payment received from customer](GST-GST-on-Advance-Payment-received-from-Customer.md).
1. Create a sales invoice for the same customer and enter the service lines with the relevant **GST Group Code** and **HSN/SAC Code**.
1. On the invoice, select the advance receipt in **Applies-to Doc. No.** Review the GST calculation, and then post the invoice.

The GST group on the invoice lines must match the group on the advance receipt when you apply an advance that has **GST on Advance Payment** turned on.

## Example of an advance application

For example, service amount is INR 20000 and customer made an advance payment of INR 10,000 and 18% GST (that is, 9% CGST and 9% SGST/UTGST) has to be charged on the advance payment.

- GST calculation appears in the FactBox as follows:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|
    |**GST Transactional Value**|8,474 (10000*100/118)|
    |**CGST**|763 (8,475*9%)|  
    |**SGST**|763 (8,475*9%)|

Later sales invoice for services is issued to the customer for INR 20,000. 18% GST (that is, 9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) has to be charged on the invoice amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|20000|  
    |**CGST**|1800|  
    |**SGST**|1800|

- GL Entries for application of advance payment with sales invoice are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|23600|  
    |**CGST Payable Account**|-1800|  
    |**SGST/UTGST Payable Account**|-1800|
    |**Sales Account**|-20000|
    |**CGST Payable Account**|763|
    |**SGST/UTGST Payable Account**|763|
    |**CGST Payable (Interim) Account**|-763|
    |**SGST/UTGST Payable (Interim) Account**|-763|  

## Unapply a customer advance from a sales invoice

If the payment and invoice were applied incorrectly, use the unapply functionality to reverse the application. Unapplication entries are the same for applications made during posting and applications made afterward.

> [!TIP]
> An advance receipt and invoice application can't be unapplied, if the tax liability on both is discharged through GST Settlement Screen.

- GL Entries for un-application of an advance payment and sales invoice:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**CGST Payable (Interim) Account**|763|  
    |**SGST/UTGST Payable (Interim) Account**|763|  
    |**CGST Payable Account**|-763|
    |**SGST/UTGST Payable Account**|-763|

> [!TIP]
> In case of Inter-State Sale, IGST is calculated.

## Related information

[GST and TCS on Customer Advance](GST-TCS-on-Advance-Receipt-Application-to-Sales-Invoice.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
