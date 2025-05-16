---
title: Purchase Return to Unregistered Vendor (Reverse Charge)
description: Purchase Return to Unregistered Vendor (Reverse Charge)

author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Purchase Return to Unregistered Vendor (Reverse Charge)


Persons whose aggregate turnover in a financial year does not exceed forty lakh rupees are not required to be registered with the GST authorities. Such persons are called unregistered vendors. Any purchases from unregistered vendors do not attract GST. However, there are some notified services under GST, on supply of such services GST is applicable under reverse charge i.e. the purchasers are required to  pay GST to the Government.

A buyer may have to return the goods or issue credit note due to various reasons like damaged goods, quality issues etc.

Process for purchase returns to unregistered vendor has been explained in this document.


## Create a purchase return order or credit memo

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Return Order** or **Purchase Credit Memo**, and then choose the related link. 
2. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Unregistered**.
3. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase and **Charge (Item)** for Item Charge on **Purchase Credit Memo** line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** on the Item, G/L Account, Fixed Asset, Item (Charge). 

For example, purchase credit memo or return order is issued for INR 10,000 on which 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction), has to be charged.

- GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|

- GL Entries for Intra-State or Intra-Union Territory purchase return of goods, services, fixed asset, charge item to unregistered vendor where input tax credit is available (reverse charge), will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account**|10000| 
    |**CGST Payable Account**|900|
    |**SGST/UTGST Payable Account**|900|
    |**CGST Receivable Account**|-900|
    |**SGST/UTGST Receivable Account**|-900|
    |**Purchase or Services Account or Fixed Asset increase during the year**|-10000|

- GL Entries for Intra-State or Intra-Union Territory purchase return of goods, services, fixed asset, charge item to unregistered vendor where input tax credit is not available (reverse charge), will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account**|10000|
    |**CGST Payable Account**|900|
    |**SGST/UTGST Payable Account**|900|
    |**Purchase or Service Account or Fixed Asset increase during the year**|-11800|


















## Related information 
[Purchase Return to Foreign Vendor](GST-Purchase-Return-to-Foreign-Vendor.md)






















[!INCLUDE[footer-include](../../includes/footer-banner.md)]
