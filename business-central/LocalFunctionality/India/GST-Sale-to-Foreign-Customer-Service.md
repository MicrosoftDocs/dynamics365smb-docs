---
title: Export of Goods and/or Services to Foreign Customer
description: Learn how to export goods and services to foreign customers in India, including GST treatment, invoice creation, and accounting entries.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, foreign customer, create sales invoice, SEZ development, IGST
ms.date: 06/23/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Export of goods and services to foreign customer

Export of goods is defined as taking goods out of India to a place outside India. Export of services means the supply of services where the supplier of service is located in India, recipient of service is located outside India and the place of supply is outside India. Exports can be without Payment of duty or with payment of duty.

Process of sale to foreign customer has been explained in this document.

## Create a sales invoice

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Sales Invoice**, and then choose the related link.
1. Select **Customer** on **Sales Invoice** header, GST customer type should be **Export** or **Deemed Export** or **SEZ Development** or **SEZ Unit**.
1. Select **G/L Account** or **Item Code** on **Sales Invoice** line. **GST Group Code**, **HSN/SAC Code** shouldn't be blank on the **G/L Account** or **Item Card**.

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
> Export or Deemed export have same treatment, as it's treated as interstate transaction and only IGST is applicable irrespective of location of receiver. There's no scenario of deemed export without payment of Duty, as company has to pay IGST and claim refund. Refund can be claimed either by seller or recipient.

## Related information

[Sale to Registered Customer with Overseas POS](GST-Sale-to-Registered-Customer-Overseas-POS.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
