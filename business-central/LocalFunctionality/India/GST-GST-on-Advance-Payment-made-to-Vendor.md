---
title: GST on Advance Payment made to Vendor, with reverse charge
description: Learn how GST is calculated and applied on advance payments made to vendors under reverse charge in Business Central India localization.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, GST on advance payment, cash payment voucher, reverse charge, create a general journal
ms.date: 19/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# GST on advance payment made to vendor with reverse charge

The tax needs to be paid if supplier gets the payment first, therefore we need to calculate GST at the time of advance payment made to the vendor. However, when ‘supplier of goods’ receives advance payment, they aren't required to pay GST at the time of the receipt of advance payment, while GST is required to be paid in case of supply of services.

The process of GST calculation on advance payment to vendor has been explained in this document.

## Create a general journal or a bank or cash payment voucher

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal** or **Bank Payment Voucher** or **Cash Payment Voucher**, and then choose the related link.
1. Select **Vendor** in account type and select relevant **Vendor Code**, GST vendor type, and registration number should be filled in vendor master.
1. Select **G/L Account** or **Bank Account** in balancing account type, and select the cash or the bank account.
1. Advance Payment made to vendor doesn't include tax payment, as the purchaser is liable to pay tax under reverse charge. Hence, tax is applied straight away on base.
1. GST on Advance Payment field needs to be activated on General Journal Line for computation of GST on Advance Payment. In addition, GST Group code and GST Place of Supply shouldn't be blank for computation of GST.

For example, advance payment made to vendor against supply of services of INR 10,000 on which 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) has to be charged.

- GST Calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|

- GL Entries for Advance Payment made to Vendor are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Vendor Account**|10,000|  
    |**SGST/UTGST Receivable (Interim) Account**|900|  
    |**CGST Receivable (Interim) Account**|900|
    |**SGST/UTGST Payable Account**|-900|
    |**CGST Payable Account**|-900|
    |**Bank Account**|-10000|

## Reversal of advance payment made to vendor with reverse charges

If the vendor advance needs to be corrected or the entry is wrongly posted, in such a case the entry can be reversed and new entry can be created.

- Reversal GL Entries for Advance Payment made to Vendor are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Account**|10000|
    |**SGST/UTGST Payable Account**|900|
    |**CGST Payable Account**|900|
    |**SGST/UTGST Receivable (Interim) Account**|-900|  
    |**CGST Receivable (Interim) Account**|-900|
    |**Vendor Account**|-10,000|  

> [!TIP]
> In case of Inter-State Advance Payment, IGST is calculated.

## Related information

[GST Application of Payment and Invoice](GST-Advance-Normal-Payment-and-Purchase-Invoice-Goods-Application.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
