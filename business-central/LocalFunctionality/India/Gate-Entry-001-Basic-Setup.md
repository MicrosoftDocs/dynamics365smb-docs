---
title: Setting up Gate Entry tracking
description: Specifies Basic Setups required to keep track of entrance and exit of materials or other entities, to and from the organization’s premises.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 12/12/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Setting up Gate Entry Tracking

A process in any organization, used to keep track of entrance and exit of materials or other entities, to and from the organization’s premises, is termed as Gate Entry.

This functionality provides the facility to keep the record of the gate entries (Inward/Outward) of the goods and also helps in relating these entries with the Purchase Order / Transfer Order / Sales Order / Return Orders.

The **"Gate Entry"** system provides a physical control over the goods, which are the movable assets of the organization. Gate Entry also helps in audit trail.

### The following types of Gate Entry can be used:

 - Inward Gate Entry provides the facility to create Inward Gate Entry against:

      - Purchase Order / Purchase Invoice
      - Transfer Receipt
      - Sales Return Order / Sales credit Memo

 - Outward Gate Entry provides the facility to create Outward Gate Entry against:
     - Sales Order / Sales invoice
     - Transfer Shipment
     - Purchase Return Order / Purchase Credit Memo
 
### The following setups are required:

- Inventory Setup
- Posting No. Series Setup

## Setting up no. series for gate entry in inventory setup

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Inventory Setup**, and then choose the related link.
2. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Inward Gate Entry Nos.**|Specifies the no. series code to assign Inward gate entry.|
    |**Outward Gate Entry Nos.**|Specifies the no. series code to assign Outward gate entry.|

## Setting up posting no. series for gate entry in posting no. series setup

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Posting No. Series Setup**, and then choose the related link.
2. Fill in the fields as described in the following table.

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Entry Type**|Specify the gate entry type. The available options are Inward and Outward.|  
    |**Condition**|Choose the relevant entry type and location code from the lookup list and assign no. series for applied conditions.|  
    |**Posting No. Series**|Choose the posted number series from the lookup list.| 







## Related information 
[Gate Entry Inward Transaction](Gate-Entry-Inward_Transactions.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
