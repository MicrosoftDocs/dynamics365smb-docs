---
title: Stock Transfer
description: Learn how to process stock transfers under GST in India, including steps for transfer orders, GST calculation, and handling bonded warehouse scenarios.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, stock transfer
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Stock transfer

Stock transfers between ordinary locations, branches, or divisions with different GST registration numbers can generate GST. For locations in the same state with different registration numbers, the calculation uses CGST and SGST/UTGST. Transfers between states use IGST. For ordinary locations with the same registration number, GST isn't calculated. Bonded warehouse transfers have separate requirements, described later in this article.

## Create a transfer order

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Transfer Orders**, and then choose the related link.
1. Select **Transfer-from Code** and **Transfer-to Code** on **Transfer Order** header.  State Code and GST registration number should be filled on the location master.
1. Select **Item** on **Transfer Order** line. GST Group Code, HSN/SAC Code should be filled on **Item**.

For example, inventory for INR 1000 is being transferred from one location to another and 18% GST (9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) has to be charged on INR 1000.

The rates illustrate the example. Use CGST and SGST for the intrastate case, or IGST for the interstate case—not all three components together.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|1000|  
    |**IGST**|180|
    |**CGST**|90|
    |**SGST**|90|

Post the transfer shipment, and then post the receipt. The following tables show the example entries for each stage.

- GL Entries for shipment transaction in case of Interstate stock transfer are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Unrealized Profit Account**|180|
    |**IGST Payable Account**|-180|
    |**Inventory Adjustment Account**|1000|
    |**Inventory Account**|-1000|

- GL Entries for receipt transaction in case of Interstate stock transfer are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**IGST Receivable Account**|180|  
    |**Unrealized Profit Account**|-180|  
    |**Inventory Account**|1000|
    |**Inventory Adjustment Account**|-1000|

- GL Entries for shipment transaction in case of Intra-State or Intra-Union Territory stock transfer are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Unrealized Profit Account**|180|  
    |**CGST Payable Account**|-90|
    |**SGST/UTGST Payable Account**|-90|  
    |**Inventory Account**|-1000|
    |**Inventory Adjustment Account**|1000|

- GL Entries for receipt transaction in case of Intra-State or Intra-Union Territory stock transfer are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Unrealized Profit Account**|-180|  
    |**CGST Receivable Account**|90|
    |**SGST/UTGST Receivable Account**|90|  
    |**Inventory Account**|1000| 
    |**Inventory Adjustment Account**|-1000|

## Stock transfer for bonded warehouse

Bonded warehouse transfer means transfer of stock from customs warehouse to company warehouse. This scenario occurs when material is stored at customs warehouse before moving it to company’s warehouse. In this case, the customs duty is paid only when material is moved from bonded warehouse.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Transfer Orders**, and then choose the related link.
1. Select **Transfer-from Code** and **Transfer-to Code** on **Transfer Order** header.
1. State Code and GST registration number should be filled on Transfer-to **Location**.
1. **Bonded warehouse** field should be marked true on Transfer-from **Location**.
1. Select **Item** on **Transfer Order** line. GST Group Code, HSN/SAC Code should be filled on **Item**.
1. Enter **GST Assessable Value** and **Custom Duty Amount** on **Transfer Order** lines. System calculates GST on GST Assessable Value and Custom Duty Amount, not on transaction line amount.
1. Enter **Bill of Entry No.**, **Bill of Entry Date**, and **Vendor No.** on the transfer order header. These fields and **GST Assessable Value** are validated when you receive the bonded warehouse transfer.

## Related information

[GST Service Transfer](GST-Service-Transfer.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
