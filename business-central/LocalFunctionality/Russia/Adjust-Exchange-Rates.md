---
title: Adjust exchange rates in Russia
description: Russian localization adds detailed exchange rate adjustment features for vendors and customers.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: adjust exchange rates, exchange rate adjustment, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Adjust exchange rates in the Russian version

When **Enable Russian Accounting** is selected in **General Ledger Setup**, exchange rate adjustment runs per entry. Customer and vendor adjustments use posting groups from the ledger entries rather than the current customer or vendor card.

1. Open **Exchange Rates Adjustment**.
1. Fill the fields:

   | Field | Description |
   |--|--|
   | Starting Date | Specifies the beginning of the period for which entries are adjusted. This field is usually left blank, but you can enter a date. |
   | Ending Date | Specifies the date to which the report or batch job processes information. |
   | Posting Description | Specifies text for the general ledger entries that are created by the batch job. The default text is Exchange Rate Adjmt. of %1 %2, in which %1 is replaced by the currency code and %2 is replaced by the currency amount that is adjusted. For example, Exchange Rate Adjmt. of DEM 38,000. |
   | Posting Date | Specifies the posting date of the entries that you want to include in the report or batch job. |
   | Document No. | Specifies the document number that appears on the general ledger entries that are created by the batch job. |
   | Adjust G/L Accounts for Add.-Reporting Currency | Specifies if you want to post in an additional reporting currency and adjust general ledger accounts for currency fluctuations between LCY and the additional reporting currency. |
   | Adjust Bank Accounts | Specifies whether to adjust bank account entries. |
   | Adjust Customers | Specifies whether to adjust customer entries. |
   | Adjust Vendors | Specifies whether to adjust vendor entries. |

1. Select **OK**.

## Related information

[Russia Local Functionality](russia-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
