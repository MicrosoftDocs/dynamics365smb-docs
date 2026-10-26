---
title: Purchase Credit Memo or Return Order to Foreign Vendor
description: Learn how to create a purchase credit memo or return order to a foreign vendor in India, including GST and reverse charge considerations.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, purchase credit memo, foreign vendor
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Purchase credit memo or return order to foreign vendor

Purchasing goods in India from a place outside India is import of goods. For services, if the supplier is located outside India, the recipient is located in India and the place of supply is in India, then it's called Import of services. Purchase of goods and/or services from a foreign vendor are subject to reverse charge, that is, the person importing goods or services is required to remit tax to the Government.

A buyer may have to return the goods or issue credit note due to various reasons like damaged goods, quality issues etc.

Process for purchase returns to foreign vendor has been explained in this document.

> [!NOTE]
> The rates and amounts below are illustrative. Confirm current import and refund requirements separately.

## Create a purchase return order or credit memo

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Return Orders** or **Purchase Credit Memos**, and then choose the related link.
1. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Import**.
1. Select **Item** for goods, **G/L Account** for services, or **Fixed Asset** on the credit memo line. Check **GST Group Code** and **HSN/SAC Code**. Set **GST Credit** to **Availment** or **Non-Availment** to match the transaction being returned.
1. GST Credit option can be changed on **Purchase Credit Memo** line.

The purchase return validation requires **GST Assessable Value** and **Custom Duty Amount** to be zero on credit memo and return order lines. Don't enter the original invoice's customs values directly in these fields on the return.

The following historical posting example uses an original purchase with a transaction value of INR 10,000, customs duty of INR 1,000, and a GST assessable value of INR 11,000. At the example rate of 18%, GST on the original INR 12,000 calculation base is INR 2,160. These values explain the original tax amount, not values to enter in the return's customs fields.

- The tax amount in this example comes from the original purchase:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Original GST Assessable Value**|11,000|
    |**Original Custom Duty (BCD)**|1000|
    |**Original GST Base Amount**|12,000|
    |**Original IGST**|2160|

- GL Entries for purchase credit memo or return order for imported goods or fixed asset where input tax credit is available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account (Transactional Value)**|10000|
    |**IGST Refund Account**|2160|
    |**IGST Receivable Account**|-2160|
    |**Purchase Account or Fixed Asset increase during the year (Transactional Value)**|-10000|

- GL Entries for purchase credit memo or return order for imported goods or fixed asset where input tax credit isn't available are as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account (Transactional Value)**|10000|
    |**IGST Refund Account**|2160|
    |**Purchase Account or Fixed Asset increase during the year (Transactional Value)**|-12160|

## Related information

[Purchase Return to Vendor with Overseas Place of Supply](GST-Return-of-Service-for-Overseas-Place-of-supply-Registered-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
