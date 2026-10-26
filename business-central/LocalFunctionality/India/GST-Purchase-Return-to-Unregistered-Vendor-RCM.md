---
title: Purchase Return to Unregistered Vendor (Reverse Charge)
description: Process purchase returns to unregistered vendors under GST reverse charge and review illustrative accounting entries in Business Central for India.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, purchase return, unregistered vendor, reverse charge
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Purchase return to unregistered vendor (reverse charge)

Persons whose aggregate turnover in a financial year doesn't exceed 40 lakh rupees aren't required to be registered with the GST authorities. Such persons are called unregistered vendors. Any purchases from unregistered vendors don't attract GST. However, there are some notified services under GST, on supply of such services GST is applicable under reverse charge, that is, the purchasers are required to  pay GST to the Government.

A buyer may have to return the goods or issue credit note due to various reasons like damaged goods, quality issues etc.

Process for purchase returns to unregistered vendor has been explained in this document.

> [!NOTE]
> The turnover threshold and statutory background above describe the original scenario. Confirm current tax requirements separately. The rates and amounts below are examples.

## Create a purchase return order or credit memo

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Return Orders** or **Purchase Credit Memos**, and then choose the related link.
1. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Unregistered**.
1. Select **Item** for goods, **G/L Account** for services, **Fixed Asset**, or **Charge (Item)** on the credit memo line. Check **GST Group Code** and **HSN/SAC Code**. Set **GST Credit** to **Availment** or **Non-Availment** to match the transaction being returned.

For an **Unregistered** vendor, purchase line validation sets **GST Reverse Charge**. Review the line's GST group and exemption treatment against the original purchase. An exempt return shouldn't be treated as taxable solely because the vendor is unregistered.

For example, purchase credit memo or return order is issued for INR 10,000 on which 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction), has to be charged.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**IGST**|1800|

- GL Entries for Intra-State or Intra-Union Territory purchase return of goods, services, fixed asset, charge item to unregistered vendor where input tax credit is available (reverse charge),  are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account**|10000| 
    |**CGST Payable Account**|900|
    |**SGST/UTGST Payable Account**|900|
    |**CGST Receivable Account**|-900|
    |**SGST/UTGST Receivable Account**|-900|
    |**Purchase or Services Account or Fixed Asset increase during the year**|-10000|

- GL Entries for Intra-State or Intra-Union Territory purchase return of goods, services, fixed asset, charge item to unregistered vendor where input tax credit isn't available (reverse charge) are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account**|10000|
    |**CGST Payable Account**|900|
    |**SGST/UTGST Payable Account**|900|
    |**Purchase or Service Account or Fixed Asset increase during the year**|-11800|

## Related information

[Purchase Return to Foreign Vendor](GST-Purchase-Return-to-Foreign-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
