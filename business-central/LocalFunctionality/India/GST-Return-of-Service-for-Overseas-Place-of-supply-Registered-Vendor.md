---
title: Purchase Return of Services for Overseas Place of Supply to Registered Vendor
description: Purchase Return of Services for Overseas Place of Supply to Registered Vendor

author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Purchase Return of Services for Overseas Place of Supply to Registered Vendor


The supply of goods or services or both when the supplier is located in India and the place of supply is outside India shall be treated to be a supply of goods or services or both in the course of inter-state trade or commerce.

The process of computing tax on purchase return to a vendor with overseas place of supply has been explained in this document.

## Create a purchase return order or purchase credit memo

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Return Order** or **Purchase Credit Memo**, and then choose the related link.
2. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Registered**.
3. Select **G/L Account** on **Purchase Credit Memo** line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** in the G/L Account. 
4. GST Credit option can be changed on **Purchase Credit Memo** line.

For example, if a service recipient has a GSTIN for West Bengal and the Vendor has a GSTIN in West Bengal, but the place of supply is outside India. In this case, IGST will be charged as place of supply is outside India. So, return order or credit memo will be issued for INR 10,000 on which 18% IGST, has to be charged.

- GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

- GL Entries for Return or Credit Note of services for overseas place of supply from registered vendor where input tax credit is available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|11800|  
    |**IGST Receivable Account**|-1800|  
    |**Vendor Account**|-10000|

- GL Entries for Return or Credit Note of services for overseas place of supply from registered vendor where input tax credit is not available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|-11800|  
    |**Vendor Account**|11800|





















## Related information 
[GST Overview](GST-001-Basic-Setup.md)


















[!INCLUDE[footer-include](../../includes/footer-banner.md)]
