---
title:  Czech Local Functionality Check of Posting Group changing – Customer, Vendor, item, bank account
description: The following topics describe the local functionality Check of Posting Group changing – Customer, Vendor, item, bank account in the Czech version of Business Central.
author: v-pejano

ms-service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 12/01/2020
ms.reviewer: v-pejano
ms.author: v-pejano
---

# Check of Posting Group changing – Customer, Vendor, item, bank account

The standard functionality has been extended with checks in case of a request to change posting groups for customer, vendor, item and bank account cards.

- On the Customer Card, the customer's posting group can be changed if there are no open customer entries.
- On the Vendor Card, you can change the vendor posting group if there are no open vendor entries.
- On the Item Card, you can change the item posting group if there are no open item entries and at the same time there are no uninvoiced closed item entries.
- On the Bank Account Card, you can change the posting group of the bank account if the Balance or Balance (LCY) is non-zero.

## See Also

[Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)  
