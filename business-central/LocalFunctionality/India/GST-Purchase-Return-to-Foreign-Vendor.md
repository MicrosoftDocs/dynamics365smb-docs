---
title: Purchase Credit Memo or Return Order to Foreign Vendor
description: Purchase Credit Memo or Return Order to Foreign Vendor

author: v-debapd

    
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Purchase Credit Memo or Return Order to Foreign Vendor


Purchasing goods in India from a place outside India is import of goods. For services, if the supplier is located outside India, the recipient is located in India and the place of supply is in India, then it is called Import of services. Purchase of goods and/or services from a foreign vendor are subject to reverse charge i.e. the person importing goods or services is required to remit tax to the Government.

A buyer may have to return the goods or issue credit note due to various reasons like damaged goods, quality issues etc.

Process for purchase returns to foreign vendor has been explained in this document.

## Create a purchase return order or credit memo

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Return Order or Credit Memo**, and then choose the related link. 
2. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Import**.
3. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase on **Purchase Credit Memo** line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** on the Item, G/L Account, Fixed Asset.
4. GST Credit option can be changed on **Purchase Credit Memo** line.

- Purchase Credit Memo or Return Order for Imported Goods or Fixed asset, IGST is to be calculated on GST Assessable Value + Basic Custom Duty. 

For example, purchase credit memo or return order is issued for INR 10000, Custom Duty INR 1000, GST Assessable Value INR 11000 (IGST @18%) has to be charged. Calculation base:  (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%).

  - GST calculation will appear in the Fact Box, as following:
    
      |Component|Amount|
      |----------------------------------|---------------------------------------|  
      |**GST Base Amount**|11,000|
      |**Custom Duty (BCD)**|1000|  
      |**IGST**|2160|
    
  - GL Entries for purchase credit memo or return order for imported goods or fixed asset where input tax credit is available, will be as following:

      |Particulars|Amount|
      |----------------------------------|---------------------------------------|
      |**Vendor Account (Transactional Value)**|10000|
      |**IGST Refund Account**|2160|
      |**IGST Receivable Account**|-2160|
      |**Purchase Account or Fixed Asset increase during the year (Transactional Value)**|-10000|

  - GL Entries for purchase credit memo or return order for imported goods or fixed asset where input tax credit is not available, will be as following:

     |Particulars|Amount|
     |----------------------------------|---------------------------------------|
     |**Vendor Account (Transactional Value)**|10000|
     |**IGST Refund Account**|2160| 
     |**Purchase Account or Fixed Asset increase during the year (Transactional Value)**|-12160|















## Related information 
[Purchase Return to Vendor with Overseas Place of Supply](GST-Return-of-Service-for-Overseas-Place-of-supply-Registered-Vendor.md)

























[!INCLUDE[footer-include](../../includes/footer-banner.md)]
