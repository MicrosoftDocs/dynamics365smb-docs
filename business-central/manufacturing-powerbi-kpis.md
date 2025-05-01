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

- [Machine Center Actual Efficiency %]()
- [Machine Center Actual Need]()
- [Machine Center Total Cost]()
- [Machine Center Allocated Time](#machine-center-allocated-time)
- [Machine Center Capacity (Effective)](#machine-center-capacity-effective)
- [Machine Center Capacity (Total)]()
- [Machine Center Expected Efficiency %]()

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

## Prod Order Capacity Need

### Prod Order Capacity Need Measures

- [Allocated Time]()
- [Needed Time]()
- [Needed Time (MS)]()

## Prod Order Components

### Prod Order Component Measures

- [Prod Order Component Cost Amount]()
- [Prod Order Component Expected Qty. (Base)]()
- [Prod Order Component Remaining Qty. (Base)]()

## Prod Order Routing Lines

### Prod Order Routing Measures

- [Expected Operation Cost]()
- [Operation Move Time]()
- [Operation Run Time]()
- [Operation Setup Time]()
- [Operation Wait Time]()
- [Prod Order Routing Expected Capacity Need]()
- [Prod Order Routing Expected Capacity Ovhd. Cost]()
- [Prod Order Routing Expected Operation Cost Amt.]()
- [Total Duration Days]()
- [Total Duration Hours]()

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
