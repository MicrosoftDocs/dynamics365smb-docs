---
title: Manufacturing KPIs and measures (Power BI)
description: Get an overview of all the KPIs and measures in the semantic model for the Manufacturing Power BI app.
author: kennienp
ms.author: kepontop
ms.reviewer:
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 
ms.date: 11/06/2024
ms.service: dynamics-365-business-central
---

# Power BI Manufacturing app KPIs and measures

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This page provides a list of all Key Performance Indicators (KPIs) included in the semantic model for the Power BI Manufacturing report.

Explore the list of KPIs below to learn more about how they can help you achieve your business goals.

Each KPI is described, including how it is calculated and what data was used in the calculations.

## Calendar Entries

### Calendar Entry Measures

- [Capacity (Effective)](#capacity-effective)
- [Capacity (Total)](#capacity-total)

#### Capacity (Effective)

**Formula**

- This measure, **Capacity (Effective)**, calculates the total effective capacity from the Calendar Entries table by summing up all values in the Capacity Effective column.

**Data Source**

- Calendar Entry

#### Capacity (Total)

**Formula**

- This measure, **Capacity (Total)**, calculates the overall total effective capacity from the Calendar Entries table by summing up all values in the Capacity Total column.

**Data Source**

- Calendar Entry

## Capacity Ledger Entries

### Capacity Ledger Entry Measures

- [Capacity Ledger Output Quantity](#capacity-ledger-output-quantity)
- [Capacity Ledger Quantity](#capacity-ledger-quantity)
- [Direct Cost](#direct-cost)
- [Overhead Cost](#overhead-cost)
- [Run Time](#run-time)
- [Scrap %](#scrap-percent)
- [Scrap Quantity](#scrap-quantity)
- [Setup Time](#setup-time)
- [Stop Time](#stop-time)

#### Capacity Ledger Output Quantity

**Formula**

- The Capacity Ledger Output Quantity measure calculates the total output quantity recorded in the Capacity Ledger Entries table by summing up all values in the outputQuantity column.

**Data Source**

- Capacity Ledger Entry

#### Capacity Ledger Quantity

**Formula**

- The Capacity Ledger Quantity measure calculates the total quantity recorded in the Capacity Ledger Entries table by summing up all values in the quantity column.

**Data Source**

- Capacity Ledger Entry

#### Direct Cost

**Formula**

- The Direct Cost measure calculates the cost amount actual from the Value Entries table, specifically filtering for entries categorized as Direct Cost.
This measure determines the direct cost for capacity ledger entries by summing the related value entry cost amounts.

**Data Source**

- Capacity Ledger Entry
- Value Entry

#### Overhead Cost

**Formula**

- The Overhead Cost measure calculates the cost amount actual from the Value Entries table, specifically filtering for entries categorized as Indirect Cost.
This measure determines the indirect cost for capacity ledger entries by summing the related value entry cost amounts.

**Data Source**

- Capacity Ledger Entry
- Value Entry

#### Run Time

**Formula**

- The Run Time measure calculates the total runtime recorded in the Capacity Ledger Entries table by summing up all values in the runtime column.

**Data Source**

- Capacity Ledger Entry

#### Scrap Percent

**Formula**

- The Scrap % measure calculates the percentage of scrapped output by dividing the Scrap Quantity by the total Output Quantity recorded in the Capacity Ledger Entries table.

**Data Source**

- Capacity Ledger Entry

#### Scrap Quantity

**Formula**

- The Scrap Quantity measure calculates the total amount of scrapped output recorded in the Capacity Ledger Entries table by summing up all values in the scrapQuantity column.

**Data Source**

- Capacity Ledger Entry

#### Setup Time

**Formula**

- The Setup Time measure calculates the total setup time recorded in the Capacity Ledger Entries table by summing up all values in the setupTime column.

**Data Source**

- Capacity Ledger Entry

#### Stop Time

**Formula**

- The Stop Time measure calculates the total stop time recorded in the Capacity Ledger Entries table by summing up all values in the stopTime column.

**Data Source**

- Capacity Ledger Entry

## Item Ledger Entries

### Item Ledger Entry Measures

- [Consumption Quantity](#consumption-quantity)
- [Item Ledger Entry Cost Amount Actual](#item-ledger-entry-cost-amount-actual)
- [Output Quantity](#output-quantity)
- [Quantity](#quantity)

#### Consumption Quantity

**Formula**

- The **Consumption Quantity** measure calculates the total [Quantity](#quantity) of item ledger entries where the **Entry Type** is "Consumption" by filtering the *Item Ledger Entries* table before summing.

**Data Source**

- Item Ledger Entry

#### Item Ledger Entry Cost Amount Actual

**Formula**

- The **Item Ledger Entry Cost Amount Actual** measure calculates the total actual cost recorded in the Item Ledger Entries table by summing up all values in the **costAmountActual** column.

**Data Source**

- Item Ledger Entry

#### Output Quantity

**Formula**

- The **Output Quantity** measure calculates the total [Quantity](#quantity) of item ledger entries where the **Entry Type** is "Output" by filtering the *Item Ledger Entries* table before summing.

**Data Source**

- Item Ledger Entry

#### Quantity

**Formula**

- The **Quantity** measure sums the values in the *qty* column of the Item Ledger Entries table to calculate the total quantity across all records.

**Data Source**

- Item Ledger Entry

## Machine Center

### Machine Center Measures

- [Machine Center Availability After Orders](#machine-center-availability-after-orders)
- [Machine Center Load](#machine-center-load)
- [Machine Center Output](#machine-center-output)
- [Machine Center Run Time](#machine-center-run-time)
- [Machine Center Scrap](#machine-center-scrap)
- [Machine Center Scrap %](#machine-center-scrap-percent)
- [Machine Center Stop %](#machine-center-stop-percent)
- [Machine Center Stop Time](#machine-center-stop-time)

#### Machine Center Availability After Orders

**Formula**

- The **Machine Center Availability After Orders** measure calculates the remaining available capacity for machine centers by subtracting the **[Machine Center Allocated Time](#machine-center-allocated-time)** from the **[Machine Center Capacity (Effective)](#machine-center-capacity-effective)**.

**Data Source**

- Prod Order Capacity Need
- Calendar Entry

#### Machine Center Load

**Formula**

- The **Machine Center Load** measure calculates the ratio of allocated time to effective capacity for machine centers by dividing the **[Machine Center Allocated Time](#machine-center-allocated-time)** by the **[Machine Center Capacity (Effective)](#machine-center-capacity-effective)**.

**Data Source**

- Prod Order Capacity Need
- Calendar Entry

#### Machine Center Output

**Formula**

- The **Machine Center Output** measure calculates the total output quantity for machine centers by summing the **outputQuantity** column in the *Capacity Ledger Entries* table, filtered to include only rows where **Type** is "Machine Center".

**Data Source**

- Capacity Ledger Entry

#### Machine Center Run Time

**Formula**

- The **Machine Center Run Time** measure calculates the total run time for machine centers by summing the **runTime** and **setupTime** columns in the *Capacity Ledger Entries* table, filtered to include only rows where **Type** is "Machine Center". This is done using the `SUMX` function over the filtered table.

**Data Source**

- Capacity Ledger Entry

#### Machine Center Scrap

**Formula**

- The **Machine Center Scrap** measure calculates the total scrap quantity for machine centers by summing the **scrapQuantity** column in the *Capacity Ledger Entries* table, filtered to include only rows where **Type** is "Machine Center".

**Data Source**

- Capacity Ledger Entry

#### Machine Center Scrap Percent

**Formula**

- The **Machine Center Scrap %** measure calculates the percentage of scrap for machine centers by dividing the **[Machine Center Scrap](#machine-center-scrap)** by the **[Machine Center Output](#machine-center-output)**.

**Data Source**

- Capacity Ledger Entry

#### Machine Center Stop Percent

**Formula**

- The **Machine Center Stop %** measure calculates the percentage of stop time for machine centers by dividing the **[Machine Center Stop Time](#machine-center-stop-time)** by the **[Machine Center Run Time](#machine-center-run-time)**.

**Data Source**

- Capacity Ledger Entry

#### Machine Center Stop Time

**Formula**

- The **Machine Center Stop Time** measure calculates the total stop time for machine centers by summing the **stopTime** column in the *Capacity Ledger Entries* table, filtered to include only rows where **Type** is "Machine Center".

**Data Source**

- Capacity Ledger Entry

### Machine Center Statistics

- [Machine Center Actual Efficiency %](#machine-center-actual-efficiency-percent)
- [Machine Center Actual Need](#machine-center-actual-need)
- [Machine Center Actual Total Cost](#machine-center-actual-total-cost)
- [Machine Center Allocated Time](#machine-center-allocated-time)
- [Machine Center Capacity (Effective)](#machine-center-capacity-effective)
- [Machine Center Capacity (Total)](#machine-center-capacity-total)
- [Machine Center Expected Efficiency %](#machine-center-expected-efficiency-percent)

#### Machine Center Actual Efficiency Percent

**Formula**

- The **Machine Center Actual Efficiency %** measure calculates the actual efficiency for machine centers by dividing the **[Machine Center Actual Need](#machine-center-actual-need)** by the **[Machine Center Capacity (Total)]()**.

**Data Source**

- Capacity Ledger Entry
- Calendar Entry

#### Machine Center Actual Need

**Formula**

- The **Machine Center Actual Need** measure calculates the total actual time required for machine centers by summing the **setupTime**, **runTime**, and **stopTime** columns in the *Capacity Ledger Entries* table, filtered to include only rows where **Type** is "Machine Center". This is done using the `SUMX` function over the filtered table.

**Data Source**

- Capacity Ledger Entry

#### Machine Center Actual Total Cost

**Formula**

- The **Machine Center Actual Total Cost** measure calculates the total actual cost for machine centers by adding the **[Direct Cost](#direct-cost)** and **[Overhead Cost](#overhead-cost)** measures, filtered to include only rows in the *Capacity Ledger Entries* table where **Type** is "Machine Center".

**Data Source**

- Capacity Ledger Entry
- Value Entry

#### Machine Center Allocated Time

**Formula**

- The **Machine Center Allocated Time** measure calculates the total allocated time for machine centers by summing the **allocatedTime** column in the *Prod Order Capacity Need* table, filtered to include only rows where **Type** is "Machine Center" and **Requested Only** is FALSE.

**Data Source**

- Prod Order Capacity Need

#### Machine Center Capacity (Effective)

**Formula**

- The **Machine Center Capacity (Effective)** measure calculates the total effective capacity for machine centers by summing the **Capacity Effective** column in the *Calendar Entries* table, filtered to include only rows where **Capacity Type** is "Machine Center".

**Data Source**

- Calendar Entry

#### Machine Center Capacity (Total)

**Formula**

- The **Machine Center Capacity (Total)** measure calculates the total capacity for machine centers by summing the **Capacity Total** column in the *Calendar Entries* table, filtered to include only rows where **Capacity Type** is "Machine Center".

**Data Source**

- Calendar Entry

#### Machine Center Expected Efficiency Percent

**Formula**

- The **Machine Center Expected Efficiency %** measure calculates the expected efficiency for machine centers by dividing the **[Machine Center Capacity (Effective)](#machine-center-capacity-effective)** by the **[Machine Center Capacity (Total)](#machine-center-capacity-total)**.

**Data Source**

- Calendar Entry

## Prod Order Capacity Need

### Prod Order Capacity Need Measures

- [Allocated Time](#allocated-time)
- [Needed Time](#needed-time)
- [Needed Time (MS)](#needed-time-ms)

#### Allocated Time

**Formula**

- The **Allocated Time** measure calculates the total allocated time by summing the **allocatedTime** column in the *Prod Order Capacity Need* table, filtered to include only rows where **Requested Only** is FALSE.

**Data Source**

- Prod Order Capacity Need

#### Needed Time

**Formula**

- The **Needed Time** measure calculates the total needed time by summing the **neededTime** column in the *Prod Order Capacity Need* table.

**Data Source**

- Prod Order Capacity Need

#### Needed Time (MS)

**Formula**

- The **Needed Time (MS)** measure calculates the total needed time in manufacturing-specific units by dividing the sum of **neededTimeMs** from the *Prod Order Capacity Need* table by a **Time Factor**. The **Time Factor** is retrieved using `LOOKUPVALUE` based on the capacity unit of measure selected in the *Manufacturing Setup* table.

**Data Source**

- Prod Order Capacity Need
- Manufacturing Setup

## Prod Order Components

### Prod Order Component Measures

- [Prod Order Component Cost Amount](#prod-order-component-cost-amount)
- [Prod Order Component Expected Qty. (Base)](#prod-order-component-expected-qty-base)
- [Prod Order Component Remaining Qty. (Base)](#prod-order-component-remaining-qty-base)

#### Prod Order Component Cost Amount

**Formula**

- The **Prod Order Component Cost Amount** measure calculates the total cost of production order components by summing the **costAmount** column in the *Prod Order Components* table.

**Data Source**

- Prod Order Component

#### Prod Order Component Expected Qty. (Base)

**Formula**

- The **Prod Order Component Expected Qty. (Base)** measure calculates the total expected quantity (in base units) of production order components by summing the **expectedQtyBase** column in the *Prod Order Components* table.

**Data Source**

- Prod Order Component

#### Prod Order Component Remaining Qty. (Base)

**Formula**

- The **Prod Order Component Remaining Qty. (Base)** measure calculates the total remaining quantity (in base units) of production order components by summing the **remainingQtyBase** column in the *Prod Order Components* table.

**Data Source**

- Prod Order Component

## Prod Order Routing Lines

### Prod Order Routing Measures

- [Expected Operation Cost](#expected-operation-cost)
- [Operation Move Time](#operation-move-time)
- [Operation Run Time](#operation-run-time)
- [Operation Setup Time](#operation-setup-time)
- [Operation Wait Time](#operation-wait-time)
- [Prod Order Routing Expected Capacity Need](#prod-order-routing-expected-capacity-need)
- [Prod Order Routing Expected Capacity Ovhd. Cost](#prod-order-routing-expected-capacity-ovhd-cost)
- [Prod Order Routing Expected Operation Cost Amt.](#prod-order-routing-expected-operation-cost-amt)
- [Total Duration Days](#total-duration-days)
- [Total Duration Hours](#total-duration-hours)

#### Expected Operation Cost

**Formula**

- The **Expected Operation Cost** measure calculates the total expected operational cost by using `SUMX` to iterate over the *Prod Order Routing Lines* table and summing the difference between **Expected Operation Cost Amt.** and **Expected Capacity Ovhd. Cost** for each row.

**Data Source**

- Prod Order Routing Line

#### Operation Move Time

**Formula**
-The **Operation Move Time** measure calculates the total move time for production order routing lines by summing the **Move Time** column in the *Prod Order Routing Lines* table.

**Data Source**

- Prod Order Routing Line

#### Operation Run Time

**Formula**

- The **Operation Run Time** measure calculates the total run time for production order routing lines by summing the **Run Time** column in the *Prod Order Routing Lines* table.

**Data Source**

- Prod Order Routing Line

#### Operation Setup Time

**Formula**

- The **Operation Setup Time** measure calculates the total setup time for production order routing lines by summing the **Setup Time** column in the *Prod Order Routing Lines* table.

**Data Source**

- Prod Order Routing Line

#### Operation Wait Time

**Formula**

- The **Operation Wait Time** measure calculates the total wait time for production order routing lines by summing the **Wait Time** column in the *Prod Order Routing Lines* table.

**Data Source**

- Prod Order Routing Line

#### Prod Order Routing Expected Capacity Need

**Formula**

- The **Prod Order Routing Expected Capacity Need** measure calculates the total expected capacity requirement for production order routing lines by summing the **Expected Capacity Need** column in the *Prod Order Routing Lines* table.

**Data Source**

- Prod Order Routing Line

#### Prod Order Routing Expected Capacity Ovhd. Cost

**Formula**

- The **Prod Order Routing Expected Capacity Ovhd. Cost** measure calculates the total expected capacity overhead cost for production order routing lines by summing the **Expected Capacity Ovhd. Cost** column in the *Prod Order Routing Lines* table.

**Data Source**

- Prod Order Routing Line

#### Prod Order Routing Expected Operation Cost Amt

**Formula**

- The **Prod Order Routing Expected Operation Cost Amt.** measure calculates the total expected operation cost amount for production order routing lines by summing the **Expected Operation Cost Amt.** column in the *Prod Order Routing Lines* table.

**Data Source**

- Prod Order Routing Line

#### Total Duration Days

**Formula**

- The **Total Duration Days** measure calculates the total duration of production order routing lines in days by summing the **Duration Total Days** column in the *Prod Order Routing Lines* table. Duration Total Days column is calculated in Power Query from the Starting Date Time and Ending Date Time fields on the Prod Order Routing Line.

**Data Source**

- Prod Order Routing Line

#### Total Duration Hours

**Formula**

- The **Total Duration Hours** measure calculates the total duration of production order routing lines in hours by summing the **Duration Total Hours** column in the *Prod Order Routing Lines* table. Duration Total Hours column is calculated in Power Query from the Starting Date Time and Ending Date Time fields on the Prod Order Routing Line.

**Data Source**

- Prod Order Routing Line

## Production Order Lines

### Production Order Line Measures

- [Finished Quantity (Base)]()
- [Quantity (Base)]()
- [Remaining Quantity (Base)]()

## Production Orders

### Production Order Measures

- [Actual Time Used]()
- [Average Production Time Per Finished Quantity]()
- [Expected Production Order Scrap Quantity]()
- [Finished %]()
- [No. of Production Orders]()
- [Planned Quantity]()
- [Remaining %]()
- [Variance Quantity]()

### Production Order Statistics

#### Actual Costs

- [Actual Capacity Cost]()
- [Actual Capacity Overhead Cost]()
- [Actual Manufacturing Overhead Cost]()
- [Actual Material Cost]()
- [Actual Subcontracted Cost]()
- [Total Actual Cost]()

#### Capacity Need

- [Prod Order Actual Capacity Need]()
- [Prod Order Capacity Need Dev %]()
- [Prod Order Capacity Need Variance]()
- [Prod Order Expected Capacity Need]()
- [Prod Order Expected Capacity Need (Finished)]()
- [Prod Order Expected Capacity Need (Non Finished)]()

#### Expected Costs

- [Expected Capacity Cost]()
- [Expected Capacity Overhead Cost]()
- [Expected Manufacturing Overhead Cost]()
- [Expected Material Cost]()
- [Expected Subcontracted Cost]()
- [Total Expected Cost]()

##### Variance to Expected Cost

- [Expected Capacity Cost Variance]()
- [Expected Capacity Overhead Cost Variance]()
- [Expected Manufacturing Overhead Cost Variance]()
- [Expected Material Cost Variance]()
- [Expected Subcontracted Cost Variance]()
- [Total Expected Cost Variance]()

##### Variance to Expected Cost Deviation %

- [Expected Capacity Cost Dev %]()
- [Expected Capacity Overhead Cost Dev %]()
- [Expected Manufacturing Overhead Cost Dev %]()
- [Expected Material Cost Dev %]()
- [Expected Subcontracted Cost Dev %]()
- [Total Expected Cost Dev %]()

#### Standard Costs

- [Standard Capacity Cost]()
- [Standard Capacity Overhead Cost]()
- [Standard Manufacturing Overhead Cost]()
- [Standard Material Cost]()
- [Standard Subcontracted Cost]()
- [Total Standard Cost]()

##### Variance to Standard Cost

- [Standard Capacity Cost Variance]()
- [Standard Capacity Overhead Cost Variance]()
- [Standard Manufacturing Overhead Cost Variance]()
- [Standard Material Cost Variance]()
- [Standard Subcontracted Cost Variance]()
- [Total Standard Cost Variance]()

##### Variance to Standard Cost Deviation %

- [Standard Capacity Cost Dev %]()
- [Standard Capacity Overhead Cost Dev %]()
- [Standard Manufacturing Overhead Cost Dev %]()
- [Standard Material Cost Dev %]()
- [Standard Subcontracted Cost Dev %]()
- [Total Standard Cost Dev %]()

## Value Entries

### Production Order - WIP

- [Beginning Balance Value]()
- [Capacity Value]()
- [Consumption Value]()
- [Cost Posted to G/L]()
- [Ending Balance Value]()
- [Output Value]()

### Value Entry Measures

- [Cost Amount Actual]()
- [Cost Amount Expected]()
- [Cost Posted to G/L]()
- [Expected Cost]()
- [Expected Cost Posted to G/L]()
- [ILE Quantity]()
- [Valued Quantity]()

## Work Center

### Work Center Measures

- [Work Center Availability After Orders]()
- [Work Center Load]()
- [Work Center Output]()
- [Work Center Scrap]()
- [Work Center Scrap %]()

### Work Center Statistics

- [Work Center Actual Efficieny %]()
- [Work Center Actual Need]()
- [Work Center Actual Total Cost]()
- [Work Center Allocated Time]()
- [Work Center Capacity (Effective)]()
- [Work Center Capacity (Total)]()
- [Work Center Expected Efficiency %]()

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
