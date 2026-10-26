---
title: Purchase of Goods from SEZ Vendor
description: Learn how to process the purchase of goods from a Special Economic Zone (SEZ) vendor in India, including GST calculation and accounting entries in Business Central.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, SEZ vendor, create purchase invoice
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Purchase of goods from SEZ vendor

A special economic zone (SEZ) is a dedicated zone wherein businesses enjoy simpler tax and easier legal compliances. The transactions with SEZ’s are deemed  exports and imports. The SEZ supply of goods can be made with cover of bill of entry or without cover of bill of entry.

Process for purchase from SEZ vendor has been explained in this document.

> [!NOTE]
> The tax rates and amounts below are illustrative. Confirm current SEZ and customs requirements separately.

## Create a purchase invoice

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Invoices**, and then choose the related link.
1. Select **Vendor** on **Purchase Invoice** header, GST vendor type should be **SEZ**.
1. Select **Item** for goods or **Fixed Asset** on the invoice line. Check **GST Group Code**, **HSN/SAC Code**, and **GST Credit**.
1. Enter **GST Assessable Value** and **Custom Duty Amount** on the goods line as applicable.
1. If the invoice is without a bill of entry, select **Without Bill Of Entry** on the header. This option is available only for **SEZ** vendors.
1. Otherwise, enter **Bill of Entry No.**, **Bill of Entry Date**, and **Bill of Entry Value** before posting.

The examples use INR 11,000 as the assessable value before adding INR 1,000 of basic customs duty. The resulting GST calculation base is INR 12,000.

For example, purchase invoice is issued for INR 10000, Custom Duty INR 1000, GST Assessable Value INR 11000 (IGST @18%), has to be charged. Calculation base: (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%)

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Assessable Value**|11,000|
    |**Custom Duty (BCD)**|1000|
    |**GST Base Amount**|12,000|
    |**IGST**|2160|  

- GL Entries for import of goods with input tax credit available from SEZ vendor with cover of Bill of Entry are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account (Transactional Value+ BCD)**|11000|  
    |**IGST Receivable Account (on GST Assessable Value + BCD)**|2160|
    |**Customs House Account (GST Amount + BCD)**|-3160|
    |**Vendor Account (Transaction Value)**|-10000|

- GL Entries for import of goods with input tax credit available from SEZ vendor without cover of Bill of Entry are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account (Transactional Value+ BCD)**|11000|  
    |**IGST Receivable Account (on GST Assessable Value + BCD)**|2160|
    |**Vendor Account (Transaction Value)**|-13160|

- GL Entries for import of goods without input tax credit available from SEZ vendor with cover of Bill of Entry are as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|13160|  
    |**Custom House Account**|-3160|
    |**Vendor Account (Transaction Value)**|-10000|

- GL Entries for import of goods without input tax credit available from SEZ vendor without cover of Bill of Entry are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase Account**|13160|  
    |**Vendor Account (Transaction Value)**|-13160|

- GL Entries for import of fixed asset with input tax credit available from SEZ vendor with cover of Bill of Entry are as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Fixed Asset Increased During the Year Account (Transactional Value+ BCD)**|11000|  
    |**IGST Receivable Account (on GST Assessable Value + BCD)**|2160| 
    |**Customs House Account (GST Amount + BCD)**|-3160|
    |**Vendor Account (Transaction Value)**|-10000|

- GL Entries for import of fixed assets with input tax credit available from SEZ vendor without cover of Bill of Entry are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Fixed Asset Increased During the Year Account  (Transactional Value+ BCD)**|11000|  
    |**IGST Receivable Account (on GST Assessable Value + BCD)**|2160| 
    |**Vendor Account (Transaction Value)**|-13160|

- GL Entries for import of fixed asset without input tax credit available from SEZ vendor with cover of Bill of Entry are as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Fixed Asset Increased During the Year Account**|13160|  
    |**Custom House Account**|-3160|
    |**Vendor Account (Transaction Value)**|-10000|

- GL Entries for import of fixed asset without input tax credit available from SEZ vendor without cover of Bill of Entry are as following:

    |Particular|Amount|
    |----------------------------------|---------------------------------------|  
    |**Fixed Asset Increased During the Year Account**|13160|  
    |**Vendor Account (Transaction Value)**|-13160|

> [!NOTE]
> The GST calculation process for SEZ vendor is same as for an Import vendor.

## Related information

[Purchase from Foreign Vendor](GST-Purchase-from-Foreign-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
