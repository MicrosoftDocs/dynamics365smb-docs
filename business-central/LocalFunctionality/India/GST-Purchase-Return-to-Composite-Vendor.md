---
title: Purchase Return of Goods and Services to Composite Vendor or Purchase Return of exempted goods and services with no GST Impact
description: Purchase Return of Goods and Services to Composite Vendor or Purchase Return of exempted goods and services with no GST Impact
author: v-debapd 
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, composite vendor, purchase return 
ms.date: 23/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Purchase return of goods and services to composite vendor or purchase return of exempted goods and services with no GST impact

A composite vendor is a vendor whose aggregate turnover in a financial year doesn't exceed 50 lakh rupees and has opted for composition scheme. A composite vendor neither collects tax from the recipient of supplies nor passes on any credit of Input Tax. Hence, no GST is computed if the purchases are made from a composite vendor. 

A composite vendor has to register himself with the GST authorities and hence registration no. is mandatory on the vendor card, if the vendor Type is selected as Composite. State Code is also mandatory. No GST entries are generated for a composite vendor, as a composite vendor isn't entitled to collect any tax from the customers. 

A buyer may have to return the goods or issue credit note due to various reasons like damaged goods, quality issues etc.

Process for purchase returns to a composite vendor has been explained in this document.

## Create a purchase return order or credit memo

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Purchase Return Order or Credit Memo**, and then choose the related link.
1. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Composite** or **Exempted**.
1. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase and **Charge (Item)** for Item Charge on **Purchase Credit Memo** line. 

For example, Purchase Return Order or Credit Memo has been issued for INR 10000 on which no GST is charged.

GL Entries are as following:

|Particulars|Amount|
|----------------------------------|---------------------------------------|
|**Vendor Account**|10000|
|**Purchase or Services or Fixed Asset increase during the year Account**|-10000|

## Related information

[Purchase Return to Registered Vendor](GST-Purchase-Return-to-Registered-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
