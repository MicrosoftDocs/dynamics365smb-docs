---
title: Period calculation
description: Learn how to calculate periods to bill for on invoices in subscription billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 05/06/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Period calculation

**Period Calculation** controls how a period is determined for invoicing. Billing for a period length of *one* month works smoothly with subscription billing. However, if the start of the billing period is within the last three days of a month, the length of the month and the following month aren't taken into account.

A contract invoice issued for *one* month from February 28th (no leap year) ends with the [!INCLUDE [prod_short](../../includes/prod_short.md)] standard calculation on March 27th (+ 1M - 1D). However, a recurring billing from the *last* day of a month should extend to the *second to last* day of the following month to actually represent a full month.

To accommodate this, there is a choice to calculate periods using the [!INCLUDE [prod_short](../../includes/prod_short.md)] standard method or the subscription billing method. The **Period Calculation** with the option *[Align to Start of Month](#align-to-start-of-month)* uses the [!INCLUDE [prod_short](../../includes/prod_short.md)] standard method, whereas *[Align to End of Month](#align-to-end-of-month)* uses a different method.

For all recurring billing, we generally recommend the *Align to End of Month* option. You can set the option as the default. To learn more, go to [Service & Contracts Setup](/docs/srb/setup/general.md#default-period-calculation).

## Align to Start of Month

The calculation of a month with the option **Align to Start of Month** as the **Period Calculation** in the contract line uses the [!INCLUDE [prod_short](../../includes/prod_short.md)] standard date calculation.

### Calculation of the period

When calculating a whole month, the start date *plus* one month *minus* one day (CM-1D) is used to calculate the end of the period. For the calculation of two months, the start date *plus* two months *minus* one day (CM+1M-1D) is used to calculate the end of the period.

|1M - 1T|2M - 1T|1Q - 1T|1Y - 1T|
|:--|:--|:--|:--|
|01.28.24 - 02.27.24|01.28.24 - 03.27.24|01.28.24 - 04.27.24|01.28.24 - 01.27.25|
|01.29.24 - 02.28.24|01.29.24 - 03.28.24|01.29.24 - 04.28.24|01.29.24 - 01.28.25|
|01.30.24 - 02.28.24|01.30.24 - 03.29.24|01.30.24 - 04.29.24|01.30.24 - 01.29.25|
|01.31.24 - 02.28.24|01.31.24 - 03.30.24|01.31.24 - 04.29.24|01.31.24 - 01.30.25|
|02.29.24 - 03.28.24|02.29.24 - 04.28.24|02.29.24 - 05.28.24|02.29.24 - 02.27.25|

### Price calculation

The [Billing Rhythm](/docs/srb/masterdata/service-commitments.md#overview-of-the-fields-in-the-service-commitment-package) is not taken into account when calculating the price. The Billing Rhythm determines the cycle in which a contract line is invoiced (billing period) if no manual intervention is made. The price of a **Billing line** is calculated on the basis of **Price** and **Billing Base Period** in the Service Commitment or Contract line and the **Billed Base Period**. If the invoiced period is a multiple of the **Billing Base Period**, the price is multiplied accordingly.

*Monthly price = 100,- (Price = 100,- Calculation Base Period = 1M)*

|1M - 1T|Price|2M - 1T|Price|1Q - 1T|Price|1Y - 1T|Price|
|:--|:--|:--|:--|:--|:--|:--|:--|
|01.28.24 - 02.27.24|100|01.28.24 - 03.27.24|200|01.28.24 - 04.27.24|300|01.28.24 - 01.27.25|1200|
|01.29.24 - 02.28.24|100|01.29.24 - 03.28.24|200|01.29.24 - 04.28.24|300|01.29.24 - 01.28.25|1200|
|01.30.24 - 02.28.24|100|01.30.24 - 03.29.24|200|01.30.24 - 04.29.24|300|01.30.24 - 01.29.25|1200|
|01.31.24 - 02.28.24|100|01.31.24 - 03.30.24|200|01.31.24 - 04.29.24|300|01.31.24 - 01.30.25|1200|
|02.29.24 - 03.28.24|100|02.29.24 - 04.28.24|200|02.29.24 - 05.28.24|300|01.29.24 - 02.27.25|1200|

If you invoice periods that don't correspond to a multiple of the **Billing Base Period**, price calculation will always use *days* (as the next smaller unit). Depending on the **calendar month** and the **Billing Base Period**, a different number of days is used as the basis. In a calendar year that isn't a leap year, the number of days is 31 in January, 28 in February, and 90 in the first quarter (01.01.25 - 03.31.25).

```math
Price \ of \ the \ Billing \ lines = \sum\limits_1^n \frac{Price \ of \ Contract \ lines}{Number \ of \ days \ in \ the \ started \ period} * Days \ to \ be \ invoiced \ in \ the \ started \ period
```

|Start - End|Price|Billing Base Period|Billing Rhythm|Invoiced Period|Price of the Billing Lines|
|:--|:--|:--|:--|:--|:--|
|01.01.2023 - 01.15.2023|100,-|1M|1J|15 out of 31 days|100/ 31 * 15 = 48,387|
|01.02.2023 - 02.14.2023|100,-|1M|1J|14 out of 28 days|100 * 14 / 28 = 50,-|
|01.01.2023 - 02.14.2023|100,-|1M|1J|1M + 14 days|100/ 31 * 31 + 100 * 14 / 28 = 150,-|
|01.31.2023 - 03.01.2023|100,-|1M|1J|1M + 2 days|100,- + 100,- * 2/ 28 = 107,143 |
|01.01.2023 - 01.14.2023|100,-|1Q|1J|14 out of 90 days|100/ 90 * 14 = 15,556|
|01.01.2023 - 04.14.2023|100,-|1Q|1J|1Q + 14 out of 91 days|100/ 90 * 90 + 100 * 14 / 91|
|02.28.2023 - 06.14.2023|100,-|1Q|1J|1Q + 18 out of 92 days|100/ 92 * 92 + 100 * 18 / 92 = 119,565|

The price of a contract line is based on the period length in **Billing Base Period** (for example, 1 month). *N* corresponds to the number of periods included. In the third example, one and a half months are invoiced (whole of January + half of February). Accordingly, the price for January and February is calculated separately and then added up.

01.01.2023 - 01.31.2023 is a whole month. The price is 100,- for the month.

02.01.2023 - 02.14.2023 are 14 days. A whole month would be 28 days (02.01.2023 - 02.28.2023). The price for the second month is therefore calculated pro rata: 14 / 28 * 100 = 50,-.

The price for the entire period invoiced corresponds to the sum of the partial periods: 100,- + 50,- = 150,-

## Align to End of Month

If the **Service Start Date** and the **Next Billing Date** are within the last three days of a month, the period is determined from the end of the month. A contract line that's invoiced from the last day of a month for one month is invoiced up to the second to last day of the following month. This calculation happens regardless of how long the respective months are. This type of period calculation guarantees that the 13th monthly invoice starts on the same day (one year later). Apart from that, this type of period calculation works in the same way as *Align to Start of Month*. For example, the **Next Billing Date**  determines the first day of the next billing.

*Monthly price = 100,- (Price = 100,- Billing Base Period = 1M)*

|1M - 1T|2M - 1T|1Q - 1T|1Y - 1T|
|:--|:--|:--|:--|
|01.28.24 - 02.27.24|01.28.24 - 03.27.24|01.28.24 - 04.27.24|01.28.24 - 01.27.25|
|01.29.24 - 02.26.24|01.29.24 - 03.28.24|01.29.24 - 04.27.24|01.29.24 - 01.28.25|
|01.30.24 - 02.27.24|01.30.24 - 03.29.24|01.30.24 - 04.28.24|01.30.24 - 01.29.25|
|01.31.24 - 02.28.24|01.31.24 - 03.30.24|01.31.24 - 04.29.24|01.31.24 - 01.30.25|
|02.29.24 - 03.30.24|02.29.24 - 04.29.24|02.29.24 - 05.30.24|02.29.24 - 02.27.25|

### Calculation of prices

The price calculation uses the same logic as [above](#price-calculation). Only the period lengths are potentially different.

*Monthly price = 100,- (Price = 100,- Billing Base Period = 1M)*

|1M - 1T|Price|2M - 1T|Price|1Q - 1T|Price|1Y - 1T|Price|
|:--|:--|:--|:--|:--|:--|:--|:--|
|01.28.24 - 02.27.24|100|01.28.24 - 03.27.24|200|01.28.24 - 04.27.24|300|01.28.24 - 01.27.25|1200|
|01.29.24 - 02.26.24|100|01.29.24 - 03.28.24|200|01.29.24 - 04.27.24|300|01.29.24 - 01.28.25|1200|
|01.30.24 - 02.27.24|100|01.30.24 - 03.29.24|200|01.30.24 - 04.28.24|300|01.30.24 - 01.29.25|1200|
|01.31.24 - 02.28.24|100|01.31.24 - 03.30.24|200|01.31.24 - 04.29.24|300|01.31.24 - 01.30.25|1200|
|02.29.24 - 03.30.24|100|02.29.24 - 04.29.24|200|02.29.24 - 05.30.24|300|02.29.24 - 02.27.25|1200|

```math
Price \ of \ the \ Billing \ lines = \sum\limits_1^n \frac{Price \ of \ Contract \ lines}{Number \ of \ days \ in \ the \ started \ period} * Days \ to \ be \ invoiced \ in \ the \ started \ period
```

|Start - End|Price|Billing Base Period|Billing Rhythm|Invoiced Period|Price of the Billing Lines|
|:--|:--|:--|:--|:--|:--|
|01.01.2023 - 01.15.2023|100,-|1M|1J|15 out of 31 days|100/ 31 * 15 = 48,387|
|02.01.2023 - 02.14.2023|100,-|1M|1J|14 out of 28 days|100 * 14 / 28 = 50,-|
|01.01.2023 - 02.14.2023|100,-|1M|1J|1M + 14 days|100/ 31 * 31 + 100 * 14 / 28 = 150,-|
|01.31.2023 - 03.01.2023|100,-|1M|1J|1M + 2 days|100,- + 100,- * 2/ 28 = 107,143 |
|01.01.2023 - 01.14.2023|100,-|1Q|1J|14 out of 90 days|100/ 90 * 14 = 15,556|
|01.01.2023 - 04.14.2023|100,-|1Q|1J|1Q + 14 out of 91 days|100/ 90 * 90 + 100 * 14 / 91 = 115,385|
|02.28.2023 - 06.14.2023|100,-|1Q|1J|1Q + 15 out of 92 days|100/ 92 * 92 + 100 * 15 / 92 = 116,304|

### Leap year

The period calculation works almost the same in leap years as in normal years. The only difference is that 02.29 is the last day in February.

02.29.2024 - 03.30.2024 corresponds to one month. 02.29.2024 is the last day of February and 03.30.2024 is the second to last day of March.

## Related information

[Customer subscription contracts](customer-contracts.md)  
