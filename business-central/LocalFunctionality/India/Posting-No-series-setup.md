---
title: Setting Up Posting Number Series
description: Set up conditional posting number series for sales, purchase, transfer, and gate entry documents in the India localization of Business Central.
author: v-debapd  
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, posting number series, document numbering, transfers
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Setting up posting number series

[!INCLUDE[vnext_preview](../../includes/vnext_preview.md)]

## Overview

Business Central includes conditional posting number series for the Indian localization.

Posting No. series functionality enables you to maintain the different number series of below sales, purchase, and transfer orders for different locations.

- Purchase Receipt
- Purchase Invoice
- Sales Shipment
- Sales Invoice
- Purchase Credit Memo
- Sales Return Receipt
- Sales Credit Memo
- Purchase Return Shipment
- Transfer Shipment
- Transfer Receipt
- GST Distribution
- Service Transfer Shipment
- Service Transfer Receipt
- Gate Entry

Following comprehensive functionalities are covered under Posting No. Series:

- Provision to define different number series for different types of sales and purchase documents for different Locations.
- After posting of sales and purchase documents, the program will store the number series assigned in Posting No. Series page for specified filters.
- Provision to define separate number series in sales and purchase documents in case of trading activity.
- Provision to define separate number series for the locations used in transfer orders.

## Steps to set up posting number series

You need to create a setup for posting of documents. The following procedure shows how to set up posting number series.
1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Posting No. Series Setup**, and then choose the related link.
1. Select **New**.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |-----|:----------|
    |**Document Type**|Specify the number series for Purchase, Sales & Transfer documents. |
    |**Condition**|Specifies the filters for type of record selected in the Document Type. For example, if Document Type is Posted Sales Invoice and Condition is Location Code as BLUE, then system updates the document number of posted sales invoices for BLUE location with code specified in the Posting No. series field. |
    |**Posting No. Series**|Specifies the number series for the document type and filters.|

> [!NOTE]
> The first matching setup record supplies the posting number series. An empty condition matches any record of that document type. Avoid overlapping conditions so that the intended series is used.

## Related information

[Set up gate entry tracking](Gate-Entry-001-Basic-Setup.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
