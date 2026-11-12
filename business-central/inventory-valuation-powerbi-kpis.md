---
title: Inventory Valuation KPIs and Measures (Power BI)
description: Understand inventory valuation balances, actual and expected costs, quantities, and general ledger variances in the Power BI Inventory Valuation app.
author: kennienp
ms.author: kepontop
ms.topic: reference
ms.search.keywords: reporting
ms.date: 11/12/2026
ai-usage: ai-assisted
ms.service: dynamics-365-business-central
---

# Power BI Inventory Valuation app KPIs and measures

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This article describes inventory valuation key performance indicators (KPIs), semantic model measures, and related balance calculations for the Power BI Inventory Valuation report.

Explore the list of KPIs below to learn more about how they can help you achieve your business goals. 

Each KPI is described, including how it is calculated and what data was used in the calculations.

## Value entries table

Use the following table to find each KPI or balance calculation and its corresponding semantic model measure. Calculations without standalone measures are identified in the table.

| KPI or balance calculation | Semantic model measure |
|---|---|
| [Beginning Balance G/L](#beginning-balance-gl) | `Beginning Balance Cost Posted to G/L` |
| [Beginning Balance G/L (Expected)](#beginning-balance-gl-expected) | `Beginning Balance Expected Cost Posted to G/L` |
| [Beginning Balance Qty](#beginning-balance-qty) | `Beginning Balance Qty` |
| [Beginning Balance Value](#beginning-balance-value) | `Beginning Balance Cost Amount (Actual)` |
| [Beginning Balance Value (Expected)](#beginning-balance-value-expected) | `Beginning Balance Cost Amount (Expected)` |
| [Beginning Balance Value Expected Cost Included](#beginning-balance-value-expected-cost-included) | `Beginning Balance Cost Amount (Incl. Exp Cost)` |
| [Beginning Cost Posted to G/L (Expected)](#beginning-cost-posted-to-gl-expected) | `Beginning Balance Expected Cost Posted to G/L` |
| [Cost Amount (Actual)](#cost-amount-actual) | `Cost Amount (Actual)` |
| [Cost Amount (Expected)](#cost-amount-expected) | `Cost Amount (Expected)` |
| [Cost Posted to G/L](#cost-posted-to-gl) | `Cost Posted to G/L` |
| [Cost Posted to G/L (Expected)](#cost-posted-to-gl-expected) | `Expected Cost Posted to G/L` |
| [Decrease Qty.](#decrease-qty) | `Decrease Qty.` |
| [Decrease Value](#decreases-value) | `Decrease Value` |
| [Decrease Value (Expected)](#decreases-value-expected) | `Decrease Value (Expected)` |
| [Decrease Value Expected Cost Included](#decrease-value-expected-cost-included) | `Decrease Value Expected Cost Included` |
| [Ending Balance Expected Cost Included](#ending-balance-expected-cost-included) | `Ending Balance Cost Amount (Incl. Exp Cost)` |
| [Ending Balance Posted to G/L](#ending-balance-posted-to-gl) | `Ending Balance Cost Posted to G/L` |
| [Ending Balance Posted to G/L (Expected)](#ending-balance-posted-to-gl-expected) | `Ending Balance Expected Cost Posted to G/L` |
| [Ending Balance Qty.](#ending-balance-qty) | `Ending Balance Qty.` |
| [Ending Balance Value](#ending-balance-value) | `Ending Balance Cost Amount (Actual)` |
| [Ending Balance Value (Expected)](#ending-balance-value-expected) | `Ending Balance Cost Amount (Expected)` |
| [Ending Cost Posted to G/L (Expected)](#ending-cost-posted-to-gl-expected) | `Ending Balance Expected Cost Posted to G/L` |
| [Ending Cost Posted to G/L Expected Cost Included](#ending-cost-posted-to-gl-expected-cost-included) | Calculated from other measures; no standalone measure. |
| [Increase Value Expected Cost Included](#increase-value-expected-cost-included) | `Increase Value Expected Cost Included` |
| [Increases Qty.](#increases-qty) | `Increases Qty.` |
| [Increases Value](#increases-value) | `Increases Value` |
| [Increases Value (Expected)](#increases-value-expected) | `Increases Value (Expected)` |
| [Invoiced Quantity](#invoiced-quantity) | `Invoiced Quantity` |
| [Net Balance G/L](#net-balance-gl) | `Cost Posted to G/L` |
| [Net Balance G/L (Expected)](#net-balance-gl-expected) | `Expected Cost Posted to G/L` |
| [Net Balance Qty](#net-balance-qty) | `Invoiced Quantity` |
| [Net Balance Value](#net-balance-value) | `Cost Amount (Actual)` |
| [Net Balance Value (Expected Included)](#net-balance-value-expected-included) | `Cost Amount (Incl. Exp Cost)` |
| [Net Balance Value (Expected)](#net-balance-value-expected) | `Cost Amount (Expected)` |
| [Variance](#variance) | `Variance Cost Posted to G/L` |
| [Variance Exp](#variance-exp) | Calculated from other measures; no standalone measure. |

### Beginning balance G/L
**Formula**
- This measure calculates the cumulative [Cost Posted to G/L](#cost-posted-to-gl) for dates before the earliest date in the current context, allowing visibility into costs posted up to the start of the selected period.

**Data Sources**
- Value Entry

### Beginning balance G/L (expected)
**Formula**
- This measure calculates the cumulative [Cost Posted to G/L (Expected)](#cost-posted-to-gl-expected) for dates before the earliest date in the current context, allowing visibility into costs posted up to the start of the selected period.

**Data Sources**
- Value Entry

### Beginning balance qty
**Formula**
- This measure calculates the cumulative [Invoiced Qty](#invoiced-quantity) for dates before the earliest date in the current context, allowing visibility into quantities posted up to the start of the selected period.

**Data Sources**
- Value Entry

### Beginning balance value
**Formula**  
- This measure calculates the cumulative [Cost Amount (Actual)](#cost-amount-actual) for dates before the earliest date in the current context, providing the total value up to the start of the selected period.

**Data Sources**
- Value Entry

### Beginning balance value (expected)
**Formula**  
- This measure calculates the cumulative [Cost Amount (Expected)](#cost-amount-expected) for dates before the earliest date in the current context, providing the total expected value up to the start of the selected period.

**Data Sources**
- Value Entry

### Beginning balance value expected cost included
**Formula**  
[Beginning Balance Value](#beginning-balance-value) + [Beginning Balance Value (Expected)](#beginning-balance-value-expected)

**Data Sources**
- Value Entry

### Beginning cost posted to G/L (expected)
**Formula**  
- This measure calculates the cumulative [Cost Posted to G/L (Expected)](#cost-posted-to-gl-expected) for dates before the earliest date in the current context, providing the total expected cost posted to G/L up to the start of the selected period.

**Data Sources**
- Value Entry

### Cost amount (actual)
**Formula**
- This measure calculates the total sum of the Cost Amt. (Actual) column in the Value Entries table.

**Data Sources**
- Value Entry

### Cost amount (expected)
**Formula**
- This measure calculates the total sum of the Cost Amt. (Expected) column in the Value Entries table.

**Data Sources**
- Value Entry

### Cost posted to G/L
**Formula**
- This measure calculates the total sum of the Cost Posted to G/L column in the Value Entries table.

**Data Sources**
- Value Entry

### Cost posted to G/L (expected)
**Formula**
- This measure calculates the total sum of the Expected Cost Posted to G/L column in the Value Entries table.

**Data Sources**
- Value Entry

### Decrease qty.
**Formula**  
- This measure calculates the total sum of the Invoiced Quantity column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Sale, Negative Adjustment, Consumption, or Assembly Consumption. This measure captures quantities associated with these specific entry types that represent decreases in inventory.

**Data Sources**
- Value Entry

### Decreases value
**Formula**  
- This measure calculates the total sum of the Cost Amt. (Actual) column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Sale, Negative Adjustment, Consumption, or Assembly Consumption. This measure reflects the cost associated with these specific entry types that represent decreases in inventory.

**Data Sources**
- Value Entry

### Decreases value (expected)
**Formula**  
- This measure calculates the total sum of the Cost Amt. (Expected) column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Sale, Negative Adjustment, Consumption, or Assembly Consumption. This measure reflects the expected cost associated with these specific entry types that represent decreases in inventory.

**Data Sources**
- Value Entry

### Decrease value expected cost included
**Formula**  
[Decrease Value](#decreases-value) + [Decrease Value (Expected)](#decreases-value-expected)

**Data Sources**
- Value Entry

### Ending balance expected cost included
**Formula**
[Ending Balance Value](#ending-balance-value) + [Ending Balance Value (Expected)](#ending-balance-value-expected)

**Data Sources**
- Value Entry

### Ending balance qty.
**Formula**  
[Beginning Balance Qty.](#beginning-balance-qty) + [Net Balance Qty.](#net-balance-qty)

**Data Sources**
- Value Entry 

### Ending balance value
**Formula**  
[Beginning Balance Value](#beginning-balance-value) + Net Balance Value

**Data Sources**
- Value Entry

### Ending balance value (expected)
**Formula**  
[Beginning Balance Value (Expected)](#beginning-balance-value-expected) + [Net Balance Value (Expected)](#net-balance-value-expected)

**Data Sources**
- Value Entry

### Ending cost posted to G/L (expected)
**Formula**
[Beginning Cost Posted to G/L (Expected)](#beginning-cost-posted-to-gl-expected) + [Cost Posted to G/L (Expected)](#cost-posted-to-gl-expected)

**Data Sources**
- Value Entry

### Ending cost posted to G/L expected cost included
**Formula**
[Ending Balance Posted to G/L (Expected)](#ending-balance-posted-to-gl-expected) + [Ending Balance Posted to G/L](#ending-balance-posted-to-gl)

**Data Sources**
- Value Entry

### Increase value expected cost included
**Formula**
[Increases Value](#increases-value) + [Increases Value (Expected)](#increases-value-expected)

**Data Sources**
- Value Entry

### Increases qty.
**Formula**  
- This measure calculates the total sum of the Invoiced Quantity column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Purchase, Positive Adjustment, Output, or Assembly Output. This measure reflects the quantity associated with these entry types that represent increases in inventory.

**Data Sources**
- Value Entry

### Increases value
**Formula**  
- This measure calculates the total sum of the Cost Amt. (Actual) column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Purchase, Positive Adjustment, Output, or Assembly Output. This measure reflects the value associated with these entry types that represent increases in inventory value.

**Data Sources**
- Value Entry

### Increases value (expected)
**Formula**  
- This measure calculates the total sum of the Cost Amt. (Expected) column from the Value Entries table, but only for rows where the Item Ledger Entry Type is one of the following: Purchase, Positive Adjustment, Output, or Assembly Output. This measure reflects the expected value associated with these entry types that represent increases in inventory value.

**Data Sources**
- Value Entry


### Ending balance posted to G/L
**Formula**  
[Beginning Balance G/L](#beginning-balance-gl) + [Net Balance G/L](#net-balance-gl)

**Data Sources**
- Value Entry

### Ending balance posted to G/L (expected)
**Formula**
[Beginning Balance G/L (Expected)](#beginning-balance-gl-expected) + [Net Balance G/L (Expected)](#net-balance-gl-expected)

**Data Sources**

- Value Entry

### Invoiced quantity
**Formula**  
- This measure calculates the total sum of the Invoiced Quantity column from the Value Entries table.

**Data Sources**
- Value Entry

### Net balance G/L
**Formula**  
- This measure calculates the total sum of the Cost Posted to G/L column from the Value Entries table.

**Data Sources**
- Value Entry

### Net balance G/L (expected)
**Formula**  
- This measure calculates the total sum of the Expected Cost Posted to G/L column from the Value Entries table.

**Data Sources**
- Value Entry

### Net balance qty
**Formula**  
- This measure calculates the total sum of the Invoiced Quantity column from the Value Entries table.

**Data Sources**
- Value Entry

### Net balance value
**Formula**  
- This measure calculates the total sum of the Cost Amount (Actual) column from the Value Entries table.

**Data Sources**
- Value Entry

### Net balance value (expected included)
**Formula**  
[Ending Balance Expected Cost Included](#ending-balance-expected-cost-included) - [Beginning Balance Value Expected Cost Included](#beginning-balance-value-expected-cost-included)

**Data Sources**
- Value Entry

### Net balance value (expected)
**Formula**  
- This measure calculates the total sum of the Cost Amount (Expected) column from the Value Entries table.

**Data Sources**
- Value Entry

### Variance
**Formula**  
[Ending Balance Posted to G/L](#ending-balance-posted-to-gl) - [Ending Balance Value](#ending-balance-value)

**Data Sources**
- Value Entry

### Variance exp
**Formula**  
[Ending Cost Posted to G/L Expected Cost Included](#ending-cost-posted-to-gl-expected-cost-included) - [Ending Balance Expected Cost Included](#ending-balance-expected-cost-included)

**Data Sources**
- Value Entry

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]


## Related information

[Track KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI Inventory Valuation app](inventory-valuation-powerbi-app.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
