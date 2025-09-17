---
title: Adjust exchange rates in Russia
description: Russian localization adds detailed exchange rate adjustment features for vendors and customers.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: adjust exchange rates, exchange rate adjustment, Russia
ms.date: 07/11/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Adjust exchange rates in the Russian version

The difference for Russian task and worldwide task - Russian report create adjustment entry for every Vendor and Customer entry and uses posting group from entry not from Vendor and Customer card.

1. Go to **Adjust Exchange Rates**.
1. Fill the fields:

   | Field | Description |
   |--|--|
   | Starting Date | Specifies the beginning of the period for which entries are adjusted. This field is usually left blank, but you can enter a date. |
   | Ending Date | Specifies the date to which the report or batch job processes information. |
   | Posting Description | Specifies text for the general ledger entries that are created by the batch job. The default text is Exchange Rate Adjmt. of %1 %2, in which %1 is replaced by the currency code and %2 is replaced by the currency amount that is adjusted. For example, Exchange Rate Adjmt. of DEM 38,000. |
   | Posting Date | Specifies the posting date of the entries that you want to include in the report or batch job. |
   | Document No. | Specifies the document number that appears on the general ledger entries that are created by the batch job. |
   | Adjust G/L Accounts for Add.-Reporting Currency | Specifies if you want to post in an additional reporting currency and adjust general ledger accounts for currency fluctuations between LCY and the additional reporting currency. |
   | Adjust Bank Accounts | Specifies if you want to adjust |
   | Adjust Customer | Specifies if you want to adjust customer entries |
   | Adjust Vendor | Specifies if you want to adjust vendor entries |

1. Select **Ok**.

## Related information

[Russia Local Functionality](russia-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
