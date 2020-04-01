---
title: Adjust exchange rates in Russia
description: Russian enhancements include exchange rates adjustments.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Adjust Exchange Rates

The difference for Russian task and worldwide task - Russian report create adjustment entry for every Vendor and Customer entry and uses posting group from entry not from Vendor and Customer card.

1. Go to **Adjust Exchange Rates**.

2.  Fill the fields:

   | Field                                           | Description                                                  |
   | ----------------------------------------------- | ------------------------------------------------------------ |
   | Starting Date                                   | Specifies the beginning of the period for which entries are adjusted.This field is usually left blank, but you can enter a date. |
   | Ending Date                                     | Specifies the date to which the report or batch job processes information. |
   | Posting Description                             | Specifies text for the general ledger entries that are created by the batch job. The default text is Exchange Rate Adjmt. of %1 %2, in which %1 is replaced by the currency code and %2 is replaced by the currency amount that is adjusted. For example, Exchange Rate Adjmt. of DEM 38,000. |
   | Posting Date                                    | Specifies the posting date of the entries that you want to include in the report or batch job. |
   | Document No.                                    | Specifies the document number that will appear on the general ledger entries that are created by the batch job. |
   | Adjust G/L Accounts for Add.-Reporting Currency | Specifies if you want to post in an additional reporting currency and adjust general ledger accounts for currency fluctuations between LCY and the additional reporting currency. |
   | Adjust Bank Accounts                            | Specifies if you want to adjust                              |
   | Adjust Customer                                 | Specifies if you want to adjust customer entries             |
   | Adjust Vendor                                   | Specifies if you want to adjust vendor entries               |

   3. Click "Ok".
   
   ## See Also 

[Russia Local Functionality](russia-local-functionality.md)
