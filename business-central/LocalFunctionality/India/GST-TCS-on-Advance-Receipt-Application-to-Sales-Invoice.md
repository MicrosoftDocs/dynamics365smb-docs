---
title: GST and TCS on Advance Customer Payments
description: Learn how GST and TCS are applied to advance customer payments in Business Central for India, including calculation and posting details.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TCS, advance customer payments
ms.date: 06/25/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# GST and TCS on advance customer payments

Assessee is liable for paying GST and TCS at the time of receiving advance payment from customer.

### Mandatory fields in cash or bank receipt voucher

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Receipt Voucher** or **Cash Receipt Voucher**, and then choose the related link.
1. Select **Customer** in **Account Type** field and select relevant customer code in **Account No.** field.
1. Select **G/L Account** for cash or **Bank Account** for bank in **Bal. Account Type** field, and select relevant cash or bank account in **Bal. Account No.** field.
1. Select relevant TCS Nature of Collection, GST Group Code, HSN/SAC Code, Location Code on journal line.
1. **GST on Advance Payment** should be marked true.  

 For example, service amount is INR 20000 and customer made an advance payment of INR 10,000, 18% IGST and 1% TCS has to be charged on the advance payment.

- GST Calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|
    |**GST Transactional Value**|8,474 (10000*100/118)|
    |**IGST Amount**|1525 (8,474*18%)|
    |**TCS Amount**|100 (10,000*1%)|

- On posting of advance receipt from customer, GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Account**|10000|  
    |**IGST Payable (Interim) Account**|1525|  
    |**IGST Payable Account**|-1525|
    |**TCS Amount**|-100|
    |**Customer Account**|-9900|

Later sales invoice for services is issued to the customer for INR 20,000, 18% IGST and 1% TCS has to be charged on the invoice amount, and the advance receipt from customer is applied with the invoice.

### Mandatory fields on sales invoice

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Sales Invoice**, and then choose the related link.
1. Select **Customer** on **Sales Invoice** header.
1. Select **G/L Account** for service or **Item** for goods on **Sales Invoice** line.
1. Select relevant TCS Nature of Collection on **Sales Invoice** line.
1. GST Group Code, HSN/SAC Code, GST Credit should have a value in **G/L Account** or **Item** card.
1. **Location Code** field shouldn't be blank on both **Sales Invoice** header and line.
1. Select the advance payment in **Applies to Doc. No.** field on **Sales Invoice** header.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|20000|  
    |**IGST**|2075 = [3,600 (20,000 * 18%)]-[1525 (8,474 * 18%)]|  
    |**TCS Amount**|136 = [236 (23,600 * 1%)] - [100 (10,000 * 1%)] |

GST and TCS are calculated on the remaining amount, that is, Invoice Amount - Advance Payment Amount. If advance payment isn't applied with the sales invoice, then GST and TCS ware calculated on the whole invoice amount.

- On posting of sales invoice, GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|23736|  
    |**IGST Payable Account**|-3600|
    |**Sales Account**|-20000|
    |**TCS Payable Account**|-136|
    |**IGST Payable Account**|1525|
    |**IGST Payable (Interim) Account**|-1525|

> [!TIP]
> In case of Intra-State Sale, CGST and SGST/UTGST are calculated.

## Related information

[GST and TDS on Vendor Advance](GST-TDS-on-Advance-Payment-Application-to-Purchase-Invoice.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
