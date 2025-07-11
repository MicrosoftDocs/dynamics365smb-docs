---
title: GST and TDS on Vendor Advance Payments
description: Learn how GST and TDS are applied to vendor advance payments in Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, TDS, vendor advance payments
ms.date: 06/25/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# GST and TDS on vendor advance payments

Liability of paying GST and TDS arises at the time of advance payment to vendor.

### Mandatory fields in cash or bank payment voucher

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Payment Voucher** or **Cash Payment Voucher**, and then choose the related link.
1. Select **Vendor** in **Account Type** field and select relevant vendor code in **Account No.** field.
1. Select **G/L Account** for cash or **Bank Account** for bank in **Bal. Account Type** field, and select relevant cash or bank account in **Bal. Account No.** field.
1. Select relevant TDS Section, GST Group Code, HSN/SAC Code, Location Code on journal line.
1. **GST on Advance Payment** should be marked true. 

For example, service amount is INR 20000 and advance payment made to vendor for INR 10000, 18% GST (that is, 9% CGST and 9% SGST/UTGST) and 10% TDS has to be charged.

- GST calculation for Intra-State or Intra-Union Territory transactions appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900 (10000*9%)|  
    |**SGST**|900 (10000*9%)|
    |**TDS Amount**|1000 (10000*10%)|

- On posting of advance payment made to vendor, GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Vendor Account**|10,000|  
    |**SGST/UTGST Receivable (Interim) Account**|900|  
    |**CGST Receivable (Interim) Account**|900|
    |**TDS Payable Account**|-1000|
    |**SGST/UTGST Payable Account**|-900|
    |**CGST Payable Account**|-900|
    |**Bank Account**|-9000|

> [!IMPORTANT]
> In some cases GST needs to be calculated on the amount excluding GST, provision has been made to handle such scenario. Business user need to fill the TDS Base Value in **Amount Excl. GST** filed on **Bank Payment Voucher**, and the system calculates TDS on the mentioned value.

Later invoice for service purchase issued by vendor for INR 20,000, 18% GST (that is, 9% CGST and 9% SGST/UTGST) and 10% TDS, is charged, and the advance payment is applied with the invoice.

### Mandatory fields on purchase invoice

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Invoice**, and then choose the related link.
1. Select **Vendor** on **Purchase Invoice** header.
1. Select **G/L Account** for service on **Purchase Invoice** line.
1. Select TDS Section on **Purchase Invoice** line.
1. GST Group Code, HSN/SAC Code, GST Credit should have a value in **G/L Account** card.
1. **Location Code** field shouldn't be blank on both **Purchase Invoice** header and line.
1. Apply the advance payment in **Applies to Doc. No.** field on **Purchase Invoice** header.
  
- GST calculation appears in the Fact Box as following:

  |Component|Amount|
  |----------------------------------|---------------------------------------|  
  |**GST Base Amount**|20000|  
  |**CGST**|900 = [1800 (20000 * 9%)] - [900 (10000 * 9%)]|  
  |**SGST**|900 = [1800 (20000 * 9%)] - [900 (10000 * 9%)]| 
  |**TDS Amount**|1000 = [2000 (20000 * 10%)] - [1000 (10000 *10%)]|

GST and TDS are calculated on the remaining amount, that is, Invoice Amount - Advance Payment Amount. If advance payment isn't applied with the purchase invoice, then GST and TDS are calculated on the whole invoice amount.

- On posting the purchase invoice, GL Entries are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Vendor Account**|-19000|  
    |**SGST/UTGST Payable (Interim) Account**|-1800|
    |**CGST Payable (Interim) Account**|-1800|
    |**SGST/UTGST Receivable (Interim) Account**|-1800|
    |**CGST Receivable (Interim) Account**|-1800|
    |**TDS Payable Account**|-1000|
    |**CGST Payable (Interim) Account**|900|
    |**CGST Receivable Account**|900|
    |**SGST/UTGST Payable (Interim) Account**|900|
    |**SGST/UTGST Receivable  Account**|900|
    |**SGST/UTGST Receivable (Interim) Account**|1800|
    |**CGST Receivable (Interim) Account**|1800|
    |**Service Account**|20000|

>[!Tip]
>
> Note: In case of Inter-State Purchase, IGST is calculated.

## Related information

[GST on Journals](GST-GST-Calculation-on-Journals-where-Services-paid-directly-through-CashBank.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
