---
title: Additional Fields on Item Ledger Entries and Value Entries [CZ]
description: Learn about the additional fields available on item ledger entries and value entries in the Czech version of Business Central.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Additional fields on item ledger entries and value entries in the Czech version

Item ledger entries and value entries include extra fields so Czech companies can track more information about the source of each transaction. These fields are automatically filled in when the entries are posted:

- **Invoice-to Source No.**: The customer or vendor number the transaction is invoiced to.
- **Delivery-to Source No.**: The ship-to address (for customers) or order address (for vendors) the transaction is delivered to.
- **Source Code**: The source code that identifies the journal or process that created the entry.
- **Reason Code**: The reason code assigned to the transaction, if any.
- **Currency Code**: The currency used for the transaction.
- **Currency Factor**: The currency exchange factor used for the transaction.

The **Source Code** and **Reason Code** fields are available only on item ledger entries. The other fields are available on both item ledger entries and value entries.

## Related information

- [Advanced Localization Pack for Czech](ui-extensions-advanced-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
