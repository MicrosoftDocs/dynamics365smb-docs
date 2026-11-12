---
title: Projects KPIs and Measures (Power BI)
description: Explore project KPIs and measures in the Business Central Power BI Projects app semantic model, including formulas and the data used in calculations.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: reference
ai-usage: ai-assisted
ms.search.keywords: reporting
ms.date: 09/25/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Power BI projects app KPIs and measures

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This page provides a list of all Key Performance Indicators (KPIs) included in the semantic model for the Power BI Projects report.

Explore the list of KPIs below to learn more about how they can help you achieve your business goals.

Each KPI is described, including how it is calculated and what data was used in the calculations.

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Project measures

- [No. of Completed Projects](#no-of-completed-projects)
- [Project Count](#project-count)
- [Tasks Count](#tasks-count)
- [Invoiced (%)](#invoiced-)
- [Completed (%)](#completed-)
- [Duration (Days)](#duration-days)
- [Realization (%)](#realization-)
- [Realization Variance](#realization-variance)

### No. of completed projects

**Formula**  
The No. of Completed Projects measure calculates the number of projects where the Complete column is "Yes".

**Data Sources**
- Job

### Project count

**Formula**  
The Project Count measure counts the total number of projects in the Project table.

**Data Sources**
- Job

### Tasks count

**Formula**  
The Tasks Count measure counts the number of rows in the Tasks table where the Project Task Type has a value of "Posting".

**Data Sources**
- Job Task

### Completed (%)

**Formula**  
*Completed (%) = [Total Usage Cost](#total-usage-cost) / [Total Budget Cost](#total-budget-cost)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

### Invoiced (%)

**Formula**  
*Invoiced (%) = [Total Invoiced Price](#total-invoiced-price) / [Total Billable Price](#total-billable-price)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

### Duration (days)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Duration (Days) measure calculates the number of days between the earliest starting date and latest ending date for a given project in the Project table.

**Data Sources**
- Job

### Realization (%)

**Formula**  
*Realization (%) = [Total Billable Price](#total-billable-price) / [Total Usage Price](#total-usage-price)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

### Realization variance

**Formula**  
*Realization Variance = [Total Billable Price](#total-billable-price) - [Total Usage Price](#total-usage-price)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

## Obsolete project measures

### Actual profit

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
*Actual Profit = [Total Invoiced Price](#total-invoiced-price) - [Total Usage Cost](#total-usage-cost)*
  
**Data Sources**
- Job Ledger Entry

### Actual profit margin %

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
*Actual Profit Margin % = [Actual Profit](#actual-profit) / [Total Invoiced Price](#total-invoiced-price)*
  
**Data Sources**
- Job Ledger Entry

### Budget profit

**Formula**  
*Budget Profit = [Total Budget Price](#total-budget-price) - [Total Budget Cost](#total-budget-cost)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

### Budget profit margin %

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
*Budget Profit Margin % = [Total Budget Profit](#total-budget-profit) / [Total Budget Price](#total-budget-price)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

## Project ledger measures

- [Project Ledger Entry Quantity](#project-ledger-entry-quantity)
- [Project Ledger Line Amount](#project-ledger-line-amount)
<!-- ### Statistics -->
<!-- #### Invoiced Cost -->
- [G/L Account Invoiced Cost](#gl-account-invoiced-cost)
- [Item Invoiced Cost](#item-invoiced-cost)
- [Resource Invoiced Cost](#resource-invoiced-cost)
<!-- #### Invoiced Price -->
- [G/L Account Invoiced Price](#gl-account-invoiced-price)
- [Item Invoiced Price](#item-invoiced-price)
- [Resource Invoiced Price](#resource-invoiced-price)
<!-- #### Invoiced Profit -->
- [G/L Account Invoiced Profit](#gl-account-invoiced-profit)
- [Item Invoiced Profit](#item-invoiced-profit)
- [Resource Invoiced Profit](#resource-invoiced-profit)
<!-- #### Usage Cost -->
- [G/L Account Usage Cost](#gl-account-usage-cost)
- [Item Usage Cost](#item-usage-cost)
- [Resource Usage Cost](#resource-usage-cost)
<!-- #### Usage Price -->
- [G/L Account Usage Price](#gl-account-usage-price)
- [Item Usage Price](#item-usage-price)
- [Resource Usage Price](#resource-usage-price)
<!-- #### Totals -->
- [Total Invoiced Costs](#total-invoiced-costs)
- [Total Invoiced Price](#total-invoiced-price)
- [Total Invoiced Profit](#total-invoiced-profit)
- [Total Invoiced Profit Margin %](#total-invoiced-profit-margin-)
- [Total Usage Cost](#total-usage-cost)
- [Total Usage Price](#total-usage-price)
- [Total Usage Profit](#total-usage-profit)
- [Total Usage Profit Margin %](#total-usage-profit-margin-)

### Project ledger entry quantity

**Formula**  
The Project Ledger Entry Quantity measure aggregates the Qty. column of the Project Ledger Entry table. The sign is then inverted by multiplying by negative one.
  
**Data Sources**
- Project Ledger Entry

### Project ledger line amount
**Formula**  
The Project Ledger Line Amount measure calculates the Project Ledger Line Amount by iterating over each Project Ledger Entry and multiplying Quantity by Unit Price (LCY).
  
**Data Sources**
- Project Ledger Entry

<!-- Invoiced -->
## Project invoiced cost

<!-- Invoiced Cost -->
### G/L account invoiced cost

**Formula**  
The G/L Account Invoiced Cost calculates the total invoiced cost for G/L accounts used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Sale" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Item invoiced cost

**Formula**  
The Item Invoiced Cost calculates the total invoiced cost for items used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Sale" and the type is "Item".

**Data Sources**
- Job Ledger Entry

### Resource invoiced cost

**Formula**  
The Resource Invoiced Cost calculates the total invoiced cost for resources used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Sale" and the type is "Resource".

**Data Sources**
- Job Ledger Entry

<!-- Invoiced Price -->
## Project invoiced price

### G/L account invoiced price

**Formula**  
The G/L Account Invoiced Price calculates the total invoiced price for G/L accounts used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Sale" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Item invoiced price

**Formula**  
The Item Invoiced Price measure calculates the total invoiced price for items used in a project. It uses the SUMX function to calculate the line amount for each entry where **Entry Type** is **Sale** and **Type** is **Item**.

**Data Sources**
- Job Ledger Entry

### Resource invoiced price

**Formula**  
The Resource Invoiced Price calculates the total invoiced price for resources used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Sale" and the type is "Resource".

**Data Sources**
- Job Ledger Entry

<!-- Invoiced Profit -->
## Project invoiced profit

### G/L account invoiced profit

**Formula**  
*G/L Account Invoiced Profit = [G/L Account Invoiced Price](#gl-account-invoiced-price) - [G/L Account Invoiced Cost](#gl-account-invoiced-cost)*

**Data Sources**
- Job Ledger Entry

### Item invoiced profit

**Formula**  
*Item Invoiced Profit = [Item Invoiced Price](#item-invoiced-price) - [Item Invoiced Cost](#item-invoiced-cost)*

**Data Sources**
- Job Ledger Entry

### Resource invoiced profit

**Formula**  
*Resource Invoiced Profit = [Resource Invoiced Price](#resource-invoiced-price) - [Resource Invoiced Cost](#resource-invoiced-cost)*

**Data Sources**
- Job Ledger Entry

<!-- Usage -->
## Project usage cost

<!-- Usage Cost-->
### G/L account usage cost

**Formula**  
The G/L Account Usage Cost calculates the total usage cost for G/L accounts used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Usage" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Item usage cost

**Formula**  
The Item Usage Cost calculates the total usage cost for items used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Usage" and the type is "Item".

**Data Sources**
- Job Ledger Entry

### Resource usage cost

**Formula**  
The Resource Usage Cost calculates the total usage cost for resources used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Usage" and the type is "Resource".

**Data Sources**
- Job Ledger Entry

<!-- Usage Price-->
## Project usage price
### G/L account usage price

**Formula**  
The G/L Account Usage Price calculates the total usage price for G/L accounts used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Usage" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Item usage price

**Formula**  
The Item Usage Price calculates the total usage price for items used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Usage" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Resource usage price

**Formula**  
The Resource Usage Price calculates the total usage price for resources used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Usage" and the type is "Resource".

**Data Sources**
- Job Ledger Entry

<!-- Usage Profit-->
## Project usage profit

### G/L account usage profit

**Formula**  
*G/L Account Usage Profit = [G/L Account Usage Price](#gl-account-usage-price) - [G/L Account Usage Cost](#gl-account-usage-cost)*

**Data Sources**
- Job Ledger Entry

### Item usage profit

**Formula**  
*Item Usage Profit = [Item Usage Price](#item-usage-price) - [Item Usage Cost](#item-usage-cost)*

**Data Sources**
- Job Ledger Entry

### Resource usage profit

**Formula**  
*Resource Usage Profit = [Resource Usage Price](#resource-usage-price) - [Resource Usage Cost](#resource-usage-cost)*

**Data Sources**
- Job Ledger Entry

## Project ledger totals

### Total invoiced costs

**Formula**  
*Total Invoiced Costs = [G/L Account Invoiced Cost](#gl-account-invoiced-cost) + [Item Invoiced Cost](#item-invoiced-cost) + [Resource Invoiced Cost](#resource-invoiced-cost)*

**Data Sources**
- Job Ledger Entry

### Total invoiced price

**Formula**  
The Total Invoiced Price measure returns the absolute value of [Project Ledger Line Amount](#project-ledger-line-amount) for entries where **Entry Type** is **Sale**.

**Data Sources**
- Job Ledger Entry

### Total invoiced profit

**Formula**  
*Total Invoiced Profit = [Total Invoiced Price](#total-invoiced-price) + [Total Invoiced Costs](#total-invoiced-costs)*

The measure adds invoiced costs because sale entries normally store costs with a negative sign.

**Data Sources**
- Job Ledger Entry

### Total invoiced profit margin %

**Formula**  
*Total Invoiced Profit Margin % = [Total Invoiced Profit](#total-invoiced-profit) / [Total Invoiced Price](#total-invoiced-price)*

**Data Sources**
- Job Ledger Entry

### Total usage cost

**Formula**  
*Total Usage Costs = [G/L Account Usage Cost](#gl-account-usage-cost) + [Item Usage Cost](#item-usage-cost) + [Resource Usage Cost](#resource-usage-cost)*

**Data Sources**
- Job Ledger Entry

### Total usage price

**Formula**  
*Total Usage Price = [G/L Account Usage Price](#gl-account-usage-price) + [Item Usage Price](#item-usage-price) + [Resource Usage Price](#resource-usage-price)*

**Data Sources**
- Job Ledger Entry

### Total usage profit

**Formula**  
*Total Usage Profit = [Total Usage Price](#total-usage-price) - [Total Usage Cost](#total-usage-cost)*

**Data Sources**
- Job Ledger Entry

### Total usage profit margin %

**Formula**  
*Total Usage Profit Margin % = [Total Usage Profit](#total-usage-profit) / [Total Usage Price](#total-usage-price)*

**Data Sources**
- Job Ledger Entry

## Obsolete project ledger measures

### Actual (total price)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Actual (Total Price) measure sums **Total Price (LCY)** in the Project Ledger Entry table for entries where **Entry Type** is **Usage**, then multiplies the result by -1.
  
**Data Sources**
- Job Ledger Entry

### Billable (invoiced price)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Billable (Invoiced Price) measure shows the total invoiced price of billable project entries by calculating the total price (in local currency) in the Project Ledger Entry table and selecting only those entries with an entry type of "Sale", which indicates that the project entry is billable.
  
**Data Sources**
- Job Ledger Entry

### Invoiced (total cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Invoiced (Total Cost) measure calculates the total cost of all project ledger entries where the entry type is "Sale" in the Project Ledger Entry table.
  
**Data Sources**
- Job Ledger Entry

### Invoiced (total price)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Invoiced (Total Price) measure calculates the total price of all project ledger entries where the entry type is "Sale" in the Project Ledger Entry table.
  
**Data Sources**
- Job Ledger Entry

### Quantity

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Quantity measure calculates the total quantity of a product or service used in a project by summing the quantity in the Project Ledger Entry table and converting the measure to a positive value.
  
**Data Sources**
- Job Ledger Entry

### Total price

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Total Price measure sums **Total Price (LCY)** in the Project Ledger Entry table.

**Data Sources**
- Job Ledger Entry

## Obsolete usage measures

- [Actual (Total Cost)](#actual-total-cost)
- [Gen. Journal Usage (Total Cost)](#gen-journal-usage-total-cost)
- [Labour Usage (Total Cost)](#labour-usage-total-cost)
- [Material Usage (Total Cost)](#material-usage-total-cost)

### Actual (total cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Actual (Total Cost) measure calculates the total cost (in local currency) of all project ledger entries where the type is "Usage" in the Project Ledger Entry table.
  
**Data Sources**
- Job Ledger Entry

### Gen. journal usage (total cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Gen. Journal Usage (Total Cost) measure sums **Total Cost (LCY)** in the Project Ledger Entry table where **Entry Type** is **Usage** and **Type** is **G/L Account**.
  
**Data Sources**
- Job Ledger Entry

### Labour usage (total cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Labour Usage (Total Cost) measure sums **Total Cost (LCY)** in the Project Ledger Entry table where **Entry Type** is **Usage** and **Type** is **Resource**.
  
**Data Sources**
- Job Ledger Entry

### Material usage (total cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Material Usage (Total Cost) measure sums **Total Cost (LCY)** in the Project Ledger Entry table where **Entry Type** is **Usage** and **Type** is **Item**.
  
**Data Sources**
- Job Ledger Entry

## Planning line measures

- [Planning Line Quantity](#planning-line-quantity)
- [Planning Line Total Cost (LCY)](#planning-line-total-cost-lcy)
- [Planning Line Total Price (LCY)](#planning-line-total-price-lcy)
<!-- Variance -->
- [Total Cost Variance to Budget](#total-cost-variance-to-budget)
- [Total Cost Variance to Budget %](#total-cost-variance-to-budget-)
<!-- Statistics -->
<!-- Billable Costs -->
- [G/L Account Billable Costs](#gl-account-billable-costs)
- [Item Billable Costs](#item-billable-costs)
- [Resource Billable Costs](#resource-billable-costs)
<!-- Billable Price -->
- [G/L Account Billable Price](#gl-account-billable-price)
- [Item Billable Price](#item-billable-price)
- [Resource Billable Price](#resource-billable-price)
<!-- Billable Profit -->
- [G/L Account Billable Profit](#gl-account-billable-profit)
- [Item Billable Profit](#item-billable-profit)
- [Resource Billable Profit](#resource-billable-profit)
<!-- Budget Cost -->
- [G/L Account Budget Costs](#gl-account-budget-costs)
- [Item Budget Costs](#item-budget-costs)
- [Resource Budget Costs](#resource-budget-costs)
<!-- Budget Price -->
- [G/L Account Budget Price](#gl-account-budget-price)
- [Item Budget Price](#item-budget-price)
- [Resource Budget Price](#resource-budget-price)
<!-- Budget Profit -->
- [G/L Account Budget Profit](#gl-account-budget-profit)
- [Item Budget Profit](#item-budget-profit)
- [Resource Budget Profit](#resource-budget-profit)
<!-- Totals -->
- [Total Billable Cost](#total-billable-cost)
- [Total Billable Price](#total-billable-price)
- [Total Billable Profit](#total-billable-profit)
- [Total Budget Cost](#total-budget-cost)
- [Total Budget Price](#total-budget-price)
- [Total Budget Profit](#total-budget-profit)

### Planning line quantity

**Formula**  
The Planning Line Quantity measure calculates the sum of the quantity column in the Project Planning Line table.

**Data Sources**
- Job Planning Line

### Planning line total cost (LCY)

**Formula**  
The Planning Line Total Cost (LCY) measure calculates the total cost of all project planning lines in the Project Planning Line table. It uses the SUMX function to iterate over each row in the table and multiply the quantity and unit cost (in local currency) columns for each row. The results of each multiplication are then summed up to produce the total cost.

**Data Sources**
- Job Planning Line

### Planning line total price (LCY)

**Formula**  
The Planning Line Total Price (LCY) measure calculates the total price of all project planning lines in the Project Planning Line table. It uses the SUMX function to iterate over each row in the table and multiply the quantity and unit price (in local currency) columns for each row. The results of each multiplication are then summed up to produce the total price.

**Data Sources**
- Job Planning Line

### Total cost variance to budget

**Formula**  
*Total Cost Variance to Budget = [Total Usage Cost](#total-usage-cost) - [Total Budget Cost](#total-budget-cost)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

### Total cost variance to budget %

**Formula**  
*Total Cost Variance to Budget % = [Total Cost Variance to Budget](#total-cost-variance-to-budget) / [Total Budget Cost](#total-budget-cost)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

## Project billable costs

### G/L account billable costs

**Formula**  
The G/L Account Billable Costs calculates the total billable cost for G/L accounts used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "G/L Account".

**Data Sources**
- Job Planning Line

### Item billable costs

**Formula**  
The Item Billable Costs calculates the total billable cost for items used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "Item".

**Data Sources**
- Job Planning Line

### Resource billable costs

**Formula**  
The Resource Billable Costs calculates the total billable cost for resources used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "Resource".

**Data Sources**
- Job Planning Line

## Project billable price

### G/L account billable price

**Formula**  
The G/L Account Billable Price calculates the total billable amount for G/L accounts used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "G/L Account".

**Data Sources**
- Job Planning Line

### Item billable price

**Formula**  
The Item Billable Price calculates the total billable amount for items used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "Item".

**Data Sources**
- Job Planning Line

### Resource billable price

**Formula**  
The Resource Billable Price calculates the total billable amount for resources used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "Resource".

**Data Sources**
- Job Planning Line

## Project billable profit

### G/L account billable profit

**Formula**  
*G/L Account Billable Profit = [G/L Account Billable Price](#gl-account-billable-price) - [G/L Account Billable Costs](#gl-account-billable-costs)*

**Data Sources**
- Job Planning Line

### Item billable profit

**Formula**  
*Item Billable Profit = [Item Billable Price](#item-billable-price) - [Item Billable Costs](#item-billable-costs)*

**Data Sources**
- Job Planning Line

### Resource billable profit

**Formula**  
*Resource Billable Profit = [Resource Billable Price](#resource-billable-price) - [Resource Billable Costs](#resource-billable-costs)*

**Data Sources**
- Job Planning Line

## Project budget costs

### G/L account budget costs

**Formula**  
The G/L Account Budget Costs calculates the total budget cost for G/L accounts used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "G/L Account".

**Data Sources**
- Job Planning Line

### Item budget costs

**Formula**  
The Item Budget Costs calculates the total budget cost for items used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "Item".

**Data Sources**
- Job Planning Line

### Resource budget costs

**Formula**  
The Resource Budget Costs calculates the total budget cost for resources used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "Resource".

**Data Sources**
- Job Planning Line

## Project budget price

### G/L account budget price

**Formula**  
The G/L Account Budget Price calculates the total budget amount for G/L accounts used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "G/L Account".

**Data Sources**
- Job Planning Line

### Item budget price

**Formula**  
The Item Budget Price calculates the total budget amount for items used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "Item".

**Data Sources**
- Job Planning Line

### Resource budget price

**Formula**  
The Resource Budget Price calculates the total budget amount for resources used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "Resource".

**Data Sources**
- Job Planning Line

## Project budget profit

### G/L account budget profit

**Formula**  
*G/L Account Budget Profit = [G/L Account Budget Price](#gl-account-budget-price) - [G/L Account Budget Costs](#gl-account-budget-costs)*

**Data Sources**
- Job Planning Line

### Item budget profit

**Formula**  
*Item Budget Profit = [Item Budget Price](#item-budget-price) - [Item Budget Costs](#item-budget-costs)*

**Data Sources**
- Job Planning Line

### Resource budget profit

**Formula**  
*Resource Budget Profit = [Resource Budget Price](#resource-budget-price) - [Resource Budget Costs](#resource-budget-costs)*

**Data Sources**
- Job Planning Line

## Totals for billables

<!-- Billable Totals -->
### Total billable cost

**Formula**  
*Total Billable Cost = [G/L Account Billable Costs](#gl-account-billable-costs) + [Item Billable Costs](#item-billable-costs) + [Resource Billable Costs](#resource-billable-costs)*

**Data Sources**
- Job Planning Line

### Total billable price

**Formula**  
*Total Billable Price = [G/L Account Billable Price](#gl-account-billable-price) + [Item Billable Price](#item-billable-price) + [Resource Billable Price](#resource-billable-price)*

**Data Sources**
- Job Planning Line

### Total billable profit

**Formula**  
*Total Billable Profit = [Billable (Total Price)](#billable-total-price) - [Billable (Total Cost)](#billable-total-cost)*

**Data Sources**
- Job Planning Line

<!-- Budget Totals -->
### Total budget cost

**Formula**  
*Total Budget Cost = [G/L Account Budget Costs](#gl-account-budget-costs) + [Item Budget Costs](#item-budget-costs) + [Resource Budget Costs](#resource-budget-costs)*

**Data Sources**
- Job Planning Line

### Total budget price

**Formula**  
*Total Budget Price = [G/L Account Budget Price](#gl-account-budget-price) + [Item Budget Price](#item-budget-price) + [Resource Budget Price](#resource-budget-price)*

**Data Sources**
- Job Planning Line

### Total budget profit

**Formula**  
*Total Budget Profit = [Total Budget Price](#total-budget-price) - [Total Budget Cost](#total-budget-cost)*

**Data Sources**
- Job Planning Line

## Project purchase measures

- [Amount on PO](#amount-on-po)
- [Amount Rcvd. Not Invoiced](#amount-rcvd-not-invoiced)
- [Outstanding Amt. on PO](#outstanding-amt-on-po)
- [Purchase Order Count](#purchase-order-count)
- [Quantity on PO](#quantity-on-po)

### Amount on PO

**Formula**  
The Amount on PO measure calculates the sum of the amount (in local currency) column in the Purchases table.

**Data Sources**
- Purchase Line

### Amount rcvd. not invoiced

**Formula**  
The Amount Rcvd. Not Invoiced measure calculates the total amount of purchases that have been received but not yet invoiced in the Purchases table.

**Data Sources**
- Purchase Line

### Outstanding amt. on PO

**Formula**  
The Outstanding Amt. on PO measure sums the amount in the Purchases table for outstanding purchase lines linked to projects. The source query includes order and invoice lines where **Outstanding Qty. (Base)** is greater than zero.

**Data Sources**
- Purchase Line

### Purchase order count

**Formula**  
The Purchase Order Count measure calculates the total number of purchase orders in the Purchases table. It uses the CALCULATE function to filter the table and returns the distinct count of the "Document No." column for the filtered rows.

**Data Sources**
- Purchase Line

### Quantity on PO

**Formula**  
The Quantity on PO measure calculates the total quantity of items ordered in the Purchases table. It uses the SUM function to add up all the values in the Quantity (Base) column and returns the result.

**Data Sources**
- Purchase Line

## Obsolete planning line measures

### Billable (total cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Billable (Total Cost) measure calculates the total cost (in local currency) of all project planning lines where the line type is "Billable" or "Both Budget and Billable" in the Project Planning Line table.
  
**Data Sources**
- Job Planning Line

### Billable (total price)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Billable (Total Price) measure calculates the total price (in local currency) of all project planning lines where the line type is "Billable" or "Both Budget and Billable" in the Project Planning Line table.
  
**Data Sources**
- Job Planning Line

### Budget (total cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Budget (Total Cost) measure represents the budgeted cost of resources to be used in a project by calculating the total cost (in local currency) in the Project Planning Line table and selecting only those lines with a line type of "Budget" or "Both Budget and Billable".

**Data Sources**
- Job Ledger Entry

### Budget (total price)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Budget (Total Price) measure represents the budgeted price of resources to be used in a project by calculating the total price (in local currency) in the Project Planning Line table and selecting only those lines with a line type of "Budget" or "Both Budget and Billable".

**Data Sources**
- Job Planning Line

## Project task dates and durations

- [Project Task Duration Days](#project-task-duration-days)
- [Project Task Duration Weeks](#project-task-duration-weeks)
- [Project Task Starting Date](#project-task-starting-date)
- [Project Task Ending Date](#project-task-ending-date)

### Project task starting date

This calculated column returns the earliest **Planning Date** from the project planning lines related to the task.

**Data sources**
- Job Planning Line

### Project task ending date

This calculated column returns the latest **Planning Date** from the project planning lines related to the task.

**Data sources**
- Job Planning Line

### Project task duration days

**Formula**

The Project Task Duration Days measure calculates the duration of a project task in days by finding the earliest and latest planning dates from related Project Planning Lines, then returning the day difference between them.

**Data Sources**
- Project Planning Line

### Project task duration weeks

**Formula**

The Project Task Duration Weeks measure calculates the duration of a project task in weeks by taking the earliest and latest planning dates from related Project Planning Lines, then returning the week difference.

**Data Sources**
- Project Planning Line

## Related information

[Track your business KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI Projects app](projects-powerbi-app.md)  
[Built-in Projects reports](project-reports.md)  
[Project management overview](projects-manage-projects.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
