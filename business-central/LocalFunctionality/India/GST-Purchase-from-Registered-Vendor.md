---
title: Purchase from Registered Vendors
description: Learn how to process purchases from registered vendors in India, including GST setup, invoice creation, and accounting entries in Dynamics 365 Business Central.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, purchase process, registered vendor, 
ms.date: 23/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Purchase from registered vendors

A registered vendor is a person registered with GST authorities. For a registered vendor, on the vendor card, update the following fields:

- GST Vendor Type as Registered
- GST Registration No
- State Code

For purchases from registered vendors for services attracting reverse charge, purchasers are required to pay the GST tax, to the Government.

If exempted goods and services are purchased from registered vendor, then no GST is to be paid to supplier or to the Government.

Process for purchase from a registered vendor has been explained in this document.

## Create a purchase invoice

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Invoice**, and then choose the related link. 
1. Select **Vendor** on **Purchase Invoice** header, GST vendor type should be **Registered**.
1. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase and **Charge (Item)** for Item Charge on **Purchase Invoice** line. GST Group Code, HSN/SAC Code, and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** should be selected on the Item or G/L Account. 
1. GST Credit option can be changed on invoice line.

For example, invoice is issued for INR 10,000 on which 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction), has to be charged.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|

- GL Entries for Intra-State or Intra-Union Territory purchase of goods from registered vendor where input tax credit is available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|10,000|  
    |**SGST/UTGST Receivable Account**|900|  
    |**CGST Receivable Account**|900|
    |**Vendor Account**|-11800|

- GL Entries for Intra-State or Intra-Union Territory purchase of goods from registered vendor where input tax credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|11,800|  
    |**Vendor Account**|-11800|

- GL Entries for Intra-State or Intra-Union Territory purchase of services from registered vendor where input tax credit is available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|10,000|  
    |**SGST/UTGST Receivable Account**|900|  
    |**CGST Receivable Account**|900|
    |**Vendor Account**|-11800|

- GL Entries for Intra-State or Intra-Union Territory purchase of services from registered vendor where input tax credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|11,800|  
    |**Vendor Account**|-11800|

- GL Entries for Inter-State purchase of goods from registered vendor where input tax credit is available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|10,000|  
    |**IGST Receivable Account**|1800|
    |**Vendor Account**|-11800|

- GL Entries for Inter-State purchase of goods from registered vendor where input tax credit isn't available are as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|11800|  
    |**Vendor Account**|-11800|

- GL Entries for Inter-State purchase of services from registered vendor where input tax credit is available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|10,000|  
    |**IGST Receivable Account**|1800|
    |**Vendor Account**|-11800|

- GL Entries for Inter-State purchase of services from registered vendor where input tax credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|11800|  
    |**Vendor Account**|-11800|

- GL Entries for the Intra-State purchase from registered vendor (reverse charge) are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase or Services Account**|10000|  
    |**CGST Receivable Account (Interim)**|900|
    |**SGST Receivable Account (Interim)**|900|
    |**CGST Payable Account (Interim)**|-900|
    |**SGST Payable Account (Interim)**|-900|
    |**Vendor Account**|-10000|

- GL Entries for the Inter-State purchase from registered vendor (reverse charge) if time of supply is considered on the basis of payment are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase or Services Account**|10000|  
    |**IGST Receivable Account (Interim)**|1800|
    |**IGST Payable Account (Interim)**|-1800|
    |**Vendor Account**|-10000|

- GL Entries on payment to registered vendor (reverse charge) against Intra-State purchase invoice are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Vendor Account**|10000|
    |**CGST Payable Account (Interim)**|900|
    |**SGST Payable Account (Interim)**|900|
    |**CGST Payable Account**|-900|
    |**SGST Payable Account**|-900|
    |**Bank Account**|-10000|  

- GL Entries on payment to registered vendor (reverse charge) against Inter-State purchase invoice are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Vendor Account**|10000|
    |**IGST Payable Account (Interim)**|1800|
    |**IGST Payable Account**|-1800|
    |**Bank Account**|-10000|

- GL Entries for Intra-State or Intra-Union Territory purchase of fixed asset from registered vendor where input tax credit is available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Fixed Asset Increases during the Year**|10000|
    |**SGST Receivable Account**|900|
    |**CGST Receivable Account**|900|
    |**Vendor Account**|-11800|

- GL Entries for Intra-State or Intra-Union Territory purchase of fixed asset from registered vendor where input tax credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Fixed Asset Increases during the Year**|11800|
    |**Vendor Account**|-11800|

> [!TIP]
> In case of Inter-State purchase, IGST is calculated.

- GL Entries for Charge Item in case of Intra-State or Intra-Union Territory in purchase transaction from registered vendor where input tax credit is available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Purchase Account**|10000|
    |**SGST Receivable Account**|900|
    |**CGST Receivable Account**|900|
    |**Vendor Account**|-11800|

- GL Entries for Charge Item in case of Intra-State or Intra-Union Territory in purchase transaction from registered vendor where input tax credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Purchase Account**|11800|
    |**Vendor Account**|-11800|

> [!TIP]
> In case of Inter-State purchase, IGST is calculated.

## Related information

[Purchase from Unregistered Vendor (Reverse Charge)](GST-Purchase-from-Unregistered-Vendor-RCM.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
