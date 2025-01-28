---
author: brentholtorf
ms.topic: include
ms.date: 03/04/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
If your company operates in more than one country or region, it's probably important that you can do business in more than one currency. You define your local currency (LCY) on the **General Ledger Setup** page. Afterward, your local currency will be represented as a blank currency on documents and transactions. When the **Currency** field is blank, the currency is LCY.

The following video explains how to set up your local currency.

> [!VIDEO https://learn-video.azurefd.net/vod/player?id=d1008bb9-c45d-439a-8ce7-f30f5f655f42]

Next, you must set up currency codes for each currency that you use if you buy or sell in currencies other than your local currency (LCY). Also bank accounts can be created using currencies. It is possible to record G/L transactions in different currencies, however, the G/L transaction will always be posted in the local currency (LCY).

[!INCLUDE [finance-currencies-lcy](finance-currencies-lcy-note.md)]

Your general ledger is set up to use your local currency (LCY), but you can set it up to also use another currency with a currency exchange rate assigned. By designating a second currency as an additional reporting currency, [!INCLUDE[prod_short](prod_short.md)] automatically records amounts in both LCY and the additional reporting currency on G/L entry and other entries, such as VAT entries. For more information, see [Set Up an Additional Reporting Currency](../finance-how-setup-additional-currencies.md). The additional reporting currency is most often used to facilitate financial reporting to owners that reside in countries/regions using different currencies than the local currency (LCY).  

> [!IMPORTANT]
> If you want to use an additional reporting currency for financial reporting, make sure that you understand the limitations. For more information, see [Set Up an Additional Reporting Currency](../finance-how-setup-additional-currencies.md).

> [!NOTE]  
> When you post to the general ledger using a foreign currency, [!INCLUDE [prod_short](prod_short.md)] converts the transaction to LCY using the currency exchange rate for the posting date. The G/L entry won't contain information about which currency was used, only its value in LCY. To keep track of the original currency, use the sales and purchase documents and bank accounts that store currency information for entries.
