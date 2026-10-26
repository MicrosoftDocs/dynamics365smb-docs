---
title: Set Up Gate Entry Tracking
description: Specifies basic setups required to keep track of entrance and exit of materials or other entities, to and from the organization’s premises.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, gate entry tracking, gate entry setup, gate entry types
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Set up gate entry tracking

A process in any organization, used to keep track of entrance and exit of materials or other entities, to and from the organization’s premises, is termed as Gate Entry.

This functionality provides the facility to keep the record of the gate entries (Inward/Outward) of the goods and also helps in relating these entries with the Purchase Order / Transfer Order / Sales Order / Return Orders.

Gate entries record the physical movement of goods and support an audit trail. Posting a gate entry creates a posted gate entry record; it doesn't post the source purchase, sales, or transfer document.

## Types of gate entries

- Inward Gate Entry provides the facility to create Inward Gate Entry against:
  - Purchase Order / Purchase Invoice
  - Transfer Receipt
  - Sales Return Order / Sales credit Memo

- Outward gate entries reference posted outbound documents:
  - Sales shipments
  - Transfer shipments
  - Purchase return shipments

## Required setup

- Inventory Setup
- Posting No. Series Setup

## Set up no. series for gate entry in inventory setup

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Inventory Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Inward Gate Entry Nos.**|Specifies the no. series code to assign Inward gate entry.|
    |**Outward Gate Entry Nos.**|Specifies the no. series code to assign Outward gate entry.|

## Set up posting no. series for gate entry in posting no. series setup

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Posting No. Series Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Document Type**|Select **Gate Entry**.|
    |**Condition**|Set filters for the gate entry header, such as **Entry Type** and **Location Code**.|
    |**Posting No. Series**|Choose the posted number series from the lookup list.| 

## Related information

[Gate Entry Inward Transaction](Gate-Entry-Inward_Transactions.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
