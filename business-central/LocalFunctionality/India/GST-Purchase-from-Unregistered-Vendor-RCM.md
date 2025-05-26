---
title: Purchase of Goods from an Unregistered Vendor (Reverse Charge)
description: Purchase of Goods from an Unregistered Vendor (Reverse Charge)

author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Purchase of Goods from an Unregistered Vendor (Reverse Charge)


Persons whose aggregate turnover in a financial year does not exceed forty lakh rupees are not required to be registered with the GST authorities. Such persons are called unregistered vendors. Any purchases from unregistered vendors do not attract GST. However, there are some notified services under GST, on supply of such services GST is applicable under reverse charge mechanism i.e. the purchasers are required to pay GST tax to the Government.

Purchase process for unregistered vendor has been explained in this document.

## Create a purchase invoice


1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Invoice**, and then choose the related link. 
2. Select Vendor on **Purchase Invoice** header, GST vendor type should be **Unregistered**.
3. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase and **Charge (Item)** for Item Charge on **Purchase Invoice** line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** should be selected on the Item or G/L Account. 
4. GST Credit option can be changed on invoice line.

For example, invoice will be issued for INR 10,000 on which 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction), has to be charged.

- GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|

- GL Entries for Intra-State purchase of goods and services from an unregistered vendor where input tax credit is available (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Service Account**|10000|  
    |**SGST/UTGST Receivable (Interim) Account**|900|
    |**CGST Receivable (Interim) Account**|900|
    |**SGST/UTGST Payable (Interim) Account**|-900|
    |**CGST Payable (Interim) Account**|-900|
    |**Vendor Account**|-10000|

- GL Entries for Intra-State purchase of goods and services from an unregistered vendor where input tax credit is not available (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase or Services Account**|11800|  
    |**SGST/UTGST Payable Account**|-900|
    |**CGST Payable Account**|-900|
    |**Vendor Account**|-10000|

- GL Entries for purchase of goods and services from an unregistered vendor with reverse charge exempt, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase or Services Account**|10000|  
    |**Vendor Account**|-10000|

- GL Entries for Intra-State purchase of fixed asset from an unregistered vendor where input tax credit is available (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Fixed Asset Increases during the Year**|10000|
    |**SGST Receivable Account (Interim)**|900|
    |**CGST Receivable Account (Interim)**|900|
    |**SGST Payable Account (Interim)**|-900|
    |**CGST Payable Account (Interim)**|-900|
    |**Vendor**|10000|

- GL Entries for Intra-State purchase of fixed asset from an unregistered vendor where input tax credit is not available (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Fixed Asset Increases during the Year**|11800|
    |**SGST Payable Account (Interim)**|-900|
    |**CGST Payable Account (Interim)**|-900|
    |**Vendor**|10000|

- GL Entries for Item Charge in case of Intra-State purchase of fixed asset from an unregistered vendor where input tax credit is available (reverse charge), will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------| 
    |**Purchase Account**|10000|
    |**SGST Receivable Account (Interim)**|900|
    |**CGST Receivable Account (Interim)**|900|
    |**SGST Payable Account (Interim)**|-900|
    |**CGST Payable Account (Interim)**|-900|
    |**Vendor**|10000|

- GL Entries for Item Charge in case of Intra-State purchase of fixed asset from an unregistered vendor where input tax credit is not available (reverse charge),will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------| 
    |**Purchase Account**|10000|
    |**SGST Payable Account (Interim)**|-900|
    |**CGST Payable Account (Interim)**|-900|
    |**Vendor**|10000|






## Related information 
[Purchase from SEZ Vendor](GST-Purchase-from-SEZ-Vendor.md)


































[!INCLUDE[footer-include](../../includes/footer-banner.md)]
