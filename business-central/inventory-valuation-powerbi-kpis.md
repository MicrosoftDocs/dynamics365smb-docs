---
title: Inventory Valuation KPIs and measures (Power BI)
description: The Inventory Valuation App KPIs provides a page to clearly identify all KPIs and Measures used in the Inventory Valuation Report.
author: kennienp
ms.author: kepontop
ms.reviewer: 
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 
ms.date: 11/08/2024
ms.service: dynamics-365-business-central
---

# Power BI Inventory Valuation app KPIs and measures

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This page provides a list of all Key Performance Indicators (KPIs) included in the semantic model for the Power BI Inventory Valuation report. 

Explore the list of KPIs below to learn more about how they can help you achieve your business goals. 

Each KPI is described, including how it is calculated and what data was used in the calculations.

## Value Entries Table   
- [Beginning Balance G/L](#beginning-balance-gl)
- [Beginning Balance G/L (Expected)](#beginning-balance-gl-expected)
- [Beginning Balance Qty](#beginning-balance-qty)
- [Beginning Balance Value](#beginning-balance-value)  
- [Beginning Balance Value (Expected)](#beginning-balance-value-expected)
- [Beginning Balance Value Expected Cost Included](#beginning-balance-value-expected-cost-included)
- [Beginning Cost Posted to G/L (Expected)](#beginning-cost-posted-to-gl-expected)
- [Cost Amount (Actual)](#cost-amount-actual)
- [Cost Amount (Expected)](#cost-amount-expected)
- [Cost Posted to G/L](#cost-posted-to-gl)
- [Cost Posted to G/L (Expected)](#cost-posted-to-gl-expected)
- [Decrease Qty.](#decrease-qty)
- [Decrease Value](#decreases-value)  
- [Decrease Value (Expected)](#decreases-value-expected)
- [Decrease Value Expected Cost Included](#decrease-value-expected-cost-included)
- [Ending Balance Expected Cost Included](#ending-balance-expected-cost-included) 
- [Ending Balance Posted to G/L](#ending-balance-posted-to-gl)  
- [Ending Balance Posted to G/L (Expected)](#ending-balance-posted-to-gl-expected)
- [Ending Balance Qty.](#ending-balance-qty)  
- [Ending Balance Value](#ending-balance-value)
- [Ending Balance Value (Expected)](#ending-balance-value-expected)
- [Ending Cost Posted to G/L (Expected)](#ending-cost-posted-to-gl-expected)
- [Ending Cost Posted to G/L Expected Cost Included](#ending-cost-posted-to-gl-expected-cost-included)
- [Increase Value Expected Cost Included](#increase-value-expected-cost-included)
- [Increases Qty.](#increases-qty)  
- [Increases Value](#increases-value)  
- [Increases Value (Expected)](#increases-value-expected)
- [Invoiced Quantity](#invoiced-quantity)   
- [Net Balance G/L](#net-balance-gl)
- [Net Balance G/L (Expected)](#net-balance-gl-expected)
- [Net Balance Qty](#net-balance-qty)
- [Net Balance Value](#net-balance-value)
- [Net Balance Value (Expected Included)](#net-balance-value-expected-included)
- [Net Balance Value (Expected)](#net-balance-value-expected)
- [Variance](#variance)  
- [Variance Exp](#variance-exp)

### Beginning Balance G/L
**Formula**
- This measure calculates the cumulative [Cost Posted to G/L](#cost-posted-to-gl) for dates before the earliest date in the current context, allowing visibility into costs posted up to the start of the selected period.

**Data Sources**
- Value Entry

### Beginning Balance G/L (Expected)
**Formula**
- This measure calculates the cumulative [Cost Posted to G/L (Expected)](#cost-posted-to-gl-expected) for dates before the earliest date in the current context, allowing visibility into costs posted up to the start of the selected period.

**Data Sources**
- Value Entry

### Beginning Balance Qty
**Formula**
- This measure calculates the cumulative [Invoiced Qty](#invoiced-quantity) for dates before the earliest date in the current context, allowing visibility into quantities posted up to the start of the selected period.

**Data Sources**
- Value Entry

### Beginning Balance Value
**Formula**  
- This measure calculates the cumulative [Cost Amount (Actual)](#cost-amount-actual) for dates before the earliest date in the current context, providing the total value up to the start of the selected period.

**Data Sources**
- Value Entry

### Beginning Balance Value (Expected)
**Formula**  
- This measure calculates the cumulative [Cost Amount (Expected)](#cost-amount-expected) for dates before the earliest date in the current context, providing the total expected value up to the start of the selected period.

**Data Sources**
- Value Entry

### Beginning Balance Value Expected Cost Included
**Formula**  
[Beginning Balance Value](#beginning-balance-value) + [Beginning Balance Value (Expected)](#beginning-balance-value-expected)

**Data Sources**
- Value Entry

### Beginning Cost Posted to G/L (Expected)
**Formula**  
- This measure calculates the cumulative [Cost Posted to G/L (Expected)](#cost-posted-to-gl-expected) for dates before the earliest date in the current context, providing the total expected cost posted to G/L up to the start of the selected period.

**Data Sources**
- Value Entry

### Cost Amount (Actual)
**Formula**
- This measure calculates the total sum of the Cost Amt. (Actual) column in the Value Entries table.

**Data Sources**
- Value Entry

### Cost Amount (Expected)
**Formula**
- This measure calculates the total sum of the Cost Amt. (Expected) column in the Value Entries table.

**Data Sources**
- Value Entry

### Cost Posted to G/L
**Formula**
- This measure calculates the total sum of the Cost Posted to G/L column in the Value Entries table.

**Data Sources**
- Value Entry

### Cost Posted to G/L (Expected)
**Formula**
- This measure calculates the total sum of the Expected Cost Posted to G/L column in the Value Entries table.

**Data Sources**
- Value Entry

### Decrease Qty.
**Formula**  
- This measure calculates the total sum of the Invoiced Quantity column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Sale, Negative Adjustment, Consumption, or Assembly Consumption. This measure captures quantities associated with these specific entry types that represent decreases in inventory.

**Data Sources**
- Value Entry

### Decreases Value
**Formula**  
- This measure calculates the total sum of the Cost Amt. (Actual) column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Sale, Negative Adjustment, Consumption, or Assembly Consumption. This measure reflects the cost associated with these specific entry types that represent decreases in inventory.

**Data Sources**
- Value Entry

### Decreases Value (Expected)
**Formula**  
- This measure calculates the total sum of the Cost Amt. (Expected) column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Sale, Negative Adjustment, Consumption, or Assembly Consumption. This measure reflects the expected cost associated with these specific entry types that represent decreases in inventory.

**Data Sources**
- Value Entry

### Decrease Value Expected Cost Included
**Formula**  
[Decrease Value](#decreases-value) + [Decrease Value (Expected)](#decreases-value-expected)

**Data Sources**
- Value Entry

### Ending Balance Expected Cost Included
**Formula**
[Ending Balance Value](#ending-balance-value) + [Ending Balance Value (Expected)](#ending-balance-value-expected)

**Data Sources**
- Value Entry

### Ending Balance Qty.
**Formula**  
[Beginning Balance Qty.](#beginning-balance-qty) + [Net Balance Qty.](#net-balance-qty)

**Data Sources**
- Value Entry 

### Ending Balance Value
**Formula**  
[Beginning Balance Value](#beginning-balance-value) + Net Balance Value

**Data Sources**
- Value Entry

### Ending Balance Value (Expected)
**Formula**  
[Beginning Balance Value (Expected)](#beginning-balance-value-expected) + [Net Balance Value](#net-balance-value)

**Data Sources**
- Value Entry

### Ending Cost Posted to G/L (Expected)
**Formula**
[Beginning Cost Posted to G/L (Expected)](#beginning-cost-posted-to-gl-expected) + [Cost Posted to G/L (Expected)](#cost-posted-to-gl-expected)

**Data Sources**
- Value Entry

### Ending Cost Posted to G/L Expected Cost Included
**Formula**
[Ending Balance Posted to G/L (Expected)](#ending-balance-posted-to-gl-expected) + [Ending Balance Posted to G/L](#ending-balance-posted-to-gl)

**Data Sources**
- Value Entry

### Increase Value Expected Cost Included
**Formula**
[Increases Value](#increases-value) + [Increases Value (Expected)](#increases-value-expected)

**Data Sources**
- Value Entry

### Increases Qty.
**Formula**  
- This measure calculates the total sum of the Invoiced Quantity column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Purchase, Positive Adjustment, Output, or Assembly Output. This measure reflects the quantity associated with these entry types that represent increases in inventory.

**Data Sources**
- Value Entry

### Increases Value
**Formula**  
- This measure calculates the total sum of the Cost Amt. (Actual) column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Purchase, Positive Adjustment, Output, or Assembly Output. This measure reflects the value associated with these entry types that represent increases in inventory value.

**Data Sources**
- Value Entry

### Increases Value (Expected)
**Formula**  
- This measure calculates the total sum of the Cost Amt. (Expected) column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Purchase, Positive Adjustment, Output, or Assembly Output. This measure reflects the expected value associated with these entry types that represent increases in inventory value.

**Data Sources**
- Value Entry


### Ending Balance Posted to G/L
**Formula**  
[Beginning Balance G/L](#beginning-balance-gl) + [Net Balance G/L](#net-balance-gl)

**Data Sources**
- Value Entry

### Ending Balance Posted to G/L (Expected)
**Formula**
[Beginning Balance G/L (Expected)](#beginning-balance-gl-expected) + [Net Balance G/L (Expected)](#net-balance-gl-expected)

**Data Sources**

### Invoiced Quantity
**Formula**  
- This measure calculates the total sum of the Invoiced Quantity column from the Value Entries table.

**Data Sources**
- Value Entry

### Net Balance G/L 
**Formula**  
- This measure calculates the total sum of the Cost Posted to G/L column from the Value Entries table.

**Data Sources**
- Value Entry

### Net Balance G/L (Expected)
**Formula**  
- This measure calculates the total sum of the Expected Cost Posted to G/L column from the Value Entries table.

**Data Sources**
- Value Entry

### Net Balance Qty
**Formula**  
- This measure calculates the total sum of the Invoiced Quantity column from the Value Entries table.

**Data Sources**
- Value Entry

### Net Balance Value
**Formula**  
- This measure calculates the total sum of the Cost Amount (Actual) column from the Value Entries table.

**Data Sources**
- Value Entry

### Net Balance Value (Expected Included)
**Formula**  
[Ending Balance Expected Cost Included](#ending-balance-expected-cost-included) - [Beginning Balance Value Expected Cost Included](#beginning-balance-value-expected-cost-included)

**Data Sources**
- Value Entry

### Net Balance Value (Expected)
**Formula**  
- This measure calculates the total sum of the Cost Amount (Expected) column from the Value Entries table.

**Data Sources**
- Value Entry

### Variance
**Formula**  
[Ending Balance Posted to G/L](#ending-balance-posted-to-gl) - [Ending Balance Value](#ending-balance-value)

**Data Sources**
- Value Entry

### Variance Exp
**Formula**  
[Ending Cost Posted to G/L Expected Cost Included](#ending-cost-posted-to-gl-expected-cost-included) - [Ending Balance Expected Cost Included](#ending-balance-expected-cost-included)

**Data Sources**
- Value Entry

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]


## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Inventory Valuation app](inventory-valuation-powerbi-app.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
