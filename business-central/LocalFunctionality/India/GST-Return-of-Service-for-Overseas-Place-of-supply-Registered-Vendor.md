---
title: Purchase Return of Services for Overseas Place of Supply to Registered Vendor
description: Process service purchase returns to registered vendors with an overseas place of supply and review GST entries in Business Central for India.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, registered vendor, purchase return of services, overseas place of supply
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Purchase return of services for overseas place of supply to registered vendor

The supply of goods or services or both when the supplier is located in India and the place of supply is outside India shall be treated to be a supply of goods or services or both in the course of inter-state trade or commerce.

The process of computing tax on purchase return to a vendor with overseas place of supply has been explained in this document.

## Create a purchase return order or purchase credit memo

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Return Orders** or **Purchase Credit Memos**, and then choose the related link.
1. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Registered**.
1. In **Tax Information**, check that **GST Invoice** is selected and select **POS Out Of India**. Leave **POS as Vendor State** cleared.
1. Select **G/L Account** on the credit memo line. Check **GST Group Code** and **HSN/SAC Code**. Set **GST Credit** to **Availment** or **Non-Availment** to match the transaction being returned.
1. GST Credit option can be changed on **Purchase Credit Memo** line.

For example, the service recipient and registered vendor both have GSTINs in West Bengal, but the place of supply is outside India. Selecting **POS Out Of India** sets the GST jurisdiction to interstate. The following return example uses a value of INR 10,000 and an illustrative IGST rate of 18%.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

- GL Entries for Return or Credit Note of services for overseas place of supply from registered vendor where input tax credit is available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|-10000|
    |**IGST Receivable Account**|-1800|  
    |**Vendor Account**|11800|

- GL Entries for Return or Credit Note of services for overseas place of supply from registered vendor where input tax credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|-11800|  
    |**Vendor Account**|11800|

## Related information

[GST Overview](GST-001-Basic-Setup.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
