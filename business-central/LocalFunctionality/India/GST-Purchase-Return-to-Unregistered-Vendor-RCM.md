---
    title: Purchase Return to Unregistered Vendor (Reverse Charge)
    description: Purchase Return to Unregistered Vendor (Reverse Charge)

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
# Purchase Return to Unregistered Vendor (Reverse Charge)

## Create a Purchase Return Order or Credit Memo

1. Choose the ![img](image/search.jpg)icon, enter **Purchase Return Order or Credit Memo**, and then choose the related link. 
2. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Unregistered**.
3. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase and **Charge (Item)** for Item Charge on **Purchase Credit Memo** line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** on the Item, G/L Account, Fixed Asset, Item (Charge). For example, purchase credit memo/ return order will be issued for INR 10,000 on which 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction), will be charged.
6. GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|

6. GL Entries for Intra-State or Intra-Union Territory purchase return of goods, services, fixed asset, charge item to unregistered vendor where input tax credit is available (reverse charge), will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account**|10000| 
    |**CGST Payable Account**|900|
    |**SGST/UTGST Payable Account**|900|
    |**CGST Receivable Account**|-900|
    |**SGST/UTGST Receivable Account**|-900|
    |**Purchase or Services Account or Fixed Asset increase during the year**|-10000|

7. GL Entries for Intra-State or Intra-Union Territory purchase return of goods, services, fixed asset, charge item to unregistered vendor where input tax credit is not available (reverse charge), will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account**|10000|
    |**CGST Payable Account**|900|
    |**SGST/UTGST Payable Account**|900|
    |**Purchase or Service Account or Fixed Asset increase during the year**|-11800|







































