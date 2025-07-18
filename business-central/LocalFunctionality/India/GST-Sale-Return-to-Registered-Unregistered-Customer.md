---
title: Sales Return of Goods from Registered or Unregistered Customer
description: Learn how to process sales returns of goods from registered or unregistered customers in India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, registered customer, unregistered customer, sales return
ms.date: 23/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Sales return of goods from registered or unregistered customer

Sales to a registered customer are known as B2B sales, sales to an unregistered customer are known as B2C sales. There's no difference in computation of tax for a B2B and B2C sales. However, they're required to be reported in separately in GSTR-1.

A customer may require to return the goods or issue credit note due to various reasons like damaged goods, quality issues etc.

Process of sale return from registered or unregistered customer has been explained in this document.

## Create a sales return order or credit memo

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Sales Return Order** or **Sales Credit Memo**, and then choose the related link.
1. Select **Customer** on **Sales Return Order** or **Sales Credit Memo** header, GST customer type should be **Registered** or **Unregistered**.
1. Select **Item Code** for goods or **G/L Account** for Service Sale on **Sales Return Order** or **Sales Credit Memo** line. GST Group Code, HSN/SAC Code shouldn't be blank on Item or G/L Account.

For example, there's a sales credit memo for INR 10,000 and 18% GST (that is, 9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) has to be charged on the credit memo amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

- GL Entries for Intra-State Sales Return of Goods from Registered or Unregistered Customer are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Sales Account**|10,000|  
    |**SGST/UTGST Payable Account**|900|  
    |**CGST Payable Account**|900|
    |**Customer Account**|-11800|

- GL Entries for Inter-State Sales Return of Goods from Registered or Unregistered Customer are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Sales Account**|10,000|  
    |**IGST Payable Account**|1800|
    |**Customer Account**|- 11800|

- GL Entries for Intra-State Sales Return of Services from Registered or Unregistered Customer are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10,000|  
    |**SGST/UTGST Payable Account**|900|  
    |**CGST Payable Account**|900|
    |**Customer Account**|-11800|

- GL Entries for Inter-State Sales Return of Services from Registered or Unregistered Customer are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|10,000|  
    |**IGST Payable Account**|1800|
    |**Customer Account**|- 11800|

## Related information

[Sale Return from Registered Customer with Overseas POS](GST-Sales-Return-to-Registered-Customer-Overseas-POS.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
