---
title: GST on advance payment received from customer
description: GST on Advance Payment received from Customer
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 12/13/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# GST on advance payment received from customer


The advance payments received from the customers might need to be reported in GSTR-1 along with GST Rates.

Process of GST calculation on advance payment from customer has been explained in this document.

### Create a general journal or a bank or cash receipt voucher

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal** or **Bank Payment Voucher** or **Cash Receipt Voucher**, and then choose the related link.
2. Select **Customer** in account type and select relevant **Customer Code**, GST customer type and registration number shouldn't be blank on customer master.
3. Select **G/L Account** or **Bank Account** in balancing account type, and select the cash or bank account. 
4. GST on Advance Payment field needs to be activated in General Journal Line for computation of GST on Advance Payment. In addition, GST Group code and GST Place of Supply are to be entered for computation of GST.

For example, advance payment received from customer for INR 10,000 on which 18% GST (i.e. 9% CGST and 9% SGST/UTGST) has to be charged.

- GST calculation appears in the Fact Box, as follows:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Advance Payment**|10,000|
    |**GST Transitional Value**|8,474 (10000*100/118)|
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
> In case of Inter-State Advance Payment, IGST will be calculated.



## Related information 
[GST Application of Receipt and Invoice](GST-GST-on-Advance-Receipt-Application-to-Sales-Invoice.md)




































[!INCLUDE[footer-include](../../includes/footer-banner.md)]
