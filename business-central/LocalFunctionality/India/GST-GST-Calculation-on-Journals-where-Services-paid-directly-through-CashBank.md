---
title: GST on Journals where Services paid directly through Cash or Bank
description: GST on Journals where Services paid directly through Cash or Bank

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# GST on Journals where Services are Paid Directly through Cash or Bank


Invoice and credit memo can be posted from journals. GST calculation logic for journals will be same as GST calculation for documents. 

GST calculation process has been explained in this document.

## Create a general journal or a bank or cash payment voucher

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, and then choose the related link.
2. Select **G/L Account** in account type and **G/L Account** or **Bank Account** in balancing account type, and then select the cash or bank accounts.
3. GST (CGST/SGST/UTGST/IGST) to be calculated on Direct Expenses (Services) being paid through cash or bank, any legal fees, telephone expenses, etc. 

For example, there is an expense of INR 10,000 and 18% GST (i.e. 9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) has to be charged on expense amount.

- GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800| 

- GL Entries for Intra-State or Intra-Union Territory purchase of services where service provider is unregistered, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|  
    |**SGST/UTGST Receivable Account**|900|  
    |**CGST Receivable Account**|900|
    |**Cash/Bank Account**|-10000|
    |**SGST/UTGST Payable Account**|-900|
    |**CGST Payable Account**|-900|
    
- GL Entries for Intra-state purchase of services where service provider is registered, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000| 
    |**CGST Receivable Account**|900| 
    |**SGST/UTGST Receivable Account**|900| 
    |**Cash/Bank Account**|-11800|  

> [!TIP]
> In case of Inter-State purchase of services, IGST will be applicable.











## Related information 
[GST on Advance Payment to Vendor](GST-GST-on-Advance-Payment-made-to-Vendor.md)


























[!INCLUDE[footer-include](../../includes/footer-banner.md)]
