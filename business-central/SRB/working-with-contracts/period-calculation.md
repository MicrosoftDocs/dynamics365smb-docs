---
title: Period calculation
description: Learn about calculating periods in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Period calculation

**Period calculation** controls how a period is determined for invoicing. Billing for a period length of one month works smoothly with subscription billing. However, if the start of the billing period is within the last three days of a month, the length of the month and the following month are not considered.

A contract invoice issued for one month from February 28th (no leap year) ends with the standard calculation in [!INCLUDE [prod_short](../../includes/prod_short.md)] on March 27th (+ 1M - 1D). However, a recurring billing from the last day of a month should extend to the final day of the following month to represent a full month.

To accommodate this, there is a choice to calculate periods using the standard method in [!INCLUDE [prod_short](../../includes/prod_short.md)] or the subscription billing method. The period calculation with the **Align to Start of Month** option uses the standard method in [!INCLUDE [prod_short](../../includes/prod_short.md)], whereas **Align to End of Month** uses a different method.

For all recurring billings, the **Align to End of Month** is generally recommended. It can be set as a default on the **Service & Contracts Setup** page.

## Align to Start of Month​

The calculation of a month with the **Align to Start of Month** option as the period calculation in the contract line uses the standard date calculation in [!INCLUDE [prod_short](../../includes/prod_short.md)].

## Calculation of the period​

When calculating a month, the start date plus one month minus one day (CM-1D) is used to calculate the end of the period. For the calculation of two months, the start date plus two months minus one day (CM+1M-1D) is used to calculate the end of the period.


|1M - 1T   |2M - 1T   |1Q - 1T  | 1Y-1T  |
|---------|---------|---------|---------|
|28.01.24 - 27.02.24  |  28.01.24 - 27.03.24 |  28.01.24 - 27.04.24 | 28.01.24 - 27.01.25         |
|29.01.24 - 28.02.24      | 29.01.24 - 28.03.24         |  29.01.24 - 28.04.24        |   29.01.24 - 28.01.25       |
|30.01.24 - 28.02.24      |  30.01.24 - 29.03.24        |   30.01.24 - 29.04.24       |   30.01.24 - 29.01.25       |
|31.01.24 - 28.02.24      |  31.01.24 - 30.03.24        |  31.01.24 - 29.04.24        |   31.01.24 - 30.01.25       |
|29.02.24 - 28.03.24      |  29.02.24 - 28.04.24        |  29.02.24 - 28.05.24        |    29.02.24 - 27.02.25      |

## Price calculation​ 

The value of the **Billing Rhythm** field is not taken into account when calculating the price. The billing rhythm determines the cycle in which a contract line is invoiced (billing period) if no manual intervention is made. The price of a billing line is calculated based on the **Price and Billing Base Period** field in the service commitment or contract line and the **Billed Base Period** field. 

If the invoiced period is a multiple of the billing base period, the price is multiplied accordingly.

* Monthly price = 100 (Price = 100 and Calculation Base Period = 1M) 

|1M - 1T  |Price  |2M - 1T  |Price  |1Q - 1T  |Price  |1Y - 1T  |Price  |
|---------|---------|---------|---------|---------|---------|---------|---------|
|28.01.24 - 27.02.24      |  100       |   28.01.24 - 27.03.24       |  200       |28.01.24 - 27.04.24      |     300    | 28.01.24 - 27.01.25         | 1200        |
|29.01.24 - 28.02.24      |    100     |    29.01.24 - 28.03.24      |     200    |29.01.24 - 28.04.24      |     300    |     29.01.24 - 28.01.25     |   1200      |
|30.01.24 - 28.02.24      |   100      |    30.01.24 - 29.03.24      |    200     |30.01.24 - 29.04.24      |     300    |  30.01.24 - 29.01.25        |   1200      |
|31.01.24 - 28.02.24      |    100     |   31.01.24 - 30.03.24       |    200     |31.01.24 - 29.04.24      |     300    |    31.01.24 - 30.01.25      |    1200     |
|29.02.24 - 28.03.24      |   100      |  29.02.24 - 28.04.24        |   200      |29.02.24 - 28.05.24      |    300     |    29.02.24 - 27.02.25      |   1200      |

If periods are invoiced that do not correspond to a multiple of the billing base period, days (as the next smaller unit) are always used for the price calculation. Depending on the calendar month and the billing base period, a different number of days is used as the basis. In a calendar year that is not a leap year, the number of days is 31 in January, 28 in February, and 90 in the first quarter (01.01.25 - 31.03.25).

Price of the Billing lines=∑1nPrice of Contract lines.
Number of days in the started period∗Days to be invoiced in the started period.
Price of the Billing lines=1∑n​Number of days in the started period.
Price of Contract lines​∗Days to be invoiced in the started period.


|Start - End  |Price  |Billing Base Period  |Billing Rhythm  |Invoiced Period  |Price of the Billing Lines  |
|---------|---------|---------|---------|---------|---------|
|01.01.2023 - 15.01.2023  |   100.00  |  1M  |  1Y  |  15 out of 31 days |   100/ 31 * 15 = 48.387       |
|01.02.2023 - 14.02.2023  |   100.00  |  1M  |  1Y  |   14 out of 28 days    | 100 * 14 / 28 = 50.00 |
|01.01.2023 - 14.02.2023  |  100.00   |  1M  |   1Y |  1M + 14 days  |  100/ 31 * 31 + 100 * 14 / 28 = 150.00  |
|31.01.2023 - 01.03.2023  |   100.00  |  1M  |  1Y  |  1M + 2 days  |  100.00 + 100.00 * 2/ 28 = 107.143  |
|01.01.2023 - 14.01.2023  |   100   |  1Q |  1Y     | 14 out of 90 days | 100/ 90 * 14 = 15.556  |
|01.01.2023 - 14.04.2023  |   100   |  1Q |  1Y     |  1Q + 14 out of 91 days  | 100/ 90 * 90 + 100 * 14 / 91 |
|28.02.2023 - 14.06.2023  |   100   |  1Q |  1Y  | 1Q + 18 out of 92 days  |  100/ 92 * 92 + 100 * 18 / 92 = 119.565 |

The price of a contract line is based on the period length in billing base period (for example, one month). *n* corresponds to the number of periods included. In the third example, one and a half months are invoiced (whole of January + half of February). Accordingly, the price for January and February is calculated separately and then added up. 
01.01.2023 - 31.01.2023 is a whole month. The price is 100.00 for the month.
01.02.2023 - 14.02.2023 are 14 days. A whole month would be 28 days (01.02.2023 - 28.02.2023). The price for the second month is therefore calculated pro rata: 14 / 28 * 100 = 50.00.
The price for the entire period invoiced corresponds to the sum of the partial periods: 100.00 + 50.00 = 150.00 

## Align to End of Month​

If the service start date and the next billing date are within the last three days of a month, the period is determined from the end of the month. This means that a contract line that is invoiced from the last day of a month, for one month, is invoiced up to the penultimate day of the following month. This happens regardless of how long the respective months are. This type of period calculation guarantees that the 13th monthly invoice starts on the same day (one year later). Apart from that, this type of period calculation works in the same way as align to start of month. For example, the next billing date determines the first day of the next billing.

* Monthly price = 100.00 (Price = 100.00 Billing Base Period = 1M)

|1M - 1T  |2M - 1T  |1Q - 1T  |1Y - 1T  |
|---------|---------|---------|---------|
|28.01.24 - 27.02.24      |   28.01.24 - 27.03.24       |    28.01.24 - 27.04.24      |  28.01.24 - 27.01.25        |
|29.01.24 - 26.02.24      |   29.01.24 - 28.03.24       |   29.01.24 - 27.04.24       |   29.01.24 - 28.01.25       |
|30.01.24 - 27.02.24      |  30.01.24 - 29.03.24        |   30.01.24 - 28.04.24       |  30.01.24 - 29.01.25        |
|31.01.24 - 28.02.24      |   31.01.24 - 30.03.24       |   31.01.24 - 29.04.24       |  31.01.24 - 30.01.25        |
|29.02.24 - 30.03.24      |   29.02.24 - 29.04.24       |   29.02.24 - 30.05.24       |   29.02.24 - 27.02.25       |

## Calculation of prices​

The price calculation is carried out using exactly the same logic. Only the period lengths are potentially different.

* Monthly price = 100.00 (Price = 100.00 Billing Base Period = 1M)

|1M - 1T  |Price  |2M - 1T  |Price  | 1Q - 1T  |Price  | 2Y - 1T  |Price  |
|---------|---------|---------|---------|---------|---------|---------|---------|
|28.01.24 - 27.02.24      |   100      |  28.01.24 - 27.03.24        |   200      |28.01.24 - 27.04.24     |    300     |   28.01.24 - 27.01.25       |   1200      |
|29.01.24 - 26.02.24      |    100     | 29.01.24 - 28.03.24         |   200      |29.01.24 - 27.04.24     |   300      |    29.01.24 - 28.01.25      |    1200     |
|30.01.24 - 27.02.24      |  100       |   30.01.24 - 29.03.24       |    200     |30.01.24 - 28.04.24      |    200     |   30.01.24 - 29.01.25       |   1200      |
|31.01.24 - 28.02.24      |   100      |  31.01.24 - 30.03.24        |     200    |31.01.24 - 29.04.24      |  200       |  31.01.24 - 30.01.25        |   1200      |
|29.02.24 - 30.03.24      |   100      |   29.02.24 - 29.04.24       |    200     |29.02.24 - 30.05.24      |   300      |  29.02.24 - 27.02.25        |   1200      |

Price of the Billing lines=∑1nPrice of Contract lines.Number of days in the started period∗Days to be invoiced in the started period.Price of the Billing lines=1∑n​Number of days in the started period.Price of Contract lines​∗Days to be invoiced in the started period.

|Start - End  |Price  |Billing Base Period  |Billing Rhythm  |Invoiced Period  |Price of the Billing Lines  |
|---------|---------|---------|---------|---------|---------|
|R01.01.2023 - 15.01.2023      |    100,-     | 1M        |  1J       | 15 out of 31 days  | 100/ 31 * 15 = 48.387  |
|01.02.2023 - 14.02.2023      |    100.00     | 1M        |  1Y       | 14 out of 28 days  | 100 * 14 / 28 = 50.00  |
|01.01.2023 - 14.02.2023 | 100.00 | 1M        |  1Y       | 1M + 14 days  | 100/ 31 * 31 + 100 * 14 / 28 = 150.00  |
|31.01.2023 - 01.03.2023      |  100.00       | 1M        |  1Y       | 1M + 2 days  | 100 + 100 * 2/ 28 = 107.143  |
|01.01.2023 - 14.01.2023      |  100       |   1Q   |  1Y  | 14 out of 90 days  | 100/ 90 * 14 = 15.556  |
|01.01.2023 - 14.04.2023  |  100.00 | 1Q  |  1Y  | 1Q + 14 out of 91 days  | 100/ 90 * 90 + 100 * 14 / 91 = 115.385  |

## Leap year​

The period calculation works almost the same in leap years as in normal years. The only difference is that 29.02. is the last day in February.

29.02.2024 - 30.03.2024 corresponds to one month. 29.02.2024 is the last day of February and 30.03.2024 is the penultimate day of March.

## Related information

[Customer contracts](customer-contracts.md)  
