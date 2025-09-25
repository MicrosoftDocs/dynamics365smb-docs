---
title: Projects KPIs and measures (Power BI)
description: The Projects App KPIs provides a page to clearly identify all KPIs and Measures used in the Projects Report.
author: kennienp
ms.author: kepontop
ms.reviewer: 
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 
ms.date: 11/08/2024
ms.service: dynamics-365-business-central
---

# Power BI Projects app KPIs and measures

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This page provides a list of all Key Performance Indicators (KPIs) included in the semantic model for the Power BI Projects report. 

Explore the list of KPIs below to learn more about how they can help you achieve your business goals. 

Each KPI is described, including how it is calculated and what data was used in the calculations.

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Project Measures

- [No. of Completed Projects](#no-of-completed-projects)
- [Project Count](#project-count)
- [Tasks Count](#tasks-count)
- [Complete (%)](#completed-)
- [Invoiced (%)](#invoiced-)
- [Realization %](#realization-)
- [Realization Variance](#realization-variance)

### No. of Completed Projects

**Formula**  
The No. of Completed Projects measure calculates the number of projects where the Complete column is "Yes".

**Data Sources**
- Job

### Project Count

**Formula**  
The Project Count measure counts the total number of projects in the Project table.

**Data Sources**
- Job

### Tasks Count

**Formula**  
The Tasks Count measure counts the number of rows in the Tasks table that where the Project Task Type has a value of "Posting".

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

### Duration (Days)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Duration (Days) measure calculates the number of days between the earliest starting date and latest ending date for a given project in the Project table.
  
**Data Sources**
- Job

### Realization (%)

**Formula**  
*Realization (%) = [Total Billable Price)](#total-billable-price) / [Total Usage Price](#total-usage-price)*
  
**Data Sources**
- Job Ledger Entry

### Realization Variance

**Formula**  
*Realization Variance = [Total Billable Price](#total-billable-price) - [Total Usage Price](#total-usage-price)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

## Obsolete Measures

### Actual Profit

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
*Actual Profit = [Billable (Invoiced Price)](#billable-invoiced-price) - [Actual (Total Cost)](#actual-total-cost)*
  
**Data Sources**
- Job Ledger Entry

### Actual Profit Margin %

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
*Actual Profit Margin % = [Actual Profit Margin %](#actual-profit-margin-) / [Billable (Invoiced Price)](#billable-invoiced-price)*
  
**Data Sources**
- Job Ledger Entry

### Budget Profit

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
*Budget Profit = - [Budget (Total Price)](#budget-total-price) - [Budget (Total Cost)](#budget-total-cost)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

### Budget Profit Margin %

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
*Budget Profit Margin % = [Budget Profit](#budget-profit) / [Budget (Total Price)](#budget-total-price)*

**Data Sources**
- Job Ledger Entry
- Job Planning Line

## Project Ledger Measures

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

### Project Ledger Entry Quantity
**Formula**  
The Project Ledger Entry Quantity measure aggregates the Qty. column of the Project Ledger Entry table. The sign is then inverted by multiplying by negative one.
  
**Data Sources**
- Project Ledger Entry

### Project Ledger Line Amount
**Formula**  
The Project Ledger Line Amount measure calculates the Project Ledger Line Amount by iterating over each Project Ledger Entry and multiplying Quantity by Unit Price (LCY).
  
**Data Sources**
- Project Ledger Entry

<!-- Invoiced -->
## Invoiced Cost

<!-- Invoiced Cost -->
### G/L Account Invoiced Cost

**Formula**  
The G/L Account Invoiced Cost calculates the total invoiced cost for G/L accounts used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Sale" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Item Invoiced Cost

**Formula**  
The Item Invoiced Cost calculates the total invoiced cost for items used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Sale" and the type is "Item".

**Data Sources**
- Job Ledger Entry

### Resource Invoiced Cost

**Formula**  
The Resource Invoiced Cost calculates the total invoiced cost for resources used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Sale" and the type is "Resource".

**Data Sources**
- Job Ledger Entry

<!-- Invoiced Price -->
## Invoiced Price

### G/L Account Invoiced Price

**Formula**  
The G/L Account Invoiced Price calculates the total invoiced price for G/L accounts used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Sale" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Item Invoiced Price

**Formula**  
The Item Invoiced Price calculates the total invoiced price for items used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Sale" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Resource Invoiced Price

**Formula**  
The Resource Invoiced Price calculates the total invoiced price for resources used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Sale" and the type is "Resource".

**Data Sources**
- Job Ledger Entry

<!-- Invoiced Profit -->
## Invoiced Profit

### G/L Account Invoiced Profit

**Formula**  
*G/L Account Invoiced Profit = [G/L Account Invoiced Price](#gl-account-invoiced-price) - [G/L Account Invoiced Cost](#gl-account-invoiced-cost)*

**Data Sources**
- Job Ledger Entry

### Item Invoiced Profit

**Formula**  
*Item Invoiced Profit = [Item Invoiced Price](#item-invoiced-price) - [Item Invoiced Cost](#item-invoiced-cost)*

**Data Sources**
- Job Ledger Entry

### Resource Invoiced Profit

**Formula**  
*Resource Invoiced Profit = [Resource Invoiced Price](#resource-invoiced-price) - [Resource Invoiced Cost](#resource-invoiced-cost)*

**Data Sources**
- Job Ledger Entry

<!-- Usage -->
## Usage Cost

<!-- Usage Cost-->
### G/L Account Usage Cost

**Formula**  
The G/L Account Usage Cost calculates the total usage cost for G/L accounts used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Usage" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Item Usage Cost

**Formula**  
The Item Usage Cost calculates the total usage cost for items used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Usage" and the type is "Item".

**Data Sources**
- Job Ledger Entry

### Resource Usage Cost

**Formula**  
The Resource Usage Cost calculates the total usage cost for resources used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the entry type is "Usage" and the type is "Resource".

**Data Sources**
- Job Ledger Entry

<!-- Usage Price-->
## Usage Price
### G/L Account Usage Price

**Formula**  
The G/L Account Usage Price calculates the total usage price for G/L accounts used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Usage" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Item Usage Price

**Formula**  
The Item Usage Price calculates the total usage price for items used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Usage" and the type is "G/L Account".

**Data Sources**
- Job Ledger Entry

### Resource Usage Price

**Formula**  
The Resource Usage Price calculates the total usage price for resources used in a project. It uses the SUMX function to calculate the line amount for each entry where the entry type is "Usage" and the type is "Resource".

**Data Sources**
- Job Ledger Entry

<!-- Usage Profit-->
## Usage Profit

### G/L Account Usage Profit

**Formula**  
*G/L Account Usage Profit = [G/L Account Usage Price](#gl-account-usage-price) - [G/L Account Usage Cost](#gl-account-usage-cost)*

**Data Sources**
- Job Ledger Entry

### Item Usage Profit

**Formula**  
*Item Usage Profit = [Item Usage Price](#item-usage-price) - [Item Usage Cost](#item-usage-cost)*

**Data Sources**
- Job Ledger Entry

### Resource Usage Profit

**Formula**  
*Resource Usage Profit = [Resource Usage Price](#resource-usage-price) - [Resource Usage Cost](#resource-usage-cost)*

**Data Sources**
- Job Ledger Entry

## Totals

### Total Invoiced Costs

**Formula**  
*Total Invoiced Costs = [G/L Account Invoiced Cost](#gl-account-invoiced-cost) + [Item Invoiced Cost](#item-invoiced-cost) + [Resource Invoiced Cost](#resource-invoiced-cost)*

**Data Sources**
- Job Ledger Entry

### Total Invoiced Price

**Formula**  
*Total Invoiced Price = [G/L Account Invoiced Price](#gl-account-invoiced-price) + [Item Invoiced Price](#item-invoiced-price) + [Resource Invoiced Price](#resource-invoiced-price)*

**Data Sources**
- Job Ledger Entry

### Total Invoiced Profit

**Formula**  
*Total Invoiced Profit = [G/L Account Invoiced Profit](#gl-account-invoiced-profit) + [Item Invoiced Profit](#item-invoiced-profit) + [Resource Invoiced Profit](#resource-invoiced-profit)*

**Data Sources**
- Job Ledger Entry

### Total Invoiced Profit Margin %

**Formula**  
*Total Invoiced Profit Margin % = [Total Invoiced Profit](#total-invoiced-profit) / [Total Invoiced Price](#total-invoiced-price)*

**Data Sources**
- Job Ledger Entry

### Total Usage Cost

**Formula**  
*Total Usage Costs = [G/L Account Usage Cost](#gl-account-usage-cost) + [Item Usage Cost](#item-usage-cost) + [Resource Usage Cost](#resource-usage-cost)*

**Data Sources**
- Job Ledger Entry

### Total Usage Price

**Formula**  
*Total Usage Price = [G/L Account Usage Price](#gl-account-usage-price) + [Item Usage Price](#item-usage-price) + [Resource Usage Price](#resource-usage-price)*

**Data Sources**
- Job Ledger Entry

### Total Usage Profit

**Formula**  
*Total Usage Profit = [Total Usage Price](#total-usage-price) - [Total Usage Cost](#total-usage-cost) *

**Data Sources**
- Job Ledger Entry

### Total Usage Profit Margin %

**Formula**  
*Total Usage Profit Margin % = [Total Usage Profit](#total-usage-profit) / [Total Usage Price](#total-usage-price)*

**Data Sources**
- Job Ledger Entry

## Obsolete Measures

### Actual (Total Price)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Actual (Total Price) measure calculates the total actual cost of project entries by calculating the total price (in local currency) in the Project Ledger Entry table and selecting only those entries with an entry type of "Usage". The result of this calculation is then converted to a positive value.
  
**Data Sources**
- Job Ledger Entry

### Billable (Invoiced Price)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Billable (Invoiced Price) measure shows the total invoiced price of billable project entries by calculating the total price (in local currency) in the Project Ledger Entry table and selecting only those entries with an entry type of "Sale", which indicates that the project entry is billable.
  
**Data Sources**
- Job Ledger Entry

### Invoiced (Total Cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Invoiced (Total Cost) measure calculates the total cost of all project ledger entries where the entry type is "Sale" in the Project Ledger Entry table.
  
**Data Sources**
- Job Ledger Entry

### Invoiced (Total Price)

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

### Total Price

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Total Price measure calculates the total price of all project ledger entries in the Project Ledger Entry table. It uses the SUMX function to iterate over each row in the table and multiply the quantity and unit price (in local currency) columns for each row. The results of each multiplication are then summed up to produce the total price.

**Data Sources**
- Job Ledger Entry

### Actual (Total Cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Actual (Total Cost) measure calculates the total cost (in local currency) of all project ledger entries where the type is "Usage" in the Project Ledger Entry table.
  
**Data Sources**
- Job Ledger Entry

### Gen. Journal Usage (Total Cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Gen. Journal Usage (Total Cost) measure calculates the total cost of all project ledger entries where the type is "G/L Account" in the Project Ledger Entry table.
  
**Data Sources**
- Job Ledger Entry

### Labour Usage (Total Cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Labour Usage (Total Cost) measure calculates the total cost of all project ledger entries where the type is "Resource" in the Project Ledger Entry table.
  
**Data Sources**
- Job Ledger Entry

### Material Usage (Total Cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Material Usage (Total Cost) measure calculates the total cost of all project ledger entries where the type is "Item" in the Project Ledger Entry table.
  
**Data Sources**
- Job Ledger Entry

## Planning Line Measures

- [Planning Line Quantity](#planning-line-quantity)
- [Planning Line Total Cost (LCY)](#planning-line-total-cost-lcy)
- [Planning Line Total Price (LCY)](#planning-line-total-price-lcy)
- [Total Cost Variance to Budget](#total-cost-variance-to-budget)
- [Total Cost Variance to Budget %](#total-cost-variance-to-budget-)
<!-- Statistics -->
- [G/L Account Billable Costs](#gl-account-billable-costs)
- [Item Billable Costs](#item-billable-costs)
- [Resource Billable Costs](#resource-billable-costs)

- [G/L Account Billable Price](#gl-account-billable-price)
- [Item Billable Price](#item-billable-price)
- [Resource Billable Price](#resource-billable-price)

- [G/L Account Billable Profit](#gl-account-billable-profit)
- [Item Billable Profit](#item-billable-profit)
- [Resource Billable Profit](#resource-billable-profit)

- [G/L Account Budget Costs](#gl-account-budget-costs)
- [Item Budget Costs](#item-budget-costs)
- [Resource Budget Costs](#resource-budget-costs)

- [G/L Account Budget Price](#gl-account-budget-price)
- [Item Budget Price](#item-budget-price)
- [Resource Budget Price](#resource-budget-price)

- [G/L Account Budget Profit](#gl-account-budget-profit)
- [Item Budget Profit](#item-budget-profit)
- [Resource Budget Profit](#resource-budget-profit)

- [Total Billable Cost](#total-billable-cost)
- [Total Billable Price](#total-billable-price)
- [Total Billable Profit](#total-billable-profit)
- [Total Budget Cost](#total-budget-cost)
- [Total Budget Price](#total-budget-price)
- [Total Budget Profit](#total-budget-profit)

### Planning Line Quantity

**Formula**  
The Planning Line Quantity measure calculates the sum of the Quantity column in the Project Planning Line table.

**Data Sources**
- Job Planning Line

### Planning Line Total Cost (LCY)

**Formula**  
The Planning Line Total Cost (LCY) measure calculates the total cost of all project planning lines in the Project Planning Line table. It uses the SUMX function to iterate over each row in the table and multiply the quantity and unit cost (in local currency) columns for each row. The results of each multiplication are then summed up to produce the total cost.

**Data Sources**
- Job Planning Line

### Planning Line Total Price (LCY)

**Formula**  
The Planning Line Total Price (LCY) measure calculates the total price of all project planning lines in the Project Planning Line table. It uses the SUMX function to iterate over each row in the table and multiply the quantity and unit price (in local currency) columns for each row. The results of each multiplication are then summed up to produce the total price.

**Data Sources**
- Job Planning Line

### Total Cost Variance to Budget

**Formula**  
*Total Cost Variance to Budget = [Total Usage Cost](#total-usage-cost) - [Total Budget Cost](#total-budget-cost)*

**Data Sources**
- Job Ledger Entry

### Total Cost Variance to Budget %

**Formula**  
*Total Cost Variance to Budget % = [Total Cost Variance to Budget %](#total-cost-variance-to-budget) / [Total Budget Cost)](#total-budget-cost)*

**Data Sources**
- Job Ledger Entry

## Billable Costs

### G/L Account Billable Costs

**Formula**  
The G/L Account Billable Costs calculates the total billable cost for G/L accounts used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "G/L Account".

**Data Sources**
- Job Planning Line

### Item Billable Costs

**Formula**  
The Item Billable Costs calculates the total billable cost for items used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "Item".

**Data Sources**
- Job Planning Line

### Resource Billable Costs

**Formula**  
The Resource Billable Costs calculates the total billable cost for resources used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "Resource".

**Data Sources**
- Job Planning Line

## Billable Price

### G/L Account Billable Price

**Formula**  
The G/L Account Billable Price calculates the total billable amount for G/L accounts used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "G/L Account".

**Data Sources**
- Job Planning Line

### Item Billable Price

**Formula**  
The Item Billable Price calculates the total billable amount for items used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "Item".

**Data Sources**
- Job Planning Line

### Resource Billable Price

**Formula**  
The Resource Billable Price calculates the total billable amount for resources used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Billable" or "Both Budget and Billable" and the type is "Resource".

**Data Sources**
- Job Planning Line

## Billable Profit

### G/L Account Billable Profit

**Formula**  
*G/L Account Billable Profit = [G/L Account Billable Price](#gl-account-billable-price) - [G/L Account Billable Costs](#gl-account-billable-costs)*

**Data Sources**
- Job Planning Line

### Item Billable Profit

**Formula**  
*Item Billable Profit = [Item Billable Price](#item-billable-price) - [Item Billable Costs](#item-billable-costs)*

**Data Sources**
- Job Planning Line

### Resource Billable Profit

**Formula**  
*Resource Billable Profit = [Resource Billable Price](#resource-billable-price) - [Resource Billable Costs](#resource-billable-costs)*

**Data Sources**
- Job Planning Line

## Budget Costs

### G/L Account Budget Costs

**Formula**  
The G/L Account Budget Costs calculates the total budget cost for G/L accounts used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "G/L Account".

**Data Sources**
- Job Planning Line

### Item Budget Costs

**Formula**  
The Item Budget Costs calculates the total budget cost for items used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "Item".

**Data Sources**
- Job Planning Line

### Resource Budget Costs

**Formula**  
The Resource Budget Costs calculates the total budget cost for resources used in a project. It uses the SUM function to add up all entries by the Total Cost (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "Resource".

**Data Sources**
- Job Planning Line

## Budget Price

### G/L Account Budget Price

**Formula**  
The G/L Account Budget Price calculates the total budget amount for G/L accounts used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "G/L Account".

**Data Sources**
- Job Planning Line

### Item Budget Price

**Formula**  
The Item Budget Price calculates the total budget amount for items used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "Item".

**Data Sources**
- Job Planning Line

### Resource Budget Price

**Formula**  
The Resource Budget Price calculates the total budget amount for resources used in a project. It uses the SUM function to add up all entries by the Line Amount (LCY) column where the line type is "Budget" or "Both Budget and Billable" and the type is "Resource".

**Data Sources**
- Job Planning Line

## Budget Profit

### G/L Account Budget Profit

**Formula**  
*G/L Account Budget Profit = [G/L Account Budget Price](#gl-account-budget-price) - [G/L Account Budget Costs](#gl-account-budget-costs)*

**Data Sources**
- Job Planning Line

### Item Budget Profit

**Formula**  
*Item Budget Profit = [Item Budget Price](#item-budget-price) - [Item Budget Costs](#item-budget-costs)*

**Data Sources**
- Job Planning Line

### Resource Budget Profit

**Formula**  
*Resource Budget Profit = [Resource Billable Price](#resource-budget-price) - [Resource Budget Costs](#resource-budget-costs)*

**Data Sources**
- Job Planning Line

## Totals

<!-- Billable Totals -->
### Total Billable Cost

**Formula**  
*Total Billable Cost = [G/L Account Billable Costs](#gl-account-billable-costs) + [Item Billable Costs](#item-billable-costs) + [Resource Billable Costs](#resource-billable-costs)*

**Data Sources**
- Job Planning Line

### Total Billable Price

**Formula**  
*Total Billable Price = [G/L Account Billable Price](#gl-account-billable-price) + [Item Billable Price](#item-billable-price) + [Resource Billable Price](#resource-billable-price)*

**Data Sources**
- Job Planning Line

### Total Billable Profit

**Formula**  
*Total Billable Profit = [Total Billable Price](#total-billable-price) + [Total Billable Costs](#total-billable-cost)*

**Data Sources**
- Job Planning Line

<!-- Budget Totals -->
### Total Budget Cost

**Formula**  
*Total Budget Cost = [G/L Account Budget Costs](#gl-account-budget-costs) + [Item Budget Costs](#item-budget-costs) + [Resource Budget Costs](#resource-budget-costs)*

**Data Sources**
- Job Planning Line

### Total Budget Price

**Formula**  
*Total Budget Price = [G/L Account Budget Price](#gl-account-budget-price) + [Item Budget Price](#item-budget-price) + [Resource Budget Price](#resource-budget-price)*

**Data Sources**
- Job Planning Line

### Total Budget Profit

**Formula**  
*Total Budget Profit = [Total Budget Price](#total-budget-price) + [Total Budget Costs](#total-budget-cost)*

**Data Sources**
- Job Planning Line

## Purchase Measures
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

### Amount Rcvd. Not Invoiced

**Formula**  
The Amount Rcvd. Not Invoiced measure calculates the total amount of purchases that have been received but not yet invoiced in the Purchases table.

**Data Sources**
- Purchase Line

### Amount Rcvd. Not Invoiced

**Formula**  
The Amount Rcvd. Not Invoiced measure calculates the total amount of purchases that have been received but not yet invoiced in the Purchases table.

**Data Sources**
- Purchase Line

### Outstanding Amt. on PO

**Formula**  
The Outstanding Amt. on PO measure calculates the total amount of outstanding purchase orders in the Purchases table.

**Data Sources**
- Purchase Line

### Purchase Order Count

**Formula**  
The Purchase Order Count measure calculates the total number of purchase orders in the Purchases table. It uses the CALCULATE function to filter the table and returns the distinct count of the "Document No." column for the filtered rows.

**Data Sources**
- Purchase Line

### Quantity on PO

**Formula**  
The Quantity on PO measure calculates the total quantity of items ordered in the Purchases table. It uses the SUM function to add up all the values in the Quantity (Base) column and returns the result.

**Data Sources**
- Purchase Line

## Obsolete Measures 2

### Billable (Total Cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Billable (Total Cost) measure calculates the total cost (in local currency) of all project planning lines where the line type is "Billable" or "Both Budget and Billable" in the Project Planning Line table.
  
**Data Sources**
- Job Planning Line

### Billable (Total Price)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Billable (Total Price) measure calculates the total price (in local currency) of all project planning lines where the line type is "Billable" or "Both Budget and Billable" in the Project Planning Line table.
  
**Data Sources**
- Job Planning Line

### Budget (Total Cost)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Budget (Total Cost) measure represents the budgeted cost of resources to be used in a project by calculating the total cost (in local currency) in the Project Planning Line table and selecting only those lines with a line type of "Budget" or "Both Budget and Billable".

**Data Sources**
- Job Ledger Entry

### Budget (Total Price)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Budget (Total Price) measure represents the budgeted price of resources to be used in a project by calculating the total price (in local currency) in the Project Planning Line table and selecting only those lines with a line type of "Budget" or "Both Budget and Billable".

**Data Sources**
- Job Planning Line

## Tasks

- [Project Task Duration Days](#project-task-duration-days)
- [Project Task Duration Weeks](#project-task-duration-weeks)

### Project Task Duration Days

**Formula**

The Project Task Duration Days measure calculates the duration of a project task in days by finding the earliest and latest planning dates from related Project Planning Lines, then returning the day difference between them.

**Data Sources**
- Project Planning Line

### Project Task Duration Weeks

**Formula**

The Project Task Duration Days measure calculates the duration of a project task in weeks by taking the earliest and latest planning dates from related Project Planning Lines, then returning the week difference.

**Data Sources**
- Project Planning Line

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Projects app](projects-powerbi-app.md)  
[Built-in Projects reports](project-reports.md)  
[Project management overview](projects-manage-projects.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
