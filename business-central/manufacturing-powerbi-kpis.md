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

- [Finished Quantity (Base)](#finished-quantity-base)
- [Quantity (Base)](#quantity-base)
- [Remaining Quantity (Base)](#remaining-quantity-base)

#### Finished Quantity (Base)

**Formula**

- The **Finished Quantity (Base)** measure calculates the total finished quantity in base units for production order lines by summing the **finishedQtyBase** column in the *Production Order Lines* table.

**Data Source**

- Prod. Order Line

#### Quantity (Base)

- The **Quantity (Base)** measure calculates the total quantity in base units for production order lines by summing the **quantityBase** column in the *Production Order Lines* table.

**Data Source**

- Prod. Order Line

#### Remaining Quantity (Base)

**Formula**

- The **Remaining Quantity (Base)** measure calculates the total remaining quantity in base units for production order lines by summing the **remainingQtyBase** column in the *Production Order Lines* table.

**Data Source**

- Prod. Order Line

## Production Orders

### Production Order Measures

- [Actual Time Used](#actual-time-used)
- [Average Production Time Per Finished Quantity](#average-production-time-per-finished-quantity)
- [Expected Production Order Scrap Quantity](#expected-production-order-scrap-quantity)
- [Finished %](#finished-percent)
- [No. of Production Orders](#no-of-production-orders)
- [Planned Quantity](#planned-quantity)
- [Remaining %](#remaining-percent)
- [Variance Quantity](#variance-quantity)

#### Actual Time Used

**Forumla**

- The **Actual Time Used** measure calculates the total actual time used by production orders. It first summarizes the production orders and computes the **Actual Time** by summing the **quantity** from the *Capacity Ledger Entries* table, only when there is a **[Finished Quantity](#finished-quantity)**. Then, it sums up these values across all production orders using `SUMX`.

**Data Source**

- Capacity Ledger Entry
- Production Order

#### Average Production Time Per Finished Quantity

**Formula**

- The **Average Production Time Per Finished Quantity** measure calculates the average time spent on production per finished quantity by dividing the **[Actual Time Used](#actual-time-used)** by the **[Finished Quantity](#finished-quantity)**.

**Data Source**

- Capacity Ledger Entry
- Production Order

#### Expected Production Order Scrap Quantity

**Formula**

- The **Expected Production Order Scrap Quantity** measure calculates the expected scrap quantity for production orders by multiplying the **[Finished Quantity](#finished-quantity)** by the **Prod Order Source No. Scrap %** for the selected production order.

**Data Source**

- Production Order
- Item
- Item Ledger Entries

#### Finished Percent

**Forumla**

- The **Finished %** measure calculates the percentage of finished quantity relative to the planned quantity by dividing the **[Finished Quantity](#finished-quantity)** by the **[Planned Quantity](#planned-quantity)**.

**Data Source**

- Production Order
- Item Ledger Entry

#### Finished Quantity

**Formula**

- The **Finished Quantity** measure calculates the total finished quantity for each production order source number. It summarizes the Production Orders table by Production Order and Prod Order Source No., and then calculates the finished quantity by summing the qty from the Item Ledger Entries table where the Entry Type is "Output" and the Item No. matches the selected Prod Order Source No.. Finally, it sums the finished quantities across all production orders using SUMX.

**Data Source**

- Production Order
- Item Ledger Entry

#### No. of Production Orders

**Formula**

- The **No. of Production Orders** measure calculates the total number of production orders by counting the distinct entries in the **Production Order** column of the *Production Orders* table.

**Data Source**

- Production Order

#### Planned Quantity

**Formula**

- The **Planned Quantity** measure calculates the total planned quantity for production orders by summing the **quantity** column in the *Production Orders* table.

**Data Source**

- Production Order

#### Production Order Scrap Percent

**Formula**

- The **Production Order Scrap %** measure calculates the percentage of scrap quantity relative to the finished quantity by dividing the **[Scrap Quantity](#scrap-quantity)** by the **[Finished Quantity](#finished-quantity)**.

**Data Source**

- Item Ledger Entry
- Capacity Ledger Entry

#### Remaining Percent

**Formula**

- The **Remaining %** measure calculates the remaining percentage of the planned quantity that hasn't been finished. It checks if the **[Finished Quantity](#finished-quantity)** is less than the **[Planned Quantity](#planned-quantity)**. If true, it returns the negative of the **[Variance Quantity](#variance-quantity)** divided by the **[Planned Quantity](#planned-quantity)**. If the finished quantity is equal to or greater than the planned quantity, it returns **BLANK**.

**Data Source**

- Item Ledger Entry
- Production Order

#### Variance Quantity

**Formula**

- The **Variance Quantity** measure calculates the difference between the **[Finished Quantity](#finished-quantity)** and the **[Planned Quantity](#planned-quantity)**, indicating whether the production order has a surplus or deficit in finished quantity relative to what was planned.

**Data Source**

- Item Ledger Entry
- Production Order

### Production Order Statistics

#### Actual Costs

- [Actual Capacity Cost](#actual-capacity-cost)
- [Actual Capacity Overhead Cost](#actual-capacity-overhead-cost)
- [Actual Manufacturing Overhead Cost](#actual-manufacturing-overhead-cost)
- [Actual Material Cost](#actual-material-cost)
- [Actual Subcontracted Cost](#actual-subcontracted-cost)
- [Total Actual Cost](#total-actual-cost)

#### Actual Capacity Cost

**Formula**

The **Actual Capacity Cost** measure calculates the actual cost of capacity usage based on production order lines and related inventory adjustments. Here's a breakdown of the calculation:

1. **Variables for Production Order Details**:
   The measure defines variables for the **Production Order Number**, **Production Order Line Number**, **Item Number**, and **Production Order Status** from the *Production Order Lines* table.

2. **Inventory Adjustment Lines**:
   It then creates a table of relevant inventory adjustment lines that correspond to the current production order line, with the condition that the **iSFinished** status is set to TRUE if the production order status is "Finished".

3. **Inventory Adjustment Details**:
   The measure selects the order number, item number, and order line number from the inventory adjustment lines.

4. **Capacity Ledger Entries**:
   It then filters the *Capacity Ledger Entries* table to match the **Order No.**, **Order Line No.**, and **Item No.** from the inventory adjustments and ensures **Subcontracting** is excluded.

5. **Return the Actual Capacity Cost**:
   Finally, the measure calculates the sum of **directCost** from the *Capacity Ledger Entries* table, dividing it by the **ShareOfCapCost** measure to account for the specific share of capacity costs.

This complex calculation ties together various production and inventory details to derive the actual capacity cost for the production orders.

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)

#### Actual Capacity Overhead Cost

**Formula**

- The **Actual Capacity Overhead Cost** measure calculates the total overhead cost recorded in capacity ledger entries by summing the **overheadCost** column in the *Capacity Ledger Entries* table.

**Data Source**

- Capacity Ledger Entry

#### Actual Manufacturing Overhead Cost

**Formula**

The **Actual Manufacturing Overhead Cost** measure calculates the total overhead cost incurred during manufacturing by combining indirect cost percentages and per-unit overhead rates with actual production metrics. Here's how it works:

1. **IndirectCost**:
   It sums the **indirectCostPercent** values across all production order lines.

2. **OverheadRate**:
   It sums the **overheadRate** values across all production order lines.

3. **OutputQty**:
   It calculates the total output quantity from the *Item Ledger Entries* table, filtered to include only entries of type **"Output"**, and scoped to the currently selected production order.

4. **Final Calculation**:
   The measure multiplies the sum of:

   - **[Actual Material Cost](#actual-material-cost)**
   - **[Actual Capacity Cost](#actual-capacity-cost)**
   - **[Actual Subcontracted Cost](#actual-subcontracted-cost)**
   - **[Actual Capacity Overhead Cost](#actual-capacity-overhead-cost)**

   by the **IndirectCost** percentage (converted from percent to decimal), and then adds the product of **OutputQty** and **OverheadRate**.

This measure captures both proportional overhead based on other costs and fixed overhead based on output volume.

**Data Sources**

- Prod. Order Line
- Item Ledger Entry
- Capacity Ledger Entry
- Value Entry

#### Actual Material Cost

**Formula**

The **Actual Material Cost** measure calculates the total material cost consumed in production by summing the **costAmountActual** from the *Value Entries* table, filtered to:

- Exclude entries where **entryType** is "Rounding"
- Include only entries where **Item Ledger Entry Type** is "Consumption"

The result is then multiplied by -1 to reflect material consumption as a cost.

**Data Source**

- Value Entry

#### Actual Subcontracted Cost

**Formula**
The **Actual Subcontracted Cost** measure calculates the total direct cost of subcontracted work associated with production orders. Here's how it works:

1. **Context per Line**:
   For each row in the *Production Order Lines* table, it defines key variables:

   - ProdOrderNo
   - ProdOrderLineNo
   - ProdOrderItem
   - ProdOrderStatus

2. **Inventory Adjustment Matching**:
   It retrieves matching rows from *Inventory Adjustment Entry Order Line* where:

   - Order number, line number, and item match the production order line variables.
   - The **iSFinished** flag corresponds to whether the production order is marked as "Finished".

3. **Subcontracted Capacity Ledger Entries**:
   It then filters the *Capacity Ledger Entries* table to:

   - Match the order number, order line number, and item number from the inventory adjustment.
   - Include only entries where **Subcontracting** is TRUE.

4. **Cost Calculation**:
   It calculates the total **directCost** from these filtered subcontracted capacity ledger entries and divides it by the **ShareOfCapCost** measure.

5. **Aggregation**:
   `SUMX` iterates this logic over all production order lines, returning the total actual subcontracted cost.

This measure isolates and aggregates costs related to subcontracted operations.

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)

#### Total Actual Cost

**Formula**

The **Total Actual Cost** measure calculates the full cost of production by summing the following measures:

- **[Actual Material Cost](#actual-material-cost)**
- **[Actual Capacity Cost](#actual-capacity-cost)**
- **[Actual Subcontracted Cost](#actual-subcontracted-cost)**
- **[Actual Capacity Overhead Cost](#actual-capacity-overhead-cost)**
- **[Actual Manufacturing Overhead Cost](#actual-manufacturing-overhead-cost)**

This measure provides a comprehensive view of all actual costs incurred during the production process.

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Value Entry
- Item Ledger Entry

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
