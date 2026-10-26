---
title: Purchase from Composite Vendor or Purchase of Exempted Goods and Services with No GST Impact
description: Explains how to record purchases from composite vendors or for exempted goods and services that have no GST impact in Business Central India localization.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, composite vendor, exempted goods and services
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Purchase from composite vendor or purchase of exempted goods and services with no GST impact

A composite vendor is a vendor whose aggregate turnover in a financial year doesn't exceed 50 lakh rupees and opted for composition scheme. A composite vendor neither collects tax from the recipient of supplies nor passes on any credit of input tax. Hence, no GST is computed if the purchases are made from a composite vendor. 

On the vendor card, set **GST Vendor Type** to **Composite**. Business Central requires either **GST Registration No.** or **ARN No.** for this vendor type. When you enter a GST registration number, also specify **State Code** and the required PAN details. The composite vendor purchase scenario doesn't calculate GST.

Process for purchases from a composite vendor has been explained in this document.

> [!NOTE]
> The turnover threshold above is historical background, not current eligibility guidance. Confirm the vendor's current GST classification before selecting **GST Vendor Type**.

## Create a purchase invoice

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Invoices**, and then choose the related link.
1. Select **Vendor** on **Purchase Invoice** header, GST vendor type should be **Composite** or **Exempted**.
1. Select **G/L Account**, **Item Code**, **Fixed Asset**, or **Charge (Item)** on **Purchase Invoice** line.
1. Check **Exempted** on the line when the goods or services are exempt. For a vendor with **GST Vendor Type** set to **Exempted**, the line validation requires this field to be selected.

Line GST details are copied from the selected item, G/L account, fixed asset, or item charge. A purchase from a composite vendor and an exempt line from a registered vendor are different scenarios. For the latter, keep the vendor's **GST Vendor Type** as **Registered** and check the line's **Exempted** value.

For example, invoice is issued for INR 10000 on which there's no GST is charged.

GL Entries are as following:

 |Particulars|Amount|
 |----------------------------------|---------------------------------------|  
 |**Purchase or Services Account**|10000|  
 |**Vendor Account**|-10000|

## Related information

[Purchase from Registered Vendor](GST-Purchase-from-Registered-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
