---
    title: Purchase Credit Memo/Return Order to Foreign Vendor
    description: Purchase Credit Memo/Return Order to Foreign Vendor

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
# Purchase Credit Memo/Return Order to Foreign Vendor

## Create a Purchase Return Order/Credit Memo

1. Choose the ![img](image/search.jpg)icon, enter **Purchase Return Order/Credit Memo**, and then choose the related link. 
2. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Import**.
3. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase on **Purchase Credit Memo** line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** on the Item, G/L Account, Fixed Asset.
4. GST Credit option can be changed on **Purchase Credit Memo** line.

- Purchase Credit Memo/Return Order for Imported Goods/ Fixed asset, IGST is to be calculated on GST Assessable Value + Basic Custom Duty. For example: Purchase credit memo/ return order will be issued for INR 10000, Custom Duty INR 1000, GST Assessable Value INR 11000 (IGST @18%) will be charged. Calculation base:  (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%)

1. GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|11,000|
    |**Custom Duty (BCD)**|1000|  
    |**IGST**|2160|
    
2. GL Entries for purchase credit memo/return order for imported goods/ fixed asset where input tax credit is available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account (Transactional Value)**|10000|
    |**IGST Refund Account**|2160|
    |**IGST Receivable Account**|-2160|
    |**Purchase Account/Fixed Asset increase during the year (Transactional Value)**|-10000|

3. GL Entries for purchase credit memo/return order for imported goods/fixed asset where input tax credit is not available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account (Transactional Value)**|10000|
    |**IGST Refund Account**|2160| 
    |**Purchase Account/Fixed Asset increase during the year (Transactional Value)**|-12160|

> [!NOTE]
>
> All relevant GST attributes are stored along with the GST transactions for GST Settlement and generating GST returns for government authorities.





































