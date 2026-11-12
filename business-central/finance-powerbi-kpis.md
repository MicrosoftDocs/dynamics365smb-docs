---
title: Finance App KPIs and Measures (Power BI)
description: Explore finance KPIs and measures in the Business Central Power BI Finance app semantic model, including calculations and the data each measure uses.
author: kennienp
ms.author: kepontop
ms.topic: reference
ai-usage: ai-assisted
ms.search.keywords: reporting
ms.date: 10/31/2024
ms.service: dynamics-365-business-central
---

# Power BI finance app KPIs and measures

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This page provides a list of all Key Performance Indicators (KPIs) included in the semantic model for the Power BI Finance report. 

Explore the list of KPIs below to learn more about how they can help you achieve your business goals. 

Each KPI and measure is described, including how it is calculated and what data was used in the calculations.

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]


## Activity KPIs

- [% Change in Operating Profit - EBIT](#-change-in-operating-profit---ebit) 
- [% Change in Revenue](#-change-in-revenue) 
- [Asset Turnover Ratio](#asset-turnover-ratio)  
- [Average Collection Period (Days)](#average-collection-period-days)  
- [Cash Conversion Cycle - CCC](#cash-conversion-cycle---ccc)
- [Days Payable Outstanding - DPO](#days-payable-outstanding---dpo)  
- [Days Sales Of Inventory - DSI](#days-sales-of-inventory---dsi)  
- [Days Sales Outstanding - DSO](#days-sales-outstanding---dso)  
- [Degree Of Operating Leverage - DOL](#degree-of-operating-leverage---dol)  
- [Inventory Turnover](#inventory-turnover)  
- [No. of Days](#no-of-days)


### % change in operating profit - EBIT
**Formula**  
( [Operating Profit - EBIT (Balance at Date)](#operating-profit---ebit-balance-at-date) - [Operating Profit - EBIT (Beginning Balance)](#operating-profit---ebit-beginning-balance) ) / [Operating Profit - EBIT (Beginning Balance)](#operating-profit---ebit-beginning-balance)

**Data Sources**
- G/L Entry
- G/L Account Category

### % change in revenue
**Formula**  
( [Revenue (Balance at Date)](#revenue-balance-at-date) - [Revenue (Beginning Balance)](#revenue-beginning-balance) ) / [Revenue (Beginning Balance)](#revenue-beginning-balance)

**Data Sources**
- G/L Entry
- G/L Account Category

### Asset turnover ratio
**Formula**  
[Revenue](#revenue) / [Assets](#assets)

**Data Sources**
- G/L Entry
- G/L Account Category

### Average collection period (days)
**Formula**  
( [No. of Days](#no-of-days) * [Accounts Receivable (Net Change)](#accounts-receivable-net-change) ) / [Revenue](#revenue)

**Data Sources**
- Date
- G/L Entry
- G/L Account Category

### Cash conversion cycle - CCC
**Formula**  
[Days Sales Of Inventory - DSI](#days-sales-of-inventory---dsi) + [Days Sales Outstanding - DSO](#days-sales-outstanding---dso) - [Days Payable Outstanding - DPO](#days-payable-outstanding---dpo)

**Data Sources**
- G/L Entry
- G/L Account Category

### Days payable outstanding - DPO
**Formula**  
 ( [Accounts Payable](#accounts-payable) / [Cost of Goods Sold](#cost-of-goods-sold) ) * [No. of Days](#no-of-days)

**Data Sources**
- Date
- G/L Entry
- G/L Account Category

 
### Days sales of inventory - DSI
**Formula**  
( [Inventory](#inventory) / [Cost of Goods Sold](#cost-of-goods-sold) ) * [No. of Days](#no-of-days)

**Data Sources**
- Date
- G/L Entry
- G/L Account Category

### Days sales outstanding - DSO
**Formula**  
 ( [Accounts Receivable](#accounts-receivable) / [Revenue](#revenue) ) * [No. of Days](#no-of-days)

**Data Sources**
- Date
- G/L Entry
- G/L Account Category

### Degree of operating leverage - DOL
**Formula**  
[% Change in Operating Profit - EBIT](#-change-in-operating-profit---ebit) / [% Change in Revenue](#-change-in-revenue)

**Data Sources**
- G/L Entry
- G/L Account Category

### Inventory turnover
**Formula**  
[Cost of Goods Sold](#cost-of-goods-sold) / [Inventory (Average)](#inventory-average)

**Data Sources**
- G/L Entry
- G/L Account Category

### No. of days
**Formula**

The No. of Days measure calculates the total number of days within a selected period by counting the rows between the earliest (MIN) and latest (MAX) dates in the Date table. This measure provides a count of days for the specified date range in the context.

**Date Sources**
- Date

## Balance sheet measures

- [Accounts Payable](#accounts-payable)   
- [Accounts Payable (Neg)](#accounts-payable-neg)   
- [Accounts Receivable](#accounts-receivable)   
- [Accounts Receivable (Average)](#accounts-receivable-average)   
- [Accounts Receivable (Beginning Balance)](#accounts-receivable-beginning-balance)   
- [Accounts Receivable (Net Change)](#accounts-receivable-net-change)
- [Assets](#assets)
- [Capital Employed](#capital-employed)   
- [Current Assets](#current-assets)   
- [Current Liabilities](#current-liabilities)
- [Equity](#equity)   
- [Fixed Assets](#fixed-assets)   
- [Inventory](#inventory)   
- [Inventory (Average)](#inventory-average)   
- [Inventory (Beginning Balance)](#inventory-beginning-balance)   
- [Liabilities](#liabilities)
- [Liabilities & Equity](#liabilities--equity)   
- [Liabilities (Neg)](#liabilities-neg)   
- [Liquid Assets](#liquid-assets)   
- [Longterm Liabilities](#longterm-liabilities)   
- [Payroll Liabilities](#payroll-liabilities)   
- [Purchase Prepayments](#purchase-prepayments)   
- [Shareholders' Equity](#shareholders-equity)   
- [Working Capital](#working-capital)   

### Accounts payable
**Formula**  
The Accounts Payable measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Accounts Payable* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Accounts Payable (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Accounts payable (neg)
**Formula**  
The Accounts Payable measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Accounts Payable* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Accounts Payable (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories
 
### Accounts receivable
**Formula**  
The Accounts Receivable measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Accounts Receivable* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Accounts Receivable (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Accounts receivable (average)
**Formula**  
( [Accounts Receivable (Beginning Balance)](#accounts-receivable-beginning-balance) + [Accounts Receivable](#accounts-receivable) ) / 2

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Accounts receivable (beginning balance)
**Formula**  
The Accounts Receivable (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [accounts receivable](#accounts-receivable) before the earliest date in the selected period. It removes filters on the date column and includes only dates earlier than the first selected date.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Accounts receivable (net change)
**Formula**  
The Accounts Receivable (Net Change) measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Accounts Receivable* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Accounts Receivable (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Assets
**Formula**  
The Assets measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Assets* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Assets (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Current assets
**Formula**  
The Current Assets measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Current Assets* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Current Assets (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Fixed assets
**Formula**  
The Fixed Assets measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Fixed Assets* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Fixed Assets (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Inventory
**Formula**  
The Inventory measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Inventory* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Inventory (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Inventory (average)
**Formula**  
( [Inventory (Beginning Balance)](#inventory-beginning-balance) + [Inventory](#inventory) ) / 2

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Inventory (beginning balance)
**Formula**  
The Inventory (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [Inventory](#inventory) before the earliest date in the selected period. It removes filters on the date column and includes only dates earlier than the first selected date.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Liquid assets
**Formula**  
The Liquid Assets measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Cash* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Liquid Assets (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Capital employed
**Formula**  
[Assets](#assets) - [Current Liabilities](#current-liabilities)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
### Equity
**Formula**  
The Equity measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Equity* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Equity (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

It multiplies the balance by -1 to reverse the sign of credit balances.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 

### Current liabilities
**Formula**  
The Current Liabilities measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Current Liabilities* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Current Liabilities (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
### Liabilities

**Formula**  
The Liabilities measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Liabilities* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Liabilities (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
### Liabilities (neg)
**Formula**  
The Liabilities measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Liabilities* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Liabilities (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 

### Liabilities & equity
**Formula**  
[Liabilities](#liabilities) + [Equity](#equity)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 

### Longterm liabilities
**Formula**  
The Longterm Liabilities measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Longterm Liabilities* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Longterm Liabilities (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
### Payroll liabilities
**Formula**  
The Payroll Liabilities measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Payroll Liabilities* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Payroll Liabilities (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
### Purchase prepayments
**Formula**  
The Purchase Prepayments measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Purchase Prepayments* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Purchase Prepayments (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
### Shareholders equity
**Formula**  
The Shareholders Equity measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Common Stock* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Shareholder's Equity (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

It multiplies the balance by -1 to reverse the sign of credit balances.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
   
### Working capital
**Formula**  
[Current Assets](#current-assets) - [Current Liabilities](#current-liabilities)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
## Income statement measures

The Revenue, Interest Revenue, FX Gains Revenue, and Extraordinary Revenue measures multiply the underlying net change by -1 to reverse the sign of credit balances. Their Balance at Date and Beginning Balance variants apply the same sign reversal to the corresponding balances.
- [Cost of Goods Sold](#cost-of-goods-sold)
- [Depreciation and Amortization](#depreciation-and-amortization)
- [Expense](#expense) 
- [Expense (Balance at Date)](#expense-balance-at-date)  
- [Expense (Beginning Balance)](#expense-beginning-balance)  
- [Extraordinary Expense](#extraordinary-expense)   
- [Extraordinary Expense (Balance at Date)](#extraordinary-expense-balance-at-date)   
- [Extraordinary Expense (Beginning Balance)](#extraordinary-expense-beginning-balance)   
- [Extraordinary Revenue](#extraordinary-revenue)   
- [Extraordinary Revenue (Balance at Date)](#extraordinary-revenue-balance-at-date)   
- [Extraordinary Revenue (Beginning Balance)](#extraordinary-revenue-beginning-balance)   
- [FX Gains Revenue](#fx-gains-revenue) 
- [FX Gains Revenue (Balance at Date)](#fx-gains-revenue-balance-at-date) 
- [FX Gains Revenue (Beginning Balance)](#fx-gains-revenue-beginning-balance)  
- [FX Losses Expense](#fx-losses-expense)     
- [FX Losses Expense (Balance at Date)](#fx-losses-expense-balance-at-date)     
- [FX Losses Expense (Beginning Balance)](#fx-losses-expense-beginning-balance)    
- [Interest Expense](#interest-expense)   
- [Interest Expense (Balance at Date)](#interest-expense-balance-at-date)   
- [Interest Expense (Beginning Balance)](#interest-expense-beginning-balance)   
- [Interest Revenue](#interest-revenue)    
- [Interest Revenue (Balance at Date)](#interest-revenue-balance-at-date)   
- [Interest Revenue (Beginning Balance)](#interest-revenue-beginning-balance)   
- [Operating Expense - OPEX](#operating-expense---opex) 
- [Operating Expense - OPEX (Balance at Date)](#operating-expense---opex-balance-at-date)   
- [Operating Expense - OPEX (Beginning Balance)](#operating-expense---opex-beginning-balance)    
- [Operating Revenue](#operating-revenue)   
- [Operating Revenue (Balance at Date)](#operating-revenue-balance-at-date)   
- [Operating Revenue (Beginning Balance)](#operating-revenue-beginning-balance)   
- [Purchases](#purchases)  
- [Revenue](#revenue) 
- [Revenue (Balance at Date)](#revenue-balance-at-date) 
- [Revenue (Beginning Balance)](#revenue-beginning-balance) 
- [Tax Expense](#tax-expense)   
- [Tax Expense (Balance at Date)](#tax-expense-balance-at-date)   
- [Tax Expense (Beginning Balance)](#tax-expense-beginning-balance)   

### Cost of goods sold
**Formula**  
The Cost of Goods Sold measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Cost of Goods Sold* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Cost of Goods Sold (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Depreciation and amortization
**Formula**  
The Depreciation and Amortization measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Depreciation and Amortization* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Depreciation and Amortization Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Expense
**Formula**  
The Expense measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Expense (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Expense (balance at date)
**Formula**  
The Expense measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Expense (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Expense (beginning balance)
**Formula**  
The Expense (Beginning Balance) measure calculates [Expense (Balance at Date)](#expense-balance-at-date) using dates strictly before the first selected date.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary expense
**Formula**  
The Extraordinary Expense measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Extraordinary Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Extraordinary Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary expense (balance at date)
**Formula**  
The Extraordinary Expense (Balance at Date) measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Extraordinary Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Extraordinary Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary expense (beginning balance)
**Formula**  
The Extraordinary Expense (Beginning Balance) measure calculates [Extraordinary Expense (Balance at Date)](#extraordinary-expense-balance-at-date) using dates strictly before the first selected date.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary revenue
**Formula**  
The Extraordinary Revenue measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Extraordinary Revenue* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Extraordinary Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary revenue (balance at date)
**Formula**  
The Extraordinary Revenue (Balance at Date) measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Extraordinary Revenue* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Extraordinary Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary revenue (beginning balance)
**Formula**  
The Extraordinary Revenue (Beginning Balance) measure calculates [Extraordinary Revenue (Balance at Date)](#extraordinary-revenue-balance-at-date) using dates strictly before the first selected date, including the revenue sign reversal.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories


### FX gains revenue
**Formula**  
The FX Gains Revenue measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *FX Gains Revenue* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **FX Gains Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### FX gains revenue (balance at date)
**Formula**  
The FX Gains Revenue measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *FX Gains Revenue* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **FX Gains Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### FX gains revenue (beginning balance)
**Formula**  
The FX Gains Revenue (Beginning Balance) measure calculates [FX Gains Revenue (Balance at Date)](#fx-gains-revenue-balance-at-date) using dates strictly before the first selected date, including the revenue sign reversal.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### FX losses expense
**Formula**  
The FX Losses Expense measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *FX Losses Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **FX Losses (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### FX losses expense (balance at date)
**Formula**  
The FX Losses Expense measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *FX Losses Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **FX Losses Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### FX losses expense (beginning balance)
**Formula**  
The FX Losses Expense (Beginning Balance) measure calculates [FX Losses Expense (Balance at Date)](#fx-losses-expense-balance-at-date) using dates strictly before the first selected date.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest expense
**Formula**  
The Interest Expense measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Interest Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Interest Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest expense (balance at date)
**Formula**  
The Interest Expense measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Interest Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Interest Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest expense (beginning balance)
**Formula**  
The Interest Expense (Beginning Balance) measure calculates [Interest Expense (Balance at Date)](#interest-expense-balance-at-date) using dates strictly before the first selected date.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest revenue
**Formula**  
The Interest Revenue measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Income, Interest* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Interest Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest revenue (balance at date)
**Formula**  
The Interest Revenue measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Income, Interest* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Interest Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest revenue (beginning balance)
**Formula**  
The Interest Revenue (Beginning Balance) measure calculates [Interest Revenue (Balance at Date)](#interest-revenue-balance-at-date) using dates strictly before the first selected date, including the revenue sign reversal.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating expense - OPEX
**Formula**  
[Expense](#expense) - [Interest Expense](#interest-expense) - [FX Losses Expense](#fx-losses-expense) - [Tax Expense](#tax-expense) - [Extraordinary Expense](#extraordinary-expense)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating expense - OPEX (balance at date)
**Formula**  
[Expense (Balance at Date)](#expense-balance-at-date) - [Interest Expense (Balance at Date)](#interest-expense-balance-at-date) - [FX Losses Expense (Balance at Date)](#fx-losses-expense-balance-at-date) - [Tax Expense (Balance at Date)](#tax-expense-balance-at-date) - [Extraordinary Expense (Balance at Date)](#extraordinary-expense-balance-at-date)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating expense - OPEX (beginning balance)
**Formula**  
[Expense (Beginning Balance)](#expense-beginning-balance) - [Interest Expense (Beginning Balance)](#interest-expense-beginning-balance) - [FX Losses Expense (Beginning Balance)](#fx-losses-expense-beginning-balance) - [Tax Expense (Beginning Balance)](#tax-expense-beginning-balance) - [Extraordinary Expense (Beginning Balance)](#extraordinary-expense-beginning-balance)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating revenue
**Formula**  
[Revenue](#revenue) - [Interest Revenue](#interest-revenue) - [FX Gains Revenue](#fx-gains-revenue) - [Extraordinary Revenue](#extraordinary-revenue)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating revenue (balance at date)
**Formula**  
[Revenue (Balance at Date)](#revenue-balance-at-date) - [Interest Revenue (Balance at Date)](#interest-revenue-balance-at-date) - [FX Gains Revenue (Balance at Date)](#fx-gains-revenue-balance-at-date) - [Extraordinary Revenue (Balance at Date)](#extraordinary-revenue-balance-at-date)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating revenue (beginning balance)
**Formula**  
[Revenue (Beginning Balance)](#revenue-beginning-balance) - [Interest Revenue (Beginning Balance)](#interest-revenue-beginning-balance) - [FX Gains Revenue (Beginning Balance)](#fx-gains-revenue-beginning-balance) - [Extraordinary Revenue (Beginning Balance)](#extraordinary-revenue-beginning-balance)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Purchases
**Formula**  
The Purchases measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Purchases* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Purchases (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Revenue
**Formula**  
The Revenue measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Income* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Revenue (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Revenue (balance at date)
**Formula**  
The Revenue measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Income* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Revenue (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Revenue (beginning balance)
**Formula**  
The Revenue (Beginning Balance) measure calculates [Revenue (Balance at Date)](#revenue-balance-at-date) using dates strictly before the first selected date, including the revenue sign reversal.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Tax expense
**Formula**  
The Tax Expense measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Tax Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Tax Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Tax expense (balance at date)
**Formula**  
The Tax Expense measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Tax Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Tax Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Tax expense (beginning balance)
**Formula**  
The Tax Expense (Beginning Balance) measure calculates [Tax Expense (Balance at Date)](#tax-expense-balance-at-date) using dates strictly before the first selected date.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

## Liquidity KPIs
- [Cash Ratio](#cash-ratio) 
- [Current Ratio](#current-ratio) 
- [Quick Ratio](#quick-ratio) 

### Cash ratio
**Formula**  
[Liquid Assets](#liquid-assets) / [Current Liabilities](#current-liabilities)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Current ratio
**Formula**  
[Current Assets](#current-assets) / [Current Liabilities](#current-liabilities)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Quick ratio
**Formula**  
 ( [Current Assets](#current-assets) - [Inventory](#inventory) - [Purchase Prepayments](#purchase-prepayments) ) / [Current Liabilities](#current-liabilities)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

## Profitability KPIs
- [Debt Ratio](#debt-ratio)
- [Debt/Equity Ratio](#debtequity-ratio)  
- [EBITDA](#ebitda)
- [Gross Profit](#gross-profit)
- [Gross Profit Margin](#gross-profit-margin)
- [Net Profit](#net-profit)
- [Net Profit Margin](#net-profit-margin)
- [Operating Profit - EBIT](#operating-profit---ebit)
- [Operating Profit - EBIT (Balance at Date)](#operating-profit---ebit-balance-at-date)
- [Operating Profit - EBIT (Beginning Balance)](#operating-profit---ebit-beginning-balance)
- [Operating Profit Margin](#operating-profit-margin) 
- [Return On Assets - ROA](#return-on-assets---roa) 
- [Return On Capital Employed - ROCE](#return-on-capital-employed---roce)
- [Return On Equity - ROE](#return-on-equity---roe)
- [Return On Net Assets - RONA](#return-on-net-assets---rona)  
- [Shareholder Equity Ratio](#shareholder-equity-ratio)  

### Debt ratio
**Formula**  
[Liabilities](#liabilities) / [Assets](#assets)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Debt/equity ratio
**Formula**  
[Liabilities](#liabilities) / [Shareholder's Equity](#shareholders-equity)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### EBITDA
**Formula**  
[Operating Profit - EBIT](#operating-profit---ebit) + [Depreciation and Amortization](#depreciation-and-amortization)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Gross profit
**Formula**  
[Revenue](#revenue) - [Cost of Goods Sold](#cost-of-goods-sold)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Gross profit margin
**Formula**  
[Gross Profit](#gross-profit) / [Revenue](#revenue)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Net profit
**Formula**  
[Revenue](#revenue) - [Cost of Goods Sold](#cost-of-goods-sold) - [Expense](#expense)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Net profit margin
**Formula**  
[Net Profit](#net-profit) / [Revenue](#revenue)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating profit - EBIT
**Formula**  
[Operating Revenue](#operating-revenue) - [Operating Expense - OPEX](#operating-expense---opex)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating profit - EBIT (balance at date)
**Formula**  
[Operating Revenue (Balance at Date)](#operating-revenue-balance-at-date) - [Operating Expense - OPEX (Balance at Date)](#operating-expense---opex-balance-at-date)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating profit - EBIT (beginning balance)
**Formula**  
[Operating Revenue (Beginning Balance)](#operating-revenue-beginning-balance) - [Operating Expense - OPEX (Beginning Balance)](#operating-expense---opex-beginning-balance)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating profit margin
**Formula**  
[Operating Profit - EBIT](#operating-profit---ebit) / [Operating Revenue](#operating-revenue)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Return on assets - ROA
**Formula**  
[Net Profit](#net-profit) / [Assets](#assets)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Return on capital employed - ROCE
**Formula**  
[Operating Profit - EBIT](#operating-profit---ebit) / [Capital Employed](#capital-employed)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Return on equity - ROE
**Formula**  
[Net Profit](#net-profit) / [Shareholder's Equity](#shareholders-equity)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Return on net assets - RONA
**Formula**  
[Net Profit](#net-profit) / ( [Fixed Assets](#fixed-assets) + [Working Capital](#working-capital) )

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Shareholder equity ratio
**Formula**  
[Shareholder's Equity](#shareholders-equity) / [Assets](#assets)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

## Customer ledger measures

The Customer Ledger Entries model table combines detailed customer ledger entries with their customer ledger entries. Amounts come from detailed entries, so a payment document can contribute multiple rows.
- [Bucket 1 (Receivables)](#bucket-1-receivables)
- [Bucket 2 (Receivables)](#bucket-2-receivables)
- [Bucket 3 (Receivables)](#bucket-3-receivables)
- [Bucket 4 (Receivables)](#bucket-4-receivables)
- [Current (Receivables)](#current-receivables)
- [Amount Receivable (LCY)](#amount-receivable-lcy)
- [Balance (Accounts Receivable)](#balance-accounts-receivable)
- [Original Amount (LCY)](#original-amount-lcy)
- [Late Payment Amount](#late-payment-amount)
- [Late Payment %](#late-payment-percent)
- [Average Days Late](#average-days-late)
- [No. of Payments](#no-of-payments)
- [No. of Late Payments](#no-of-late-payments)

### Bucket 1 (receivables)
**Formula**   
The Bucket 1 (Receivables) measure calculates the [Amount Receivable (LCY)](#amount-receivable-lcy) within the first aging bucket using the selected due date, posting date, or document date basis. The bucket ends one day before the latest selected date and spans the number of days in **Aging Bucket Period**.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

### Bucket 2 (receivables)
**Formula**   
The Bucket 2 (Receivables) measure calculates the [Amount Receivable (LCY)](#amount-receivable-lcy) in the period immediately before Bucket 1. It uses **Aging Bucket Period**, the latest selected date, and the selected due date, posting date, or document date basis.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry
- Date

### Bucket 3 (receivables)
**Formula**   
The Bucket 3 (Receivables) measure calculates the [Amount Receivable (LCY)](#amount-receivable-lcy) in the period immediately before Bucket 2. It uses **Aging Bucket Period**, the latest selected date, and the selected due date, posting date, or document date basis.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry
- Date

### Bucket 4 (receivables)
**Formula**   
The Bucket 4 (Receivables) measure calculates the [Amount Receivable (LCY)](#amount-receivable-lcy) for dates earlier than Bucket 3. It includes all older dates, rather than one fixed-length period, using the selected due date, posting date, or document date basis.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry
- Date

### Current (receivables)
**Formula**
The Current (Receivables) measure calculates the [Amount Receivable (LCY)](#amount-receivable-lcy) where the selected due date, posting date, or document date is on or after the latest selected date.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry
- Date

### Amount receivable (LCY)
**Formula**   
The Amount Receivable (LCY) measure calculates the total amount of receivables in the local currency for a given period. The measure sums up the amount (in local currency) of the Customer Ledger Entries table to determine the total amount of receivables.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

### Balance (accounts receivable)
**Formula**   
The Balance (Accounts Receivable) measure calculates the total balance of accounts receivable up to a specific date. The measure uses the [Amount Receivable (LCY)](#amount-receivable-lcy) measure and applies a filter to only include transactions on or before the selected date.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry
- Date

### Original amount (LCY)
**Formula**   
The Original Amount (LCY) measure calculates the total amount of original entries for customers in the local currency. The measure sums up the amount (in local currency) of the Customer Ledger Entries table, but only includes entries with the entry type of "Initial Entry".

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

### Late payment amount
**Formula**   
The Late Payment Amount measure sums **Amount (LCY)** in the Customer Ledger Entries model table for payments where the detailed entry's posting date exceeds the customer ledger entry's due date, then multiplies the result by -1.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

### Late payment percent
**Formula**   
The Late Payment % measure calculates the [No. of Late Payments](#no-of-late-payments) divided by the total [No. of Payments](#no-of-payments).

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

### Average days late
**Formula**   
The Average Days Late measure calculates the average number of days between the Due Date and Posting Date, where **Document Type** is **Payment** and Posting Date exceeds Due Date.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

### No. of payments
**Formula**   
The No. of Payments measure calculates a distinct count of **Document No.** where **Document Type** is **Payment**. It removes filters on the **Late Payment** column.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

### No. of late payments
**Formula**   
The No. of Late Payments measure counts rows in the Customer Ledger Entries model table where **Document Type** is **Payment** and the detailed entry's posting date exceeds the customer ledger entry's due date. Unlike **No. of Payments**, it doesn't count distinct document numbers.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

## Vendor ledger measures

The Vendor Ledger Entries model table combines detailed vendor ledger entries with their vendor ledger entries. Amounts come from detailed entries.
- [Bucket 1 (Payables)](#bucket-1-payables)
- [Bucket 2 (Payables)](#bucket-2-payables)
- [Bucket 3 (Payables)](#bucket-3-payables)
- [Bucket 4 (Payables)](#bucket-4-payables)
- [Current (Payables)](#current-payables)
- [Amount Payable (LCY)](#amount-payable-lcy)
- [Balance (Accounts Payable)](#balance-accounts-payable)
- [Original Amount](#original-amount)

### Bucket 1 (payables)
**Formula**   
The Bucket 1 (Payables) measure calculates the [Amount Payable (LCY)](#amount-payable-lcy) within the first aging bucket using the selected due date, posting date, or document date basis. The bucket ends one day before the latest selected date and spans the number of days in **Aging Bucket Period**.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Bucket 2 (payables)
**Formula**   
The Bucket 2 (Payables) measure calculates the [Amount Payable (LCY)](#amount-payable-lcy) in the period immediately before Bucket 1. It uses **Aging Bucket Period**, the latest selected date, and the selected due date, posting date, or document date basis.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Bucket 3 (payables)
**Formula**   
The Bucket 3 (Payables) measure calculates the [Amount Payable (LCY)](#amount-payable-lcy) in the period immediately before Bucket 2. It uses **Aging Bucket Period**, the latest selected date, and the selected due date, posting date, or document date basis.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Bucket 4 (payables)
**Formula**   
The Bucket 4 (Payables) measure calculates the [Amount Payable (LCY)](#amount-payable-lcy) for dates earlier than Bucket 3. It includes all older dates, rather than one fixed-length period, using the selected due date, posting date, or document date basis.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Current (payables)
**Formula**
The Current (Payables) measure calculates the [Amount Payable (LCY)](#amount-payable-lcy) where the selected due date, posting date, or document date is on or after the latest selected date.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Amount payable (LCY)
**Formula**   
The Amount Payable (LCY) measure calculates the total amount of payables in the local currency for a given period. The measure sums up the values in the amount (in local currency) column of the Vendor Ledger Entry table to determine the total amount of payables.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Balance (accounts payable)
**Formula**   
The Balance (Accounts Payable) measure  calculates the total balance of accounts payable up to a specific date. The measure uses the [Amount Payable (LCY)](#amount-payable-lcy) measure and applies a filter to only include transactions on or before the selected date.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry

### Original amount
**Formula**   
The Original Amount measure calculates the total amount of original entries for vendors. The measure uses the [Amount Payable (LCY)](#amount-payable-lcy) measure and applies a filter to the Vendor Ledger Entries table to only include entries with the Entry Type equal to "Initial Entry".

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry

## G/L entry measures
- [Amount](#amount)
- [Balance](#balance)
- [Balance at Date](#balance-at-date)
- [Balance at Date (Neg)](#balance-at-date-neg)
- [Net Change](#net-change)
- [Net Change (Neg)](#net-change-neg)
- [Variance to Budget](#variance-to-budget)
- [Variance to Budget %](#variance-to-budget-)

### Amount
**Formula**   
The Amount measure sums all values in the amount column of the G/L Entry table.

**Data Sources**
- G/L Entry

### Balance
**Formula**   
The Balance measure calculates the total [Amount](#amount) across all dates, ignoring any filters on the `Date` table. By removing date-based filtering, this measure provides the full balance from the start to the end of the dataset, regardless of any date selections applied in the report.

**Data Sources**
- G/L Entry

### Balance at date
**Formula**   
The Balance at Date measure calculates the cumulative [Amount](#amount) up to the latest date in the current filter context. It removes all date filters, then re-applies a filter to include only dates up to and including the maximum date within the selection. This provides a running balance up to the specified date.

**Data Sources**
- G/L Entry

### Balance at date (neg)
**Formula**   
The Balance at Date (Neg) measure, abbreviated for Balance at Date (Negative), shows the [Balance at Date](#balance-at-date) measure as a negative value.

*Balance at Date (Neg) = [Balance at Date](#balance-at-date) x -1*

**Data Sources**
- G/L Entry

### Net change
**Formula**   
The Net Change measure is a filtered version of [Amount](#amount), focusing on non-closing entries to show only the net activity. Net Change filters out entries where **Closing Entry** is TRUE, excluding closing entries from its calculation.

**Data Sources**
- G/L Entry

### Net change (neg)
**Formula**   
The Net Change (Neg) measure, abbreviated for Net Change (Negative), shows the [Net Change](#net-change) measure as a negative value.

*Net Change (Neg) = [Net Change](#net-change) x -1*

**Data Sources**
- G/L Entry

### Variance to budget
**Formula**   
The Variance to Budget measure calculates the difference between the actual net change and the budget amount.

*Variance to Budget = [Net Change](#net-change) - [Budget Amount](#budget-amount)*

**Data Sources**
- G/L Entry
- G/L Budget Entry

### Variance to budget %
**Formula**   
*Variance to Budget % = [Variance to Budget](#variance-to-budget) / [Net Change](#net-change)*

**Data Sources**
- G/L Entry
- G/L Budget Entry

## G/L budget entry measures
- [Budget Amount](#budget-amount)
- [Budget Balance at Date](#budget-balance-at-date)

### Budget amount
**Formula**   
The Budget Amount measure sums up all the budgeted amounts from the G/L Budget Entry table.

**Data Sources**
- G/L Budget Entry

### Budget balance at date
**Formula**   
The Budget Balance at Date measure calculates the budgeted balance at a specific date.

**Data Sources**
- G/L Budget Entry

## Related information

[Track your business KPIs with Power BI goals](track-kpis-with-power-bi-metrics.md)  
[Power BI finance app](finance-powerbi-app.md)  
[Ad hoc analysis on finance data](ad-hoc-analysis-finance.md)  
[Built-in core finance reports](finance-reports.md)  
[Built-in fixed assets reports](fa-reports.md)  
[Built-in accounts receivable reports](receivables-reports.md)  
[Built-in accounts payable reports](payables-reports.md)  
[Financial analytics overview](bi.md)  
[Finance overview](finance.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
