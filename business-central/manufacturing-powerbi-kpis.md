---
title: Manufacturing KPIs and Measures in Power BI
description: Learn how the Manufacturing Power BI app calculates production quantities, time, capacity, costs, scrap, variances, and work-in-progress measures.
author: kennienp
ms.author: kepontop
ms.topic: reference
ms.search.keywords: reporting
ms.date: 11/12/2026
ai-usage: ai-assisted
ms.service: dynamics-365-business-central
---

# Power BI Manufacturing app KPIs and measures

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This article describes key performance indicators (KPIs), measures, and related fields in the semantic model for the Power BI Manufacturing report.

Explore the list of KPIs to learn more about how they can help you achieve your business goals. Each KPI is described, including how it's calculated and what data is used in the calculations.

For measures that convert time or capacity units, **Manufacturing Setup** supplies the **Show Capacity In** unit and **Time Factors** supplies conversion factors. Measures based on work center units also use **Work Center** data. These are dependencies in addition to the transaction data sources listed below.

## Calendar entries

### Calendar entry measures

- [Capacity (Effective)](#capacity-effective)
- [Capacity (Total)](#capacity-total)

#### Capacity (effective)

**Formula**

- Calculates the total effective capacity from the Calendar Entries table by summing up all values in the Capacity Effective column.

**Data Source**

- Calendar Entry

#### Capacity (total)

**Formula**

- Calculates total capacity by summing **Capacity Total** from **Calendar Entries**.

**Data Source**

- Calendar Entry

## Capacity ledger entries

### Capacity ledger entry measures

- [Capacity Ledger Output Quantity](#capacity-ledger-output-quantity)
- [Capacity Ledger Quantity](#capacity-ledger-quantity)
- [Direct Cost](#direct-cost)
- [Overhead Cost](#overhead-cost)
- [Run Time](#run-time)
- [Scrap %](#scrap-percent)
- [Scrap Quantity](#scrap-quantity)
- [Setup Time](#setup-time)
- [Stop Time](#stop-time)

#### Capacity ledger output quantity

**Formula**

- Calculates the total output quantity recorded in the **Capacity Ledger Entries** table by summing up all values in the **outputQuantity** column.

**Data Source**

- Capacity Ledger Entry

#### Capacity ledger quantity

**Formula**

- Calculates the total quantity recorded in the **Capacity Ledger Entries** table by summing up all values in the **Quantity** column.

**Data Source**

- Capacity Ledger Entry

#### Direct cost

**Formula**

- Calculates the cost amount actual from the **Value Entries** table, specifically filtering for entries categorized as **Direct Cost**.
This measure determines the direct cost for capacity ledger entries by summing the related value entry cost amounts.

**Data Source**

- Capacity Ledger Entry
- Value Entry

#### Overhead cost

**Formula**

- Calculates the cost amount actual from the **Value Entries** table, specifically filtering for entries categorized as **Indirect Cost**.
This measure determines the indirect cost for capacity ledger entries by summing the related value entry cost amounts.

**Data Source**

- Capacity Ledger Entry
- Value Entry

#### Run time

**Formula**

- Sums **runTime** from **Capacity Ledger Entries** after converting each entry's capacity unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Capacity Ledger Entry

#### Scrap percent

**Formula**

- Calculates the percentage of scrapped output by dividing the **Scrap Quantity** by the total **Output Quantity** recorded in the **Capacity Ledger Entries** table.

**Data Source**

- Capacity Ledger Entry

#### Scrap quantity

**Formula**

- Calculates the total amount of scrapped output recorded in the **Capacity Ledger Entries** table by summing up all values in the **scrapQuantity** column.

**Data Source**

- Capacity Ledger Entry

#### Setup time

**Formula**

- Sums **setupTime** from **Capacity Ledger Entries** after converting each entry's capacity unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Capacity Ledger Entry

#### Stop time

**Formula**

- Sums **stopTime** from **Capacity Ledger Entries** after converting each entry's capacity unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Capacity Ledger Entry

## Item ledger entries

### Item ledger entry measures

- [Consumption Quantity](#consumption-quantity)
- [Item Ledger Entry Cost Amount Actual](#item-ledger-entry-cost-amount-actual)
- [Output Quantity](#output-quantity)
- [Quantity](#quantity)

#### Consumption quantity

**Formula**

- Calculates the total [Quantity](#quantity) of item ledger entries where the **Entry Type** is **Consumption** by filtering the **Item Ledger Entries** table before summing.

**Data Source**

- Item Ledger Entry

#### Item ledger entry cost amount actual

**Formula**

- Calculates the total actual cost recorded in the **Item Ledger Entries** table by summing up all values in the **costAmountActual** column.

**Data Source**

- Item Ledger Entry

#### Output quantity

**Formula**

- Calculates the total [Quantity](#quantity) of item ledger entries where the **Entry Type** is **Output** by filtering the **Item Ledger Entries** table before summing.

**Data Source**

- Item Ledger Entry

#### Quantity

**Formula**

- Sums the values in the **Qty** column of the **Item Ledger Entries** table to calculate the total quantity across all records.

**Data Source**

- Item Ledger Entry

## Machine center

### Machine center measures

- [Machine Center Availability After Orders](#machine-center-availability-after-orders)
- [Machine Center Load](#machine-center-load)
- [Machine Center Output](#machine-center-output)
- [Machine Center Run Time](#machine-center-run-time)
- [Machine Center Scrap](#machine-center-scrap)
- [Machine Center Scrap %](#machine-center-scrap-percent)
- [Machine Center Stop %](#machine-center-stop-percent)
- [Machine Center Stop Time](#machine-center-stop-time)

#### Machine center availability after orders

**Formula**

- Calculates the remaining available capacity for machine centers by subtracting the [Machine Center Allocated Time](#machine-center-allocated-time) from the [Machine Center Capacity (Effective)](#machine-center-capacity-effective).

**Data Source**

- Prod Order Capacity Need
- Calendar Entry

#### Machine center load

**Formula**

- Calculates the ratio of allocated time to effective capacity for machine centers by dividing the [Machine Center Allocated Time](#machine-center-allocated-time) by the [Machine Center Capacity (Effective)](#machine-center-capacity-effective).

**Data Source**

- Prod Order Capacity Need
- Calendar Entry

#### Machine center output

**Formula**

- Calculates the total output quantity for machine centers by summing the **outputQuantity** column in the **Capacity Ledger Entries** table, filtered to include only rows where **Type** is **Machine Center**.

**Data Source**

- Capacity Ledger Entry

#### Machine center run time

**Formula**

- Sums **runTime** and **setupTime** from **Capacity Ledger Entries** where **Type** is **Machine Center**, converting each entry's capacity unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Capacity Ledger Entry

#### Machine center scrap

**Formula**

- Calculates the total scrap quantity for machine centers by summing the **scrapQuantity** column in the **Capacity Ledger Entries** table, filtered to include only rows where **Type** is **Machine Center**.

**Data Source**

- Capacity Ledger Entry

#### Machine center scrap percent

**Formula**

- Calculates the percentage of scrap for machine centers by dividing the [Machine Center Scrap](#machine-center-scrap) by the [Machine Center Output](#machine-center-output).

**Data Source**

- Capacity Ledger Entry

#### Machine center stop percent

**Formula**

- Calculates the percentage of stop time for machine centers by dividing the [Machine Center Stop Time](#machine-center-stop-time) by the [Machine Center Run Time](#machine-center-run-time).

**Data Source**

- Capacity Ledger Entry

#### Machine center stop time

**Formula**

- Sums **stopTime** from **Capacity Ledger Entries** where **Type** is **Machine Center**, converting each entry's capacity unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Capacity Ledger Entry

### Machine center statistics

- [Machine Center Actual Efficiency %](#machine-center-actual-efficiency-percent)
- [Machine Center Actual Need](#machine-center-actual-need)
- [Machine Center Actual Total Cost](#machine-center-actual-total-cost)
- [Machine Center Allocated Time](#machine-center-allocated-time)
- [Machine Center Capacity (Effective)](#machine-center-capacity-effective)
- [Machine Center Capacity (Total)](#machine-center-capacity-total)
- [Machine Center Expected Efficiency %](#machine-center-expected-efficiency-percent)

#### Machine center actual efficiency percent

**Formula**

- Calculates the actual efficiency for machine centers by dividing the [Machine Center Actual Need](#machine-center-actual-need) by the [Machine Center Capacity (Total)](#machine-center-capacity-total).

**Data Source**

- Capacity Ledger Entry
- Calendar Entry

#### Machine center actual need

**Formula**

- Sums **setupTime**, **runTime**, and **stopTime** from **Capacity Ledger Entries** where **Type** is **Machine Center**, converting each entry's capacity unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Capacity Ledger Entry

#### Machine center actual total cost

**Formula**

- Calculates the total actual cost for machine centers by adding the [Direct Cost](#direct-cost) and [Overhead Cost](#overhead-cost) measures, filtered to include only rows in the **Capacity Ledger Entries** table where **Type** is **Machine Center**.

**Data Source**

- Capacity Ledger Entry
- Value Entry

#### Machine center allocated time

**Formula**

- Sums **allocatedTime** from **Prod Order Capacity Need** where **Type** is **Machine Center** and **Requested Only** is **FALSE**, converting each work center's unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Prod Order Capacity Need

#### Machine center capacity (effective)

**Formula**

- Sums **Capacity Effective** from **Calendar Entries** where **Capacity Type** is **Machine Center**, converting each work center's unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Calendar Entry

#### Machine center capacity (total)

**Formula**

- Sums **Capacity Total** from **Calendar Entries** where **Capacity Type** is **Machine Center**, converting each work center's unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Calendar Entry

#### Machine center expected efficiency percent

**Formula**

- Calculates the expected efficiency for machine centers by dividing the [Machine Center Capacity (Effective)](#machine-center-capacity-effective) by the [Machine Center Capacity (Total)](#machine-center-capacity-total).

**Data Source**

- Calendar Entry

## Prod order capacity need

### Prod order capacity need measures

- [Allocated Time](#allocated-time)
- [Needed Time](#needed-time)
- [Needed Time (MS)](#needed-time-ms)

#### Allocated time

**Formula**

- Sums **allocatedTime** from **Prod Order Capacity Need** where **Requested Only** is **FALSE**, converting each work center's unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Prod Order Capacity Need

#### Needed time

**Formula**

- Divides [Needed Time (MS)](#needed-time-ms) by the **Time Factor** for the **Show Capacity In** unit selected in **Manufacturing Setup**.

**Data Source**

- Prod Order Capacity Need

#### Needed time (MS)

**Formula**

- Sums **neededTimeMs** from **Prod Order Capacity Need**. The result is in milliseconds; conversion to the selected capacity unit is performed by [Needed Time](#needed-time).

**Data Source**

- Prod Order Capacity Need
- Manufacturing Setup

## Prod order components

### Prod order component measures

- [Prod Order Component Cost Amount](#prod-order-component-cost-amount)
- [Prod Order Component Expected Qty. (Base)](#prod-order-component-expected-qty-base)
- [Prod Order Component Remaining Qty. (Base)](#prod-order-component-remaining-qty-base)

#### Prod order component cost amount

**Formula**

- Calculates the total cost of production order components by summing the **costAmount** column in the **Prod Order Components** table.

**Data Source**

- Prod Order Component

#### Prod order component expected qty. (base)

**Formula**

- Calculates the total expected quantity (in base units) of production order components by summing the **expectedQtyBase** column in the **Prod Order Components** table.

**Data Source**

- Prod Order Component

#### Prod order component remaining qty. (base)

**Formula**

- Calculates the total remaining quantity (in base units) of production order components by summing the **remainingQtyBase** column in the **Prod Order Components** table.

**Data Source**

- Prod Order Component

## Prod order routing lines

### Prod order routing measures

- [Expected Operation Cost](#expected-operation-cost)
- [Operation Move Time](#operation-move-time)
- [Operation Run Time](#operation-run-time)
- [Operation Setup Time](#operation-setup-time)
- [Operation Wait Time](#operation-wait-time)
- [Posted Output Quantity](#posted-output-quantity)
- [Prod Order Routing Expected Capacity Need](#prod-order-routing-expected-capacity-need)
- [Prod Order Routing Expected Capacity Ovhd. Cost](#prod-order-routing-expected-capacity-ovhd-cost)
- [Prod Order Routing Expected Operation Cost Amt.](#prod-order-routing-expected-operation-cost-amt)
- [Total Duration Days](#total-duration-days)
- [Total Duration Hours](#total-duration-hours)

#### Expected operation cost

**Formula**

- Calculates the total expected operational cost by using `SUMX` to iterate over the **Prod Order Routing Lines** table and summing the difference between **Expected Operation Cost Amt.** and **Expected Capacity Ovhd. Cost** for each row.

**Data Source**

- Prod Order Routing Line

#### Operation move time

**Formula**

- Calculates the total move time for production order routing lines by summing the **Move Time** column in the **Prod Order Routing Lines** table.

**Data Source**

- Prod Order Routing Line

#### Operation run time

**Formula**

- Calculates the total run time for production order routing lines by summing the **Run Time** column in the **Prod Order Routing Lines** table.

**Data Source**

- Prod Order Routing Line

#### Operation setup time

**Formula**

- Calculates the total setup time for production order routing lines by summing the **Setup Time** column in the **Prod Order Routing Lines** table.

**Data Source**

- Prod Order Routing Line

#### Operation wait time

**Formula**

- Calculates the total wait time for production order routing lines by summing the **Wait Time** column in the **Prod Order Routing Lines** table.

**Data Source**

- Prod Order Routing Line

#### Posted output quantity

**Formula**

- Sums Output Quantity column from the Capacity Ledger Entry table only for entries whose (Routing No., Order No., Operation No., Routing Reference No.) match the distinct Prod Order Routing Lines in the current filter context.

#### Prod order routing expected capacity need

**Formula**

- Calculates the total expected capacity requirement for production order routing lines by summing the **Expected Capacity Need** column in the **Prod Order Routing Lines** table.

**Data Source**

- Prod Order Routing Line

#### Prod order routing expected capacity ovhd. cost

**Formula**

- Calculates the total expected capacity overhead cost for production order routing lines by summing the **Expected Capacity Ovhd. Cost** column in the **Prod Order Routing Lines** table.

**Data Source**

- Prod Order Routing Line

#### Prod order routing expected operation cost amt

**Formula**

- Calculates the total expected operation cost amount for production order routing lines by summing the **Expected Operation Cost Amt.** column in the **Prod Order Routing Lines** table.

**Data Source**

- Prod Order Routing Line

#### Total duration days

**Formula**

- Calculates the total duration of production order routing lines in days by summing the **Duration Total Days** column in the **Prod Order Routing Lines** table. The **Duration Total Days** column is calculated in Power Query from the **Starting Date Time** and **Ending Date Time** fields on the **Prod Order Routing Line**.

**Data Source**

- Prod Order Routing Line

#### Total duration hours

**Formula**

- Calculates the total duration of production order routing lines in hours by summing the **Duration Total Hours** column in the **Prod Order Routing Lines** table. The **Duration Total Hours** column is calculated in Power Query from the **Starting Date Time** and **Ending Date Time** fields on the **Prod Order Routing Line**.

**Data Source**

- Prod Order Routing Line

## Production order lines

### Production order line measures

- [Finished Quantity (Base)](#finished-quantity-base)
- [Quantity (Base)](#quantity-base)
- [Remaining Quantity (Base)](#remaining-quantity-base)

#### Finished quantity (base)

**Formula**

- Calculates the total finished quantity in base units for production order lines by summing the **finishedQtyBase** column in the **Production Order Lines** table.

**Data Source**

- Prod. Order Line

#### Quantity (base)

- Calculates the total quantity in base units for production order lines by summing the **quantityBase** column in the **Production Order Lines** table.

**Data Source**

- Prod. Order Line

#### Remaining quantity (base)

**Formula**

- Calculates the total remaining quantity in base units for production order lines by summing the **remainingQtyBase** column in the **Production Order Lines** table.

**Data Source**

- Prod. Order Line

## Production orders

### Production order measures

- [Actual Time Used](#actual-time-used)
- [Average Production Time Per Finished Quantity](#average-production-time-per-finished-quantity)
- [Expected Production Order Scrap Quantity](#expected-production-order-scrap-quantity)
- [Finished %](#finished-percent)
- [No. of Production Orders](#no-of-production-orders)
- [Planned Quantity](#planned-quantity)
- [Production Order Scrap Quantity](#production-order-scrap-quantity)
- [Remaining %](#remaining-percent)
- [Variance Quantity](#variance-quantity)

#### Actual time used

**Formula**

- Sums **quantity** from **Capacity Ledger Entries** for production orders with a nonzero [Finished Quantity](#finished-quantity), converting each entry's capacity unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**. It sums the results across production orders and returns blank when the result is zero.

**Data Source**

- Capacity Ledger Entry
- Production Order

#### Average production time per finished quantity

**Formula**

- Calculates the average time spent on production per finished quantity by dividing the [Actual Time Used](#actual-time-used) by the [Finished Quantity](#finished-quantity).

**Data Source**

- Capacity Ledger Entry
- Production Order

#### Expected production order scrap quantity

**Formula**

- Calculates the expected scrap quantity for production orders by multiplying the [Finished Quantity](#finished-quantity) by the **Prod Order Source No. Scrap %** for the selected production order.

**Data Source**

- Production Order
- Item
- Item Ledger Entries

#### Finished percent

**Formula**

- Calculates the percentage of finished quantity relative to the planned quantity by dividing the [Finished Quantity](#finished-quantity) by the [Planned Quantity](#planned-quantity).

**Data Source**

- Production Order
- Item Ledger Entry

#### Finished quantity

**Formula**

- Sums **qty** from **Item Ledger Entries** where **Entry Type** is **Output**, applying production order and order line filters to **Production Order Lines** and restricting those lines to **Planning Level Code** 0.

**Data Source**

- Production Order
- Item Ledger Entry
- Prod. Order Line

#### No. of production orders

**Formula**

- Counts nonblank entries in the **Production Order** column of **Production Orders** using `COUNT`, not a distinct count.

**Data Source**

- Production Order

#### Planned quantity

**Formula**

- Sums **quantityBase** from **Production Order Lines**.

**Data Source**

- Prod. Order Line

#### Production order scrap quantity

**Formula**

- Sums **scrapQuantity** from **Capacity Ledger Entries**, applying production order and order line filters to **Production Order Lines** and restricting those lines to **Planning Level Code** 0.

**Data Source**

- Capacity Ledger Entry
- Prod. Order Line

#### Production order scrap percent

**Formula**

- Divides [Production Order Scrap Quantity](#production-order-scrap-quantity) by [Finished Quantity](#finished-quantity).

**Data Source**

- Item Ledger Entry
- Capacity Ledger Entry
- Prod. Order Line

#### Remaining percent

**Formula**

- Calculates the remaining percentage of the planned quantity that hasn't been finished. It checks whether the [Finished Quantity](#finished-quantity) is less than the [Planned Quantity](#planned-quantity). If it is, it returns the negative of the [Variance Quantity](#variance-quantity) divided by the [Planned Quantity](#planned-quantity). If the finished quantity is greater than or equal to the planned quantity, it returns **BLANK**.

**Data Source**

- Item Ledger Entry
- Production Order

#### Variance quantity

**Formula**

- Subtracts [Planned Quantity](#planned-quantity) from [Finished Quantity](#finished-quantity), indicating a surplus or deficit relative to the plan. Returns blank when the difference is zero.

**Data Source**

- Item Ledger Entry
- Production Order
- Prod. Order Line

### Production order statistics

#### Actual costs

- [Actual Capacity Cost](#actual-capacity-cost)
- [Actual Capacity Overhead Cost](#actual-capacity-overhead-cost)
- [Actual Manufacturing Overhead Cost](#actual-manufacturing-overhead-cost)
- [Actual Material Cost](#actual-material-cost)
- [Actual Subcontracted Cost](#actual-subcontracted-cost)
- [Total Actual Cost](#total-actual-cost)

##### Actual capacity cost

**Formula**

Calculates the actual cost of capacity usage based on production order lines and related inventory adjustments. Here's a breakdown of the calculation:

1. **Variables for Production Order Details**:
   The measure defines variables for the **Production Order Number**, **Production Order Line Number**, **Item Number**, and **Production Order Status** from the **Production Order Lines** table.

2. **Inventory Adjustment Lines**:
   It then creates a table of relevant inventory adjustment lines that correspond to the current production order line, with the condition that the **iSFinished** status is set to **TRUE** if the production order status is **Finished**.

3. **Inventory Adjustment Details**:
   The measure selects the order number, item number, and order line number from the inventory adjustment lines.

4. **Capacity Ledger Entries**:
   It then filters the **Capacity Ledger Entries** table to match the **Order No.**, **Order Line No.**, and **Item No.** from the inventory adjustments and ensures **Subcontracting** is excluded.

5. **Return the Actual Capacity Cost**:
   Finally, the measure calculates the sum of **directCost** from the **Capacity Ledger Entries** table, dividing it by the **ShareOfCapCost** measure to account for the specific share of capacity costs.

This complex calculation ties together various production and inventory details to derive the actual capacity cost for the production orders.

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)

##### Actual capacity overhead cost

**Formula**

- Calculates the total overhead cost recorded in capacity ledger entries by summing the **overheadCost** column in the **Capacity Ledger Entries** table.

**Data Source**

- Capacity Ledger Entry

##### Actual manufacturing overhead cost

**Formula**

Calculates the total overhead cost incurred during manufacturing by combining indirect cost percentages and per-unit overhead rates with actual production metrics. Here's how it works:

1. **IndirectCost**:
   It sums the **indirectCostPercent** values across all production order lines.

2. **OverheadRate**:
   It sums the **overheadRate** values across all production order lines.

3. **OutputQty**:
   It calculates the total output quantity from the **Item Ledger Entries** table, filtered to include only entries of type **"Output"**, and scoped to the currently selected production order.

4. **Final Calculation**:
   The measure multiplies the sum of the following by the **IndirectCost** percentage (converted from percent to decimal), and then adds the product of **OutputQty** and **OverheadRate**.

   - [Actual Material Cost](#actual-material-cost)
   - [Actual Capacity Cost](#actual-capacity-cost)
   - [Actual Subcontracted Cost](#actual-subcontracted-cost)
   - [Actual Capacity Overhead Cost](#actual-capacity-overhead-cost)

This measure captures both proportional overhead based on other costs and fixed overhead based on output volume.

**Data Sources**

- Prod. Order Line
- Item Ledger Entry
- Capacity Ledger Entry
- Value Entry

##### Actual material cost

**Formula**

Calculates the total material cost consumed in production by summing the **costAmountActual** from the **Value Entries** table, filtered to:

- Exclude entries where **entryType** is **Rounding**.
- Include only entries where **Item Ledger Entry Type** is **Consumption**.

The result is then multiplied by **-1** to reflect material consumption as a cost.

**Data Source**

- Value Entry

##### Actual subcontracted cost

**Formula**
Calculates the total direct cost of subcontracted work associated with production orders. Here's how it works:

1. **Context per Line**:
   For each row in the **Production Order Lines** table, it defines key variables:

   - ProdOrderNo
   - ProdOrderLineNo
   - ProdOrderItem
   - ProdOrderStatus

2. **Inventory Adjustment Matching**:
   It retrieves matching rows from **Inventory Adjustment Entry Order Line**, where:

   - THe order number, line number, and item match the production order line variables.
   - The **iSFinished** flag corresponds to whether the production order is marked as **Finished**.

3. **Subcontracted Capacity Ledger Entries**:
   It then filters the **Capacity Ledger Entries** table to:

   - Match the order number, order line number, and item number from the inventory adjustment.
   - Include only entries where **Subcontracting** is **TRUE**.

4. **Cost Calculation**:
   It calculates the total **directCost** from these filtered subcontracted capacity ledger entries and divides it by the **ShareOfCapCost** measure.

5. **Aggregation**:
   `SUMX` iterates this logic over all production order lines, returning the total actual subcontracted cost.

This measure isolates and aggregates costs related to subcontracted operations.

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)

##### Total actual cost

**Formula**

Calculates the full cost of production by summing the following measures:

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

#### Capacity need

- [Prod Order Actual Capacity Need](#prod-order-actual-capacity-need)
- [Prod Order Capacity Need Dev %](#prod-order-capacity-need-dev-percent)
- [Prod Order Capacity Need Variance](#prod-order-capacity-need-variance)
- [Prod Order Expected Capacity Need](#prod-order-expected-capacity-need)
- [Prod Order Expected Capacity Need (Finished)](#prod-order-expected-capacity-need-finished)
- [Prod Order Expected Capacity Need (Non Finished)](#prod-order-expected-capacity-need-non-finished)

##### Prod order actual capacity need

**Formula**

Calculates the actual capacity used for production orders, converted into the unit of measure specified in the manufacturing setup. Here's how it works:

1. **Manufacturing Time Factor**:
   Retrieves the appropriate time factor from the **Time Factors** table based on the capacity unit defined in the **Manufacturing Setup**.

2. **Quantity Calculation** (`Qty` variable):
   Iterates over filtered *Capacity Ledger Entries* (excluding subcontracting), and for each row:

   - Determines the **Qty Per Capacity Unit of Measure** (defaulting to 1 if zero).
   - Looks up the appropriate **Time Factor**:

     - If the **Qty Per Capacity Unit of Measure** is zero, it uses the time factor based on the work center’s unit of measure. Otherwise, it uses the time factor based on the entry's own capacity unit.
     - Computes the adjusted quantity as `quantity / QtyPerCapUnitOfMeasure * TimeFactor`.

3. **Final Conversion**:
   Divides the total adjusted quantity by the **Manufacturing Time Factor** to express it in the target unit.

This measure provides a standardized view of how much capacity was actually used, accounting for differences in units and time factors across capacity entries.

**Data Source**

- Capacity Ledger Entry
- Manufacturing Setup

##### Prod order capacity need dev percent

**Formula**

- Calculates the percentage deviation in capacity need by dividing the [Prod Order Capacity Need Variance](#prod-order-capacity-need-variance) by the [Prod Order Expected Capacity Need](#prod-order-expected-capacity-need). This measure indicates how much the actual capacity usage differs from the expected need, expressed as a percentage.

**Data Source**

- Prod Order Routing Line
- Prod Order Capacity Need
- Capacity Ledger Entry
- Manufacturing Setup

##### Prod order capacity need variance

**Formula**

- Calculates the difference between the actual and expected capacity need for a production order by subtracting the [Prod Order Expected Capacity Need](#prod-order-expected-capacity-need) from the [Prod Order Actual Capacity Need](#prod-order-actual-capacity-need). This measure quantifies how much more or less capacity was used than originally planned.

**Data Sources**

- Prod Order Routing Line
- Prod Order Capacity Need
- Capacity Ledger Entry
- Manufacturing Setup

##### Prod order expected capacity need

**Formula**

Returns the appropriate expected capacity need based on the status of the production order:

- If the **Prod Order Status** is **"Finished"**, it returns [Prod Order Expected Capacity Need (Finished)](#prod-order-expected-capacity-need-finished).
- For all other statuses, it returns [Prod Order Expected Capacity Need (Non Finished)](#prod-order-expected-capacity-need-non-finished).

The measure reflects different logic depending on whether the production order is completed or still in progress.

**Data Source**

- Prod Order Routing Line
- Prod Order Capacity Need
- Manufacturing Setup

##### Prod order expected capacity need (finished)

**Formula**

Calculates the expected capacity required for **finished** production orders, adjusted to a standardized unit of measure. Here's how it works:

1. **Time Factor**:
   Retrieves the time conversion factor from the **Time Factors** table based on the unit configured in the **Manufacturing Setup**.

2. **Expected Capacity Need**:
   Sums the **Expected Capacity Need** from the **Prod Order Routing Lines** table, filtering for:

   - Production orders with status **"Finished"**.
   - Work centers that are **not subcontractors**.

3. **Conversion**:
   Divides the total expected capacity by the **Time Factor** to express the result in the standard capacity unit.

This measure provides a normalized view of planned capacity usage for completed production orders, excluding subcontracted operations.

**Data Source**

- Prod Order Routing Line
- Manufacturing Setup

##### Prod order expected capacity need (non finished)

**Formula**

Calculates the expected capacity required for **non-finished** production orders, adjusted to a standardized unit of measure. Here's how it works:

1. **Time Factor**:
   Retrieves the time conversion factor from the **Time Factors** table based on the unit defined in the **Manufacturing Setup**.

2. **Expected Capacity Need**:
   Sums the **neededTimeMs** from the **Prod Order Capacity Need** table, filtering for:

   - Production orders with a status **not equal to** **Finished**.
   - Work centers that are **not subcontractors**. For example, **Work Center Subcontractor No.** is blank.

3. **Conversion**:
   Divides the total **neededTimeMs** by the **Time Factor** to express the result in the standard capacity unit.

This measure provides a normalized view of the planned capacity usage for ongoing or unfinished production orders, excluding subcontracted operations.

**Data Source**

- Prod Order Capacity Need
- Manufacturing Setup

#### Expected costs

- [Expected Capacity Cost](#expected-capacity-cost)
- [Expected Capacity Overhead Cost](#expected-capacity-overhead-cost)
- [Expected Manufacturing Overhead Cost](#expected-manufacturing-overhead-cost)
- [Expected Material Cost](#expected-material-cost)
- [Expected Subcontracted Cost](#expected-subcontracted-cost)
- [Total Expected Cost](#total-expected-cost)

##### Expected capacity cost

**Formula**

- Calculates the net expected cost of in-house capacity usage by subtracting [Expected Subcontracted Cost](#expected-subcontracted-cost) from [Expected Operation Cost](#expected-operation-cost).

**Data Source**

- Prod Order Line
- Prod Order Routing Line
- Prod Order Component

##### Expected capacity overhead cost

**Formula**

- Calculates the total overhead cost expected from capacity usage by summing the **Expected Capacity Ovhd. Cost** field from the **Prod Order Routing Lines** table. This represents the anticipated indirect costs associated with capacity operations in the production process.

**Data Source**

- Prod Order Routing Line

##### Expected manufacturing overhead cost

**Formula**

The **Expected Manufacturing Overhead Cost** measure calculates the total manufacturing overhead cost for a production order by:

1. **Retrieving Direct Cost**:
   It uses the variable **ExpMfgDirCost**, which represents the expected manufacturing direct cost.
     - **ExpMfgDirCost** = [Expected Material Cost](#expected-material-cost) + [Expected Capacity Cost](#expected-capacity-cost) + [Expected Subcontracted Cost](#expected-subcontracted-cost) + [Expected Capacity Overhead Cost](#expected-capacity-overhead-cost)

2. **Iterating Over Production Order Lines**:
   For each line, it adds:

   - The value of **ExpOvhdCost**: Calculated by iterating over each row in the **Production Order Lines** table. Multiplying the **overheadRate** by the **quantityBase**.
   - A percentage-based overhead component, calculated as the line’s **indirectCostPercent** multiplied by the total **ExpMfgDirCost**, divided by **100**.

3. **Summing the Result**:
   `SUMX` aggregates the per-line overhead contributions into a total.

**Data Source**

- Prod. Order Line
- Prod Order Routing Line
- Prod Order Components

##### Expected material cost

**Formula**

- Calculates the total expected cost of materials for a production order by summing the **costAmount** field from the **Prod Order Components** table. This represents the projected material expense based on the components planned for use.

**Data Source**

- Prod Order Component

##### Expected subcontracted cost

**Formula**

Estimates the portion of expected capacity cost attributed to subcontracted operations by:

1. **Identifying Subcontracting Work Centers**:
   Filters the **Work Center** table to include only those with a **Subcontractor No.**. For example, subcontracted operations.

2. **Calculating Expected Operation Cost for Subcontracting**:
   Computes [Expected Operation Cost](#expected-operation-cost) restricted to those subcontracting work centers.

3. **Determining Share of Total Capacity Cost**:
   Retrieves the **ShareOfTotalCapCost** for the current production order from the **Production Order Lines** table.

4. **Final Calculation**:
   Multiplies the **Expected Operation Cost for Subcontracting** by the order’s share of total capacity cost.

**Data Source**

- Prod Order Line
- Prod Order Routing Line
- Prod Order Component

##### Total expected cost

Calculates the overall anticipated cost of a production order by summing the following components:

- [Expected Material Cost](#expected-material-cost)
- [Expected Capacity Cost](#expected-capacity-cost)
- [Expected Subcontracted Cost](#expected-subcontracted-cost)
- [Expected Capacity Overhead Cost](#expected-capacity-overhead-cost)
- [Expected Manufacturing Overhead Cost](#expected-manufacturing-overhead-cost)

This measure provides a complete view of all expected production costs, combining direct and indirect, in-house and subcontracted expenses.

**Data Source**

- Prod Order Line
- Prod Order Routing Line

##### Variance to expected cost

- [Expected Capacity Cost Variance](#expected-capacity-cost-variance)
- [Expected Capacity Overhead Cost Variance](#expected-capacity-overhead-cost-variance)
- [Expected Manufacturing Overhead Cost Variance](#expected-manufacturing-overhead-cost-variance)
- [Expected Material Cost Variance](#expected-material-cost-variance)
- [Expected Subcontracted Cost Variance](#expected-subcontracted-cost-variance)
- [Total Expected Cost Variance](#total-expected-cost-variance)

###### Expected capacity cost variance

**Formula**

- Calculates the difference between the [Actual Capacity Cost](#actual-capacity-cost) and [Expected Capacity Cost](#expected-capacity-cost).

**Data Source**

- Prod Order Line
- Prod Order Routing Line
- Prod Order Component
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)

###### Expected capacity overhead cost variance

**Formula**

- Calculates the difference between [Actual Capacity Overhead Cost](#actual-capacity-overhead-cost) and [Expected Capacity Overhead Cost](#expected-capacity-overhead-cost).

**Data Source**

- Capacity Ledger Entry
- Prod Order Routing Line

###### Expected manufacturing overhead cost variance

**Formula**

- Calculates the difference between [Actual Manufacturing Overhead Cost](#actual-manufacturing-overhead-cost) and [Expected Manufacturing Overhead Cost](#expected-manufacturing-overhead-cost).

**Data Source**

- Prod. Order Line
- Item Ledger Entry
- Capacity Ledger Entry
- Value Entry
- Prod Order Routing Line
- Prod Order Component

###### Expected material cost variance

**Formula**

- Calculates the difference between [Actual Material Cost](#actual-material-cost) and [Expected Material Cost](#expected-material-cost).

**Data Source**

- Value Entry
- Prod Order Component

###### Expected subcontracted cost variance

**Formula**

- Calculates the difference between [Actual Subcontracted Cost](#actual-subcontracted-cost) and [Expected Subcontracted Cost](#expected-subcontracted-cost).

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Prod Order Routing Line
- Prod Order Component

###### Total expected cost variance

**Formula**

Calculates the overall difference between actual and expected costs by summing the following sub-measures:

- [Expected Material Cost Variance](#expected-material-cost-variance)
- [Expected Capacity Cost Variance](#expected-capacity-cost-variance)
- [Expected Subcontracted Cost Variance](#expected-subcontracted-cost-variance)
- [Expected Capacity Overhead Cost Variance](#expected-capacity-overhead-cost-variance)
- [Expected Manufacturing Overhead Cost Variance](#expected-manufacturing-overhead-cost-variance)

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Prod Order Routing Line
- Prod Order Component
- Value Entry
- Item Ledger Entry

##### Variance to expected cost deviation %

- [Expected Capacity Cost Dev %](#expected-capacity-cost-dev-percent)
- [Expected Capacity Overhead Cost Dev %](#expected-capacity-overhead-cost-dev-percent)
- [Expected Manufacturing Overhead Cost Dev %](#expected-manufacturing-overhead-cost-dev-percent)
- [Expected Material Cost Dev %](#expected-material-cost-dev-percent)
- [Expected Subcontracted Cost Dev %](#expected-subcontracted-cost-dev-percent)
- [Total Expected Cost Dev %](#total-expected-cost-dev-percent)

###### Expected capacity cost dev percent

**Formula**

- Calculates the percentage deviation between actual and expected capacity cost by dividing [Expected Capacity Cost Variance](#expected-capacity-cost-variance) by [Expected Capacity Cost](#expected-capacity-cost).

**Data Source**

- Prod Order Line
- Prod Order Routing Line
- Prod Order Component
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)

###### Expected capacity overhead cost dev percent

**Formula**

- Calculates the percentage deviation between actual and expected capacity overhead costs by dividing [Expected Capacity Overhead Cost Variance](#expected-capacity-overhead-cost-variance) by [Expected Capacity Overhead Cost](#expected-capacity-overhead-cost).

**Data Source**

- Capacity Ledger Entry
- Prod Order Routing Line

###### Expected manufacturing overhead cost dev percent

**Formula**

- Calculates the percentage deviation between actual and expected manufacturing overhead costs by dividing [Expected Manufacturing Overhead Cost Variance](#expected-manufacturing-overhead-cost-variance) by [Expected Manufacturing Overhead Cost](#expected-manufacturing-overhead-cost).

**Data Source**

- Prod. Order Line
- Item Ledger Entry
- Capacity Ledger Entry
- Value Entry
- Prod Order Routing Line
- Prod Order Component

###### Expected material cost dev percent

**Formula**

- Calculates the percentage deviation between actual and expected material costs by dividing [Expected Material Cost Variance](#expected-material-cost-variance) by [Expected Material Cost](#expected-material-cost).

**Data Source**

- Value Entry
- Prod Order Component

###### Expected subcontracted cost dev percent

**Formula**

- Calculates the percentage deviation between actual and expected subcontracted costs by dividing the [Expected Subcontracted Cost Variance](#expected-subcontracted-cost-variance) by [Expected Subcontracted Cost](#expected-subcontracted-cost).

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Prod Order Routing Line
- Prod Order Component

###### Total expected cost dev percent

**Formula**

- Calculates the overall percentage deviation between actual and expected total costs by dividing the [Total Expected Cost Variance](#total-expected-cost-variance) by the [Total Expected Cost](#total-expected-cost).

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Prod Order Routing Line
- Prod Order Component
- Value Entry
- Item Ledger Entry

#### Standard costs

- [Standard Capacity Cost](#standard-capacity-cost)
- [Standard Capacity Overhead Cost](#standard-capacity-overhead-cost)
- [Standard Manufacturing Overhead Cost](#standard-manufacturing-overhead-cost)
- [Standard Material Cost](#standard-material-cost)
- [Standard Subcontracted Cost](#standard-subcontracted-cost)
- [Total Standard Cost](#total-standard-cost)

##### Standard capacity cost

**Formula**

Calculates the standard capacity cost for production order lines, using either item master data or finalized inventory adjustments:

- For each production order line:
  - If the line is fully invoiced, use the finished quantity multiplied by the single-level capacity cost from the inventory adjustment.
  - Otherwise, use the quantity **Base from Production Order Lines** multiplied by the **Item Single-Level Capacity Cost** from the **Item Card**.

**Data Source**

- Prod Order Line
- Inventory Adjmt. Entry (Order)
- Item

##### Standard capacity overhead cost

**Formula**

Calculates the standard capacity overhead cost for each production order line, using either item master data or finalized inventory adjustments:

- For each production order line:
  - If fully invoiced, multiply the finished quantity by the single-level capacity overhead cost from the inventory adjustment entry.
  - Otherwise, use the quantity **Base from Production Order Lines** multiplied by the **Item Single-Level Cap. Ovhd Cost** from the **Item Card**.

**Data Source**

- Prod Order Line
- Inventory Adjmt. Entry (Order)
- Item

##### Standard manufacturing overhead cost

**Formula**

Calculates the standard manufacturing overhead cost for each production order line, using either finalized inventory adjustment data or standard item-level overhead rates.

- For each production order line:
  - If the line is fully invoiced, multiply the finished quantity by the single-level manufacturing overhead cost from the inventory adjustment.
  - Otherwise, use the quantity **Base from Production Order Lines** multiplied by the **Item Single-Level Mfg. Ovhd Cost** from the **Item Card**.

**Data Source**

- Prod Order Line
- Inventory Adjmt. Entry (Order)
- Item

##### Standard material cost

**Formula**

Calculates the standard material cost for each production order line based on either finalized inventory adjustments or item-level standard costs:

- For each production order line:
  - If the line is fully invoiced, multiply the finished quantity by the single-level material cost from the inventory adjustment entry.
  - Otherwise, use the quantity **Base from Production Order Lines** multiplied by the **Item Single-Level Material Cost** from the **Item Card**.

**Data Source**

- Prod Order Line
- Inventory Adjmt. Entry (Order)
- Item

##### Standard subcontracted cost

**Formula**

Calculates the standard subcontracted cost for each production order line based on either finalized inventory adjustments or item-level standard costs:

- For each production order line:
  - If the line is fully invoiced, multiply the finished quantity by the single-level subcontracted cost from the inventory adjustment entry.
  - Otherwise, use the quantity **Base from Production Order Lines** multiplied by the **Item Single-Level Subcontrd. Cost** from the **Item Card**.

**Data Source**

- Prod Order Line
- Inventory Adjmt. Entry (Order)
- Item

##### Total standard cost

**Formula**

Sums up the various standard cost components associated with a production order. The measure calculates the total standard cost by adding up the following:

- [Standard Material Cost](#standard-material-cost)
- [Standard Capacity Cost](#standard-capacity-cost)
- [Standard Capacity Overhead Cost](#standard-capacity-overhead-cost)
- [Standard Manufacturing Overhead Cost](#standard-manufacturing-overhead-cost)
- [Standard Subcontracted Cost](#standard-subcontracted-cost)

**Data Source**

- Prod Order Line
- Inventory Adjmt. Entry (Order)
- Item

##### Variance to standard cost

- [Standard Capacity Cost Variance](#standard-capacity-cost-variance)
- [Standard Capacity Overhead Cost Variance](#standard-capacity-overhead-cost-variance)
- [Standard Manufacturing Overhead Cost Variance](#standard-manufacturing-overhead-cost-variance)
- [Standard Material Cost Variance](#standard-material-cost-variance)
- [Standard Subcontracted Cost Variance](#standard-subcontracted-cost-variance)
- [Total Standard Cost Variance](#total-standard-cost-variance)

###### Standard capacity cost variance

**Formula**

Calculates the difference between the [Actual Capacity Cost](#actual-capacity-cost) and [Standard Capacity Cost](#standard-capacity-cost).

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Item

###### Standard capacity overhead cost variance

**Formula**

Calculates the difference between the [Actual Capacity Overhead Cost](#actual-capacity-overhead-cost) and [Standard Capacity Overhead Cost](#standard-capacity-overhead-cost).

**Data Source**

- Capacity Ledger Entry
- Prod Order Line
- Inventory Adjmt. Entry (Order)
- Item

###### Standard manufacturing overhead cost variance

**Formula**

Calculates the difference between the [Actual Manufacturing Overhead Cost](#actual-manufacturing-overhead-cost) and [Standard Manufacturing Overhead Cost](#standard-manufacturing-overhead-cost).

**Data Source**

- Prod. Order Line
- Item Ledger Entry
- Capacity Ledger Entry
- Value Entry
- Inventory Adjmt. Entry (Order)
- Item

###### Standard material cost variance

**Formula**

Calculates the difference between the [Actual Material Cost](#actual-material-cost) and [Standard Material Cost](#standard-material-cost).

**Data Source**

- Value Entry
- Prod Order Line
- Inventory Adjmt. Entry (Order)
- Item

###### Standard subcontracted cost variance

**Formula**

Calculates the difference between the [Actual Subcontracted Cost](#actual-subcontracted-cost) and [Standard Subcontracted Cost](#standard-subcontracted-cost).

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Item

###### Total standard cost variance

**Formula**

Calculates the total deviation from standard costs by summing the following individual variances:

- [Standard Material Cost Variance](#standard-material-cost-variance)
- [Standard Capacity Cost Variance](#standard-capacity-cost-variance)
- [Standard Subcontracted Cost Variance](#standard-subcontracted-cost-variance)
- [Standard Capacity Overhead Cost Variance](#standard-capacity-overhead-cost-variance)
- [Standard Manufacturing Overhead Cost Variance](#standard-manufacturing-overhead-cost-variance)

**Data Source**

- Prod. Order Line
- Item Ledger Entry
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Item
- Value Entry

##### Variance to standard cost deviation %

- [Standard Capacity Cost Dev %](#standard-capacity-cost-dev-percent)
- [Standard Capacity Overhead Cost Dev %](#standard-capacity-overhead-cost-dev-percent)
- [Standard Manufacturing Overhead Cost Dev %](#standard-manufacturing-overhead-cost-dev-percent)
- [Standard Material Cost Dev %](#standard-material-cost-dev-percent)
- [Standard Subcontracted Cost Dev %](#standard-subcontracted-cost-dev-percent)
- [Total Standard Cost Dev %](#total-standard-cost-dev-percent)

###### Standard capacity cost dev percent

**Formula**

Calculates the percentage deviation between the actual and standard capacity costs by dividing the [Standard Capacity Cost Variance](#standard-capacity-cost-variance) by the [Standard Capacity Cost](#standard-capacity-cost).

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Item

###### Standard capacity overhead cost dev percent

**Formula**

Calculates the percentage deviation between the actual and standard capacity overhead costs by dividing the [Standard Capacity Overhead Cost Variance](#standard-capacity-overhead-cost-variance) by the [Standard Capacity Overhead Cost](#standard-capacity-overhead-cost).

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Item

###### Standard manufacturing overhead cost dev percent

**Formula**

Calculates the percentage deviation between the actual and standard manufacturing overhead costs by dividing the [Standard Manufacturing Overhead Cost Variance](#standard-manufacturing-overhead-cost-variance) by the [Standard Manufacturing Overhead Cost](#standard-manufacturing-overhead-cost).

**Data Source**

- Prod. Order Line
- Item Ledger Entry
- Capacity Ledger Entry
- Value Entry
- Inventory Adjmt. Entry (Order)
- Item

###### Standard material cost dev percent

**Formula**

Calculates the percentage deviation between the actual and standard material costs by dividing the [Standard Material Cost Variance](#standard-material-cost-variance) by the [Standard Material Cost](#standard-material-cost).

**Data Source**

- Prod. Order Line
- Value Entry
- Inventory Adjmt. Entry (Order)
- Item

###### Standard subcontracted cost dev percent

**Formula**

Calculates the percentage deviation between the actual and standard subcontracted costs by dividing the [Standard Subcontracted Cost Variance](#standard-subcontracted-cost-variance) by the [Standard Subcontracted Cost](#standard-subcontracted-cost).

**Data Source**

- Prod. Order Line
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Item

###### Total standard cost dev percent

**Formula**

Calculates the overall percentage deviation between actual and standard total costs by dividing the [Total Standard Cost Variance](#total-standard-cost-variance) by the [Total Standard Cost](#total-standard-cost).

**Data Source**

- Prod. Order Line
- Item Ledger Entry
- Capacity Ledger Entry
- Inventory Adjmt. Entry (Order)
- Item
- Value Entry

## Value entries

### Production order - WIP

- [Beginning Balance Value](#beginning-balance-value)
- [Capacity Value](#capacity-value)
- [Consumption Value](#consumption-value)
- [Ending Balance Value](#ending-balance-value)
- [Output Value](#output-value)

#### Beginning balance value

**Formula**

Calculates the value of work in progress (WIP) by summing the cumulative values of:

- [Consumption Value](#consumption-value)
- [Capacity Value](#capacity-value)
- [Output Value](#output-value)

Each measure is filtered to include only transactions that occurred **before the earliest date in the current filter context** to provide the starting WIP balance.

**Data Source**

- Value Entry

#### Capacity value

**Formula**

Calculates the total actual cost associated with capacity usage by summing the **costAmountActual** field from the **Value Entries** table where the **Item Ledger Entry Type** is **Blank**. This typically isolates capacity-related entries not linked to standard inventory transactions like consumption or output.

**Data Source**

- Value Entry

#### Consumption value

**Formula**

Negates the sum of **costAmountActual** from **Value Entries** where **Item Ledger Entry Type** is **Consumption** and **Entry Type** is not **Revaluation**. Negating the consumption cost adds the consumed material's value to WIP.

**Data Source**

- Value Entry

#### Ending balance value

**Formula**

Calculates the value of work in progress (WIP) at the end of the selected period by summing the following measures and rounding the result to five decimal places:

- [Beginning Balance Value](#beginning-balance-value)
- [Consumption Value](#consumption-value)
- [Capacity Value](#capacity-value)
- [Output Value](#output-value)

**Data Source**

- Value Entry

### Output value

**Formula**

Calculates the total negative value of actual and expected output costs by summing the **costAmountActual** and **costAmountExpected** fields from the **Value Entries** table for entries where:

- Item Ledger Entry Type is **Output**.
- entryType is **Direct Cost**.

Then, the result is multiplied by **-1** to reflect it as a cost deduction.

**Data Source**

- Value Entry

### Value entry measures

- [Cost Amount Actual](#cost-amount-actual)
- [Cost Amount Expected](#cost-amount-expected)
- [Cost Posted to G/L](#cost-posted-to-gl)
- [Expected Cost](#expected-cost)
- [Expected Cost Posted to G/L](#expected-cost-posted-to-gl)
- [Item Ledger Entry Quantity](#item-ledger-entry-quantity)
- [Valued Quantity](#valued-quantity)

#### Cost amount actual

**Formula**

- Calculates the total actual cost amount by summing the **costAmountActual** field from the **Value Entries** table.

**Data Source**

- Value Entry

#### Cost amount expected

**Formula**

- Calculates the total expected cost amount by summing the **costAmountExpected** field from the **Value Entries** table.

**Data Source**

- Value Entry

#### Cost posted to G/L

**Formula**

Calculates the total cost amount posted to the General Ledger by summing the **costPostedtoGL** field from the **Value Entries** table.

**Data Source**

- Value Entry

#### Expected cost

**Formula**

The API's **expectedCost** field is a Boolean flag, exposed as **Is Expected Cost** in the semantic model, not an additive cost measure. For the expected cost amount, use [Cost Amount Expected](#cost-amount-expected).

**Data Source**

- Value Entry

#### Expected cost posted to G/L

**Formula**

Calculates the total expected cost posted to the general ledger by summing the **expectedCostPostedtoGL** field from the **Value Entries** table.

**Data Source**

- Value Entry

#### Item ledger entry quantity

**Formula**

Calculates the total item ledger entry quantity by summing the **itemLedgerEntryQuantity** field from the **Value Entries** table.

**Data Source**

- Value Entry

#### Valued quantity

**Formula**

Calculates the total valued quantity of items by summing the **valuedQuantity** field from the **Value Entries** table.

**Data Source**

- Value Entry

## Work center

### Work center measures

- [Work Center Availability After Orders](#work-center-availability-after-orders)
- [Work Center Load](#work-center-load)
- [Work Center Output](#work-center-output)
- [Work Center Scrap](#work-center-scrap)
- [Work Center Scrap %](#work-center-scrap-percent)

#### Work center availability after orders

**Formula**

Calculates the available capacity of a work center after considering the allocated time by subtracting the [Work Center Allocated Time](#work-center-allocated-time) from the [Work Center Capacity (Effective)](#work-center-capacity-effective).

**Data Source**

- Calendar Entry
- Prod Order Capacity Need

#### Work center load

**Formula**

Calculates the load on a work center by dividing the [Work Center Allocated Time](#work-center-allocated-time) by the [Work Center Capacity (Effective)](#work-center-capacity-effective), providing the ratio of the allocated time to the available capacity.

**Data Source**

- Calendar Entry
- Prod Order Capacity Need

#### Work center output

**Formula**

Calculates the total output quantity for a work center by summing the **outputQuantity** field from the **Capacity Ledger Entries** table, filtered where the **Type** is **Work Center**.

**Data Source**

- Capacity Ledger Entry

#### Work center scrap

**Formula**

- Calculates the total scrap quantity for a work center by summing the **scrapQuantity** field from the **Capacity Ledger Entries** table, filtered where the **Type** is **Work Center**.

**Data Source**

- Capacity Ledger Entry

#### Work center scrap percent

**Formula**

Calculates the percentage of scrap relative to the total output for a work center by dividing the [Work Center Scrap](#work-center-scrap) by the [Work Center Output](#work-center-output).

**Data Source**

- Capacity Ledger Entry

### Work center statistics

- [Work Center Actual Efficiency %](#work-center-actual-efficiency-percent)
- [Work Center Actual Need](#work-center-actual-need)
- [Work Center Actual Total Cost](#work-center-actual-total-cost)
- [Work Center Allocated Time](#work-center-allocated-time)
- [Work Center Capacity (Effective)](#work-center-capacity-effective)
- [Work Center Capacity (Total)](#work-center-capacity-total)
- [Work Center Expected Efficiency %](#work-center-expected-efficiency-percent)
- [Work Center Needed Time](#work-center-needed-time)

#### Work center actual efficiency percent

**Formula**

Calculates the actual efficiency of a work center by dividing the [Work Center Actual Need](#work-center-actual-need) by the [Work Center Capacity (Total)](#work-center-capacity-total).

**Data Source**

- Capacity Ledger Entry
- Calendar Entry

#### Work center actual need

**Formula**

- Sums **setupTime**, **runTime**, and **stopTime** from **Capacity Ledger Entries**, converting each entry's capacity unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Capacity Ledger Entry

#### Work center actual total cost

- Calculates the total actual cost for work centers by adding the [Direct Cost](#direct-cost) and [Overhead Cost](#overhead-cost) measures.

**Data Source**

- Capacity Ledger Entry
- Value Entry

#### Work center allocated time

**Formula**

- Sums **allocatedTime** from **Prod Order Capacity Need** where **Requested Only** is **FALSE**, converting each work center's unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Prod Order Capacity Need

#### Work center capacity (effective)

**Formula**

- Sums **Capacity Effective** from **Calendar Entries** where **Capacity Type** is **Work Center**, converting each work center's unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Calendar Entry

#### Work center capacity (total)

**Formula**

- Sums **Capacity Total** from **Calendar Entries** where **Capacity Type** is **Work Center**, converting each work center's unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Calendar Entry

#### Work center expected efficiency percent

**Formula**

- Calculates the expected efficiency for work centers by dividing the [Work Center Capacity (Effective)](#work-center-capacity-effective) by the [Work Center Capacity (Total)](#work-center-capacity-total).

**Data Source**

- Calendar Entry

#### Work center needed time

**Formula**

- Sums **neededTime** from **Prod Order Capacity Need** where **Requested Only** is **FALSE**, converting each work center's unit of measure to the **Show Capacity In** unit from **Manufacturing Setup**, using **Time Factors**.

**Data Source**

- Prod Order Capacity Need

## Related information

[Track your business KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
