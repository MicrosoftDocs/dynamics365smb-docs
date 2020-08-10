---
    title: Purchase Return to Registered Vendor
    description: Purchase Return to Registered Vendor
    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 06/16/2020
    ms.author: v-debapd
---
# Purchase Return to Registered Vendor

## Create a Purchase Return Order or Credit Memo

1.  Choose the ![img](image/search.jpg)icon, enter **Purchase Return Order or Credit Memo**, and then choose the related link. 
2. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Registered**.
3. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase and **Charge (Item)** for Item Charge on **Purchase Credit Memo** line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** on the Item, G/L Account, Fixed Asset, Charge (Item). For example, purchase credit memo or return order will be issued for INR 10000 on which 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction), will be charged.
6. GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800| 

6. GL Entries for Intra-State or Intra-Union Territory purchase return of goods, service, fixed asset and item charge to registered vendor where input tax credit is available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account**|11800|
    |**SGST/UTGST Receivable Account**|-900|
    |**CGST Receivable Account**|-900|
    |**Purchase or Service Account or Fixed Asset increase during the year**|-10000|

7. GL Entries for Intra-State or Intra-Union Territory purchase return of goods, service, fixed asset and item charge to registered vendor where input tax credit is not available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account**|11800|
    |**Purchase or Service Account or Fixed Asset increase during the year**|-11800|


8. GL Entries for Inter-State purchase return of goods, services, fixed asset, charge item to registered vendor where input tax credit is available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|    
    |**Vendor Account**|11800| 
    |**IGST Receivable Account**|-1800| 
    |**Purchase or Services Account or Fixed Asset increase during the year**|-10000|

9. GL Entries for Inter-State purchase return of goods, services, fixed asset, charge item to registered vendor where input tax credit is not available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account**|11800| 
    |**Purchase or Services Account or Fixed Asset increase during the year**|-11800|








































