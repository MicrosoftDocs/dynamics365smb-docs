---
title: Purchase of Services for Overseas Place of Supply from Registered Vendor
description: Process service purchases from registered vendors with an overseas place of supply and review GST accounting entries in Business Central for India.
author: v-debapd   
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, service purchase, registered vendor, overseas place of supply
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Purchase of services for overseas place of supply from registered vendor

The supply of goods or services or both when the supplier is located in India and the place of supply is outside India shall be treated to be a supply of goods or services or both in the course of inter-state trade or commerce.

The process of computing tax on purchase from vendor with overseas place of supply has been explained in this document.

## Create a purchase invoice

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Invoices**, and then choose the related link.
1. Select **Vendor** on **Purchase Invoice** header, GST vendor type should be **Registered**.
1. In **Tax Information**, check that **GST Invoice** is selected and select **POS Out Of India**. Leave **POS as Vendor State** cleared.
1. Select **G/L Account** on the invoice line. Check **GST Group Code** and **HSN/SAC Code**. Set **GST Credit** to **Availment** or **Non-Availment**, as appropriate.
1. GST Credit option can be changed on **Purchase Invoice** line.

For example, the service recipient and registered vendor both have GSTINs in West Bengal, but the place of supply is outside India. Selecting **POS Out Of India** sets the GST jurisdiction to interstate. The following example uses an invoice value of INR 10,000 and an illustrative IGST rate of 18%.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|

- GL Entries for purchase of services for overseas place of supply from registered vendor where input tax credit is available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|10000|
    |**IGST Receivable Account**|1800|  
    |**Vendor Account**|-11800|

- GL Entries for purchase of services for overseas place of supply from registered vendor where input tax credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|11800|
    |**Vendor Account**|-11800|

## Related information

[GST and TDS on Purchase Transaction](GST-TDS-and-GST-on-Purchase.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
