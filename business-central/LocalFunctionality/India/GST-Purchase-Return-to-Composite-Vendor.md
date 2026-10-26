---
title: Purchase Return of Goods and Services to Composite Vendor or Purchase Return of Exempted Goods and Services with No GST Impact
description: Purchase Return of Goods and Services to Composite Vendor or Purchase Return of exempted goods and services with no GST Impact
author: v-debapd 
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, composite vendor, purchase return 
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Purchase return of goods and services to composite vendor or purchase return of exempted goods and services with no GST impact

A composite vendor is a vendor whose aggregate turnover in a financial year doesn't exceed 50 lakh rupees and has opted for composition scheme. A composite vendor neither collects tax from the recipient of supplies nor passes on any credit of Input Tax. Hence, no GST is computed if the purchases are made from a composite vendor. 

On the vendor card, set **GST Vendor Type** to **Composite**. Business Central requires either **GST Registration No.** or **ARN No.** for this vendor type. When you enter a GST registration number, also specify **State Code** and the required PAN details. The composite vendor return scenario doesn't calculate GST.

A buyer may have to return the goods or issue credit note due to various reasons like damaged goods, quality issues etc.

Process for purchase returns to a composite vendor has been explained in this document.

> [!NOTE]
> The turnover threshold above is historical background, not current eligibility guidance. Confirm the vendor's current GST classification separately.

## Create a purchase return order or credit memo

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Return Orders** or **Purchase Credit Memos**, and then choose the related link.
1. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Composite** or **Exempted**.
1. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase and **Charge (Item)** for Item Charge on **Purchase Credit Memo** line. 
1. Check the line's **Exempted** value against the original purchase. A vendor with **GST Vendor Type** set to **Exempted** requires exempt lines.

For a return of exempt goods to a registered vendor, retain **Registered** as the vendor type and use the line's **Exempted** field. Don't change the vendor to **Composite** merely because the returned goods are exempt.

For example, Purchase Return Order or Credit Memo has been issued for INR 10000 on which no GST is charged.

GL Entries are as following:

|Particulars|Amount|
|----------------------------------|---------------------------------------|
|**Vendor Account**|10000|
|**Purchase or Services or Fixed Asset increase during the year Account**|-10000|

## Related information

[Purchase Return to Registered Vendor](GST-Purchase-Return-to-Registered-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
