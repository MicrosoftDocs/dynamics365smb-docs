---
author: brentholtorf
ms.topic: include
ms.date: 03/15/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
> [!Important]
> Do not create the local currency code both in the **General Ledger Setup** and in the **Currencies** page. This will create confusion between the blank currency and the LCY code in the currency table, and bank accounts, customers or vendors might accidentally be created, some with the blank currency and some with the LCY code.