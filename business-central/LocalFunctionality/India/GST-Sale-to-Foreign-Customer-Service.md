---
title: Export of Goods and Services to Foreign Customer
description: Learn how to export goods and services to foreign customers in India, including GST treatment, invoice creation, and accounting entries.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, foreign customer, create sales invoice, SEZ development, IGST
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Export of goods and services to foreign customer

Export of goods is defined as taking goods out of India to a place outside India. Export of services means the supply of services where the supplier of service is located in India, recipient of service is located outside India and the place of supply is outside India. Exports can be without Payment of duty or with payment of duty.

Process of sale to foreign customer has been explained in this document.

## Create a sales invoice

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Sales Invoices**, and then choose the related link.
1. Select **Customer** on **Sales Invoice** header, GST customer type should be **Export** or **Deemed Export** or **SEZ Development** or **SEZ Unit**.
1. Select **G/L Account** or **Item Code** on **Sales Invoice** line. **GST Group Code**, **HSN/SAC Code** shouldn't be blank on the **G/L Account** or **Item Card**.
1. Review **GST Without Payment of Duty** on the invoice header. Select the option that applies to the transaction. Review **Post GST to Customer** for a deemed export or SEZ transaction.

For example, there's a sales invoice for INR 10,000 and 18% IGST has to be charged on the invoice amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

- GL Entries for export of goods and/or services with payment of duty to Foreign Customer, SEZ Unit, SEZ Development Customer are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|10,000|  
    |**IGST Refund Account**|1800|
    |**IGST Payable Account**|-1800|
    |**Sales Account**|-10000|

- GL Entries for export of goods and/or services without payment of duty to Foreign Customer, SEZ Unit, SEZ Development Customer will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|10,000|  
    |**Sales Account**|-10000|

> [!NOTE]
> The examples illustrate the configured posting treatment. They don't determine whether a transaction qualifies as an export, whether payment of duty is required, or who can claim a refund. Confirm the treatment that applies to your transaction before posting.

## Related information

[Sale to Registered Customer with Overseas POS](GST-Sale-to-Registered-Customer-Overseas-POS.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
