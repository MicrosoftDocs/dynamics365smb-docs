---
title: Manufacturing KPIs and measures (Power BI)
description: Get an overview of all the KPIs and measures in the semantic model for the Manufacturing Power BI app.
author: kennienp
ms.author: kepontop
ms.reviewer:
ms.topic: concept-article
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

## Capacity KPIs
- [Capacity Cost Amt. Deviation %](#capacity-cost-amt-deviation)
- [Capacity Cost Amt. Variance](#capacity-cost-amt-variance)
- [Capacity Used Deviation %](#capacity-used-deviation)
- [Capacity Used Variance (Hours)](#capacity-used-variance-hours)
- [Direct Cost Deviation %](#direct-cost-deviation)
- [Direct Cost Variance](#direct-cost-variance)
- [Expected Capacity Need %](#expected-capacity-need)
- [Load %](#load)
- [Overhead Cost Deviation %](#overhead-cost-deviation)
- [Overhead Cost Variance](#overhead-cost-variance)
- [Scrap %](#scrap)
- [Utilization %](#utilization)

### Capacity Cost Amt. Deviation%
**Formula**  
- This measure calculates the deviation between the actual capacity cost amount and the expected capacity cost amount, expressed as a percentage.

  *Capacity Cost Amt. Deviation % = ([Capacity Cost Amt. (Actual)](#capacity-cost-amt-actual) - [Expected Capacity Cost Amount](#expected-capacity-cost-amount))/ [Expected Capacity Cost Amount](#expected-capacity-cost-amount)*

**Data Sources**
- Item Ledger Entry

### Capacity Cost Amt. Variance
**Formula**  
- This measure calculates the variance between the expected cost of capacity utilization and the actual cost of capacity utilization.

  *Capacity Cost Amt. Variance = -([Expected Capacity Cost Amount](#expected-capacity-cost-amount) - [Capacity Cost Amt. (Actual)](#capacity-cost-amt-actual))*

**Data Sources**
- Capacity Ledger Entry
- Prod. Order Routing Line

### Capacity Used Deviation%
**Formula**

*Capacity Used Deviation = ( [Capacity Used (Hours)](#capacity-used-hours) - [Expected Capacity Need (Hours)](#expected-capacity-need-hours) ) / [Expected Capacity Need (Hours)](#expected-capacity-need-hours)*

**Data Sources**
- Capacity Ledger Entry
- Prod. Order Routing Line

### Capacity Used Variance (Hours)
**Formula**  
- This measure shows the variance between the expected capacity need and the actual capacity used.

  *Capacity Used Variance (Hours) = -([Expected Capacity Need (Hours)](#expected-capacity-need-hours) - [Capacity Used (Hours)](#capacity-used-hours))*

**Data Sources**
- Prod. Order Routing Line
- Capacity Ledger Entry

### Direct Cost Deviation%
**Formula**

*Direct Cost Deviation = ( [Direct Cost](#direct-cost) - [Expected Operation Cost Amt.](#expected-operation-cost-amt) ) / [Expected Operation Cost Amt.](#expected-operation-cost-amt)*

**Data Sources**
- Prod. Order Routing Line
- Capacity Ledger Entry

### Direct Cost Variance
**Formula**

*Direct Cost Variance = [Expected Operation Cost Amt.](#expected-operation-cost-amt) - [Direct Cost](#direct-cost)*

**Data Sources**
- Prod. Order Routing Line
- Capacity Ledger Entry

### Expected Capacity Need%
**Formula**

*Expected Capacity Need % = [Expected Capacity Need (Hours)](#expected-capacity-need-hours) / [Capacity Available (Hours)](#capacity-available-hours)*
**Data Sources**
- Prod. Order Routing Line
- Calendar Entry

### Load%
**Formula**  
- This measure is calculates the percentage of available capacity that is currently being utilized, expressed as a percentage..
  
  *Load % = [Allocated Time (Hours)](#allocated-time-hours) / [Capacity Available (Hours)](#capacity-available-hours)*

**Data Sources**
- Calendar Entry
- Prod. Order Routing Line

### Overhead Cost Deviation%
**Formula**  
*Overhead Cost Deviation % = ( [Overhead Cost](#overhead-cost) - [Expected Capacity Ovhd. Cost](#expected-capacity-ovhd-cost) ) / [Expected Capacity Ovhd. Cost](#expected-capacity-ovhd-cost)*

**Data Sources**
- Prod. Order Routing Line
- Capacity Ledger Entry

### Overhead Cost Variance
**Formula**

*Overhead Cost Variance = [Expected Capacity Ovhd. Cost](#expected-capacity-ovhd-cost) - [Overhead Cost](#overhead-cost)*

**Data Sources**
- Prod. Order Routing Line
- Capacity Ledger Entry

### Scrap%
**Formula**

*Scrap % = [Capacity Scrap Qty.](#capacity-scrap-qty) / [Capacity Output Qty.](#capacity-output-qty)*

**Data Source**
- Capacity Ledger Entry

### Utilization%
**Formula**

*Utilization % = [Capacity Used (Hours)](#capacity-used-hours) / [Capacity Available (Hours)](#capacity-available-hours)*

**Data Source**
- Capacity Ledger Entry
- Calendar Entry

## Capacity Measures
- [Allocated Time (Hours)](#allocated-time-hours)
- [Capacity Available (Hours)](#capacity-available-hours)
- [Capacity Cost Amt. (Actual)](#capacity-cost-amt-actual)
- [Capacity Output Qty.](#capacity-output-qty)
- [Capacity Scrap Qty.](#capacity-scrap-qty)
- [Capacity Used (Hours)](#capacity-used-hours)
- [Capacity Used per Unit (Hours)](#capacity-used-per-unit-hours)
- [Direct Cost](#direct-cost)
- [Expected Capacity Cost Amount](#expected-capacity-cost-amount)
- [Expected Capacity Need (Hours)](#expected-capacity-need-hours)
- [Expected Capacity Ovhd. Cost](#expected-capacity-ovhd-cost)
- [Expected Operation Cost Amt.](#expected-operation-cost-amt)
- [Overhead Cost](#overhead-cost)
- [Run Time (Hours)](#run-time-hours)
- [Run Time per Unit (Hours)](#run-time-per-unit-hours)
- [Setup Time](#setup-time-hours)
- [Setup Time per Unit (Hours)](#setup-time-per-unit-hours)
- [Stop Time](#stop-time-hours)
- [Stop Time per Unit (Hours)](#stop-time-per-unit-hours)


### Allocated Time (Hours)
**Formula**  
- This measure shows the amount of time in hours that are allocated for production order routing lines by summing up all the allocated time values from the Production Data table.

**Data Sources**
- Prod. Order Capacity Need
- Prod. Order Routing Line

### Capacity Available (Hours)
**Formula**  
- This measure shows the total amount of available capacity in hours by summing up all capacity available values from the Production Data table.

**Data Sources**
- Calendar Entry

### Capacity Cost Amt. (Actual)
**Formula**  
- This measure calculates the actual cost of capacity utilization for a given period by summing up the Direct Cost and the Overhead Cost. The Direct Cost represents the direct expenses incurred in producing a product, while the Overhead Cost represents the indirect expenses incurred in producing a product, such as rent, utilities, and maintenance.

  *Capacity Cost Amt. (Actual) = [Direct Cost](#direct-cost) + [Overhead Cost](#overhead-cost)*

**Data Sources**
- Capacity Ledger Entry


### Capacity Output Qty. 
**Formula**  
- This measure calculates the total Capacity Output Quantity in a given period by summing up the output quantity for each capacity ledger entry from the Production Data table.
  
**Data Sources**
- Capacity Ledger Entry

### Capacity Scrap Qty.
**Formula**  
- This measure calculates the total scrap quantity in a given period by summing up the scrap quantity for each capacity ledger entry from the Production Data table.
  
**Data Sources**
- Capacity Ledger Entry

### Capacity Used (Hours)
**Formula**  
- This measure shows the total number of capacity hours used by summing up the capacity requirement for each production activity from the Production Data table.

**Data Sources**
- Capacity Ledger Entry

### Capacity Used per Unit (Hours)
**Formula**  
- This measure shows the amount of capacity utilized to produce a single unit of a product.

  *Capacity Used per Unit (Hours) = [Capacity Used (Hours)](#capacity-used-hours) / [Finished Quantity (Base)](#finished-quantity-base)*

**Data Sources**
- Capacity Ledger Entry

### Direct Cost
**Formula**  
- This measure calculates the direct cost by summing up the Direct Cost for each capacity ledger entry from the Production Data table.

**Data Sources**
- Capacity Ledger Entry

### Expected Capacity Cost Amount
**Formula**  
- This measure calculates the expected cost of capacity utilization for a given period by summing up the Expected Operation Cost Amount and the Expected Capacity Overhead Cost. The Expected Operation Cost Amount represents the expected cost of operating the equipment or machinery used in production, while the Expected Capacity Overhead Cost represents the expected cost of indirect resources used in production, such as rent, utilities, and maintenance.

  *Expected Capacity Cost Amount = [Expected Operation Cost Amount](#expected-operation-cost-amt) + [Expected Capacity Overhead Cost](#expected-capacity-ovhd-cost)*

**Data Sources**
- Prod. Order Routing Line

### Expected Capacity Need (Hours)
**Formula**  
- This measure shows the expected total capacity required for production by summing up the expected capacity need (in hours) for each production activity from the Production Data table.

**Data Sources**
- Prod. Order Routing Line


### Expected Capacity Ovhd. Cost
**Formula**  
- This measure calculates the Expected Capacity Ovhd. Cost by summing up the Expected Capacity Ovhd. Cost for each Prod. Order Routing Line from the Production Data table.

**Data Sources**
- Prod. Order Routing Line

### Expected Operation Cost Amt.
**Formula**  
- This measure calculates the Expected Operation Cost Amt. by summing up the Expected Operation Cost Amt. for each Prod. Order Routing Line from the Production Data table.

**Data Sources**
- Prod. Order Routing Line

### Overhead Cost
**Formula**  
- This measure calculates the Overhead Cost by summing up the Overhead Cost for each Capacity Ledger Entry from the Production Data table.

**Data Sources**
- Capacity Ledger Entry

### Run Time (Hours)
**Formula**
- This measure calculates the Run Time (Hours) by summing up the Run Time (Hr.) for each Capacity Ledger Entry from the Production Data table.
 
**Data Sources**
- Capacity Ledger Entry

### Run Time per Unit (Hours)
**Formula**  
- This measure is shows the amount of time required to produce a single unit of a product. 

  *Run Time per Unit (Hours) = [Run Time (Hours)](#run-time-hours) / [Finished Quantity (Base)](#finished-quantity-base)*

**Data Sources**
- Capacity Ledger Entry

### Setup Time (Hours)
**Formula**  
- This measure calculates the Setup Time (Hours) by summing up the Setup Time (Hr.) for each Capacity Ledger Entry from the Production Data table

**Data Sources**
- Capacity Ledger Entry

### Setup Time per Unit (Hours)
**Formula**  
- This measure shows the amount of time required to set up a machine or equipment for production.

  *Setup Time per Unit (Hours) = [Setup Time (Hours)](#setup-time-hours) / [Finished Quantity (Base)](#finished-quantity-base)*

**Data Sources**
- Capacity Ledger Entry

### Stop Time (Hours)
**Formula**  
- This measure calculates the Stop Time (Hours) by summing up the Stop Time (Hr.) for each Capacity Ledger Entry from the Production Data table

**Data Sources**
- Capacity Ledger Entry

### Stop Time per Unit (Hours)
**Formula**  
- This measure shows the amount of time lost due to equipment downtime or stoppages, per unit produced.

  *Stop Time per Unit (Hours) = [Stop Time (Hours)](#stop-time-hours) / [Finished Quantity (Base)](#finished-quantity-base)*

**Data Sources**
- Capacity Ledger Entry

## Consumption KPIs
- [% Consumed](#consumed)
- [% Consumption Rem.](#consumed-rem)
- [Consumption Cost Amt. Deviation %](#consumption-cost-amt-deviation)
- [Consumption Cost Amt. Variance](#consumption-cost-amt-variance)
- [Consumption Qty. Deviation %](#consumption-qty-deviation)
- [Consumption Qty. Variance](#consumption-qty-variance)

### %Consumed
**Formula**  
[Qty. Consumed (Base)](#qty-consumed-base) / [Expected Consumption Qty. (Base)](#expected-consumption-qty-base)

**Data Sources**
- Item Ledger Entry
- Prod. Order Component

### %Consumed Rem.
**Formula**  
[Rem. Qty. to Consume (Base)](#rem-qty-to-consume-base) / [Expected Consumption Qty. (Base)](#expected-consumption-qty-base)

**Data Sources**
- Prod. Order Component

### Consumption Cost Amt. Deviation%
**Formula**  
- This measure calculates the deviation between the actual consumption cost amount and the expected consumption cost amount, expressed as a percentage.

  *Consumption Cost Amt. Deviation % = ([Consumed Cost Amount (Actual)](#consumed-cost-amount-actual) - [Expected Consumption Cost Amount](#expected-consumption-cost-amount)) / [Expected Consumption Cost Amount](#expected-consumption-cost-amount)*

**Data Sources**
- Item Ledger Entry
- Prod. Order Component

### Consumption Cost Amt. Variance
**Formula**  
- This measure shows the variance between the expected cost of consumed items and the actual cost of consumed items. 

  *Consumption Cost Amt. Variance = -([Expected Consumption Cost Amount](#expected-consumption-cost-amount) - [Consumed Cost Amount (Actual)](#consumed-cost-amount-actual))*

**Data Sources**
- Prod. Order Component
- Item Ledger Entry

### Consumption Qty. Deviation%
**Formula**  
( [Qty. Consumed (Base)](#qty-consumed-base) - [Expected Consumption Qty. (Base)](#expected-consumption-qty-base) ) / [Expected Consumption Qty. (Base)](#expected-consumption-qty-base)

**Data Sources**
- Prod. Order Component
- Item Ledger Entry

### Consumption Qty. Variance
**Formula**  
[Expected Consumption Qty. (Base)](#expected-consumption-qty-base) - [Qty. Consumed (Base)](#qty-consumed-base)

**Data Sources**
- Prod. Order Component
- Item Ledger Entry

## Consumption Measures
- [Consumed Cost Amount (Actual)](#consumed-cost-amount-actual)
- [Expected Consumption Cost Amount](#expected-consumption-cost-amount)
- [Expected Consumption Qty. (Base)](#expected-consumption-qty-base)
- [Qty. Consumed (Base)](#qty-consumed-base)
- [Rem. Consumption Cost Amt.](#rem-consumption-cost-amt)
- [Rem. Qty. to Consume (Base)](#rem-qty-to-consume-base)

### Consumed Cost Amount (Actual)
**Formula**  
- This measure shows the actual cost of consumed items for a given period by summing up the actual cost of each item used in production. To calculate this cost amount, the measure calculates the sum of the actual cost of items consumed from the Production Data Table, filtered for the Consumption data source.

**Data Sources**
- Item Ledger Entry

### Expected Consumption Cost Amount
**Formula**  
- This measure shows the expected cost of consumed items for a given period by summing up the expected consumption cost of each item used in production. To calculate this cost amount, the measure multiplies the expected consumption quantity of each item by its related unit cost and then sums up the results from the Production Data table.

**Data Sources**
- Prod. Order Component

### Expected Consumption Qty. (Base)
**Formula**  
- This measure calculates the expected consumption quantity by summing up the Expected Consumption Qty. (Base) for each Prod. Order Component from the Production Data table.

**Data Sources**
- Prod. Order Component

### Qty. Consumed (Base)
**Formula**  
- This measure calculates the quantity consumed by summing up Quantity for each consumption Item Ledger Entry from the Production Data table.

**Data Sources**
- Item Ledger Entry

### Rem. Consumption Cost Amt.
**Formula**  
- The Rem. Consumption Cost Amt. measure calculates the total remaining consumption cost for production order components. It filters the Production Data Table to include only rows where the [Data Source] is Prod. Order Component. For these rows, it multiplies the Rem. Qty. to Consume (Base) by the Unit Cost (LCY) from the related Item table. 

**Data Sources**
- Prod. Order Component
- Item

### Rem. Qty. to Consume (Base)
**Formula**  
- This measure calculates the remaining quantity to consume by summing up Remaining Qty. (Base) for each consumption Prod. Order Component from the Production Data table.

**Data Sources**
- Prod. Order Component

## Output KPIs
- [% Finished](#finished)
- [% Remaining](#remaining)
- [Cost Amt. Deviation %](#cost-amt-deviation)
- [Cost Amt. Variance](#cost-amt-variance)
- [Qty. Deviation %](#qty-deviation)
- [Qty. Variance](#qty-variance)

### %Finished
**Formula**  
  *% Finished = ( [Finished Quantity (Base)](#finished-quantity-base) / [Expected Quantity (Base)](#expected-quantity-base) )*
  
**Data Sources**
- Item Ledger Entry
- Prod. Order Line

### %Remaining
**Formula**  
  *% Remaining = ( [Remaining Qty. (Base)](#remaining-qty-base) / [Expected Quantity (Base)](#expected-quantity-base) )*
  
**Data Sources**
- Prod. Order Line

### Cost Amt. Deviation%
**Formula**  
- This measure calculates the deviation between the expected cost amount and the actual cost amount for finished goods produced, expressed as a percentage.

  *Cost Amt. Deviation % = ([Finished Cost Amt. (Actual)](#finished-cost-amt-actual) - [Expected Cost Amt.](#expected-cost-amt)) / [Expected Cost Amt.](#expected-cost-amt)*
  
**Data Sources**
- Item Ledger Entry
- Prod. Order Line

### Cost Amt. Variance
**Formula**  
- This measure calculates the variance between the expected cost amount and the actual cost amount for finished goods produced.

  *Cost Amt. Variance = -([Expected Cost Amt.](#expected-cost-amt) - [Finished Cost Amt. (Actual)](#finished-cost-amt-actual))*
  
**Data Sources**
- Item Ledger Entry
- Prod. Order Line

### Qty. Deviation%
**Formula**  
- This measure shows the deviation between the expected quantity and the actual quantity produced, expressed as a percentage.

  *Qty. Deviation % = ([Finished Quantity (Base)](#finished-quantity-base) - [Expected Quantity (Base)](#expected-quantity-base)) / [[Expected Quantity (Base)](#expected-quantity-base)*
  
**Data Sources**
- Item Ledger Entry
- Prod. Order Line

### Qty. Variance
**Formula**  
- This measure calculates the variance between the expected quantity and the actual quantity produced.
  
**Data Sources**
- Item Ledger Entry
- Prod. Order Line

## Output Measures
- [Expected Cost Amt.](#expected-cost-amt)
- [Expected Quantity (Base)](#expected-quantity-base)
- [Finished Cost Amt. (Actual)](#finished-cost-amt-actual)
- [Finished Quantity (Base)](#finished-quantity-base)
- [Remaining Cost Amt.](#remaining-cost-amt)
- [Remaining Qty. (Base)](#remaining-qty-base)

### Expected Cost Amt.
**Formula**  
- This measure shows the total expected cost amount by multiplying the quantity (in base units) for each production order line from the Production Data Table by the unit cost (in local currency) for the corresponding item, and summing up the results.
  
**Data Sources**
- Prod. Order Line

### Expected Quantity (Base)
**Formula**  
- This measure calculates the total expected quantity (in base units) for a given period by summing up the base quantity for each production order line from the Production Data table.

**Data Sources**
- Prod. Order Line

### Finished Cost Amt. (Actual)
**Formula**  
- This measure shows total actual cost amount for finished goods produced by summing up the actual cost amount for each output item ledger entry from the Production Data Table.
  
**Data Sources**
- Item Ledger Entry

### Finished Quantity (Base)
**Formula**  
- This measure calculates the total quantity of finished products produced in base units over a given period by summing up all the output quantities from the Production Data table.

**Data Sources**
- Item Ledger Entry

### Remaining Cost Amt.
**Formula**
- This measure calculates the total remaining cost for production order lines. It filters the Production Data Table to include only rows where [Data Source] is Prod. Order Line. For each of these rows, it multiplies [Remaining Qty. (Base)] by the [Unit Cost (LCY)] from the related Item table. 

**Data Sources**
- Prod. Order Line.
- Item

### Remaining Qty. (Base)
**Formula**  
- This measure calculates the total remaining quantity for production order lines. It sums the [Remaining Qty. (Base)] column in the Production Data Table, but only for rows where [Data Source] is Prod. Order Line. 

**Data Sources**
- Prod. Order Line

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]


## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Manufacturing app](manufacturing-powerbi-app.md)  
[Built-in production reports](production-reports.md)  
[Manufacturing overview](production-manage-manufacturing.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
