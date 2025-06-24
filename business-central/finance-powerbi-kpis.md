---
title: Finance App KPIs and measures (Power BI)
description: Get an overview of all the KPIs and measures in the semantic model for the Finance Power BI app.
author: kennienp
ms.author: kepontop
ms.reviewer:
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 
ms.date: 10/31/2024
ms.service: dynamics-365-business-central
---

# Power BI Finance app KPIs and measures

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


### % Change in Operating Profit - EBIT
**Formula**  
( [Operating Profit - EBIT (Balance at Date)](#operating-profit---ebit-balance-at-date) - [Operating Profit - EBIT (Beginning Balance)](#operating-profit---ebit-beginning-balance) ) / [Operating Profit - EBIT (Beginning Balance)](#operating-profit---ebit-beginning-balance)

**Data Sources**
- G/L Entry
- G/L Account Category

### % Change in Revenue 
**Formula**  
( [Revenue (Balance at Date)](#revenue-balance-at-date) - [Revenue (Beginning Balance)](#revenue-beginning-balance) ) / [Revenue (Beginning Balance)](#revenue-beginning-balance)

**Data Sources**
- G/L Entry
- G/L Account Category

### Asset Turnover Ratio 
**Formula**  
[Revenue](#revenue) / [Assets](#assets)

**Data Sources**
- G/L Entry
- G/L Account Category

### Average Collection Period (Days) 
**Formula**  
( [No. of Days](#no-of-days) * [Accounts Receivable (Net Change)](#accounts-receivable-net-change) ) / [Revenue](#revenue)

**Data Sources**
- Date
- G/L Entry
- G/L Account Category

### Cash Conversion Cycle - CCC 
**Formula**  
[Days Sales Of Inventory - DSI](#days-sales-of-inventory---dsi) + [Days Sales Outstanding - DSO](#days-sales-outstanding---dso) - [Days Payable Outstanding - DPO](#days-payable-outstanding---dpo)

**Data Sources**
- G/L Entry
- G/L Account Category

### Days Payable Outstanding - DPO 
**Formula**  
 ( [Accounts Payable](#accounts-payable) / [Cost of Goods Sold](#cost-of-goods-sold) ) * [No. of Days](#no-of-days)

**Data Sources**
- Date
- G/L Entry
- G/L Account Category

 
### Days Sales Of Inventory - DSI 
**Formula**  
( [Inventory](#inventory) / [Cost of Goods Sold](#cost-of-goods-sold) ) * [No. of Days](#no-of-days)

**Data Sources**
- Date
- G/L Entry
- G/L Account Category

### Days Sales Outstanding - DSO 
**Formula**  
 ( [Accounts Receivable](#accounts-receivable) / [Revenue](#revenue) ) * [No. of Days](#no-of-days)

**Data Sources**
- Date
- G/L Entry
- G/L Account Category

### Degree Of Operating Leverage - DOL 
**Formula**  
[% Change in Operating Profit - EBIT](#-change-in-operating-profit---ebit) / [% Change in Revenue](#-change-in-revenue)

**Data Sources**
- G/L Entry
- G/L Account Category

### Inventory Turnover
**Formula**  
[Cost of Goods Sold](#cost-of-goods-sold) / [Inventory (Average)](#inventory-average)

**Data Sources**
- G/L Entry
- G/L Account Category

### No. of Days
**Formula**

The No. of Days measure calculates the total number of days within a selected period by counting the rows between the earliest (MIN) and latest (MAX) dates in the Date table. This measure provides a count of days for the specified date range in the context.

**Date Sources**
- Date

## Balance Sheet Measures

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

### Accounts Payable
**Formula**  
The Accounts Payable measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Accounts Payable* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Accounts Payable (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Accounts Payable (Neg)
**Formula**  
The Accounts Payable measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Accounts Payable* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Accounts Payable (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories
 
### Accounts Receivable
**Formula**  
The Accounts Receivable measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Accounts Receivable* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Accounts Receivable (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Accounts Receivable (Average) 
**Formula**  
( [Accounts Receivable (Beginning Balance)](#accounts-receivable-beginning-balance) + [Accounts Receivable](#accounts-receivable) ) / 2

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Accounts Receivable (Beginning Balance) 
**Formula**  
The Accounts Receivable (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [accounts receivable](#accounts-receivable) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Accounts Receivable (Net Change) 
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

### Current Assets
**Formula**  
The Current Assets measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Current Assets* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Current Assets (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Fixed Assets
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

### Inventory (Average)
**Formula**  
( [Inventory (Beginning Balance)](#inventory-beginning-balance) + [Inventory](#inventory) ) / 2

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Inventory (Beginning Balance) 
**Formula**  
The Inventory (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [Inventory](#inventory) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Liquid Assets
**Formula**  
The Liquid Assets measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Cash* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Liquid Assets (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Capital Employed
**Formula**  
[Assets](#assets) - [Current Liabilities](#current-liabilities)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
### Equity
**Formula**  
The Equity measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Equity* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Equity (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 

### Current Liabilities
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
 
### Liabilities (Neg)
**Formula**  
The Liabilities measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Liabilities* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Liabilities (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 

### Liabilities & Equity  
**Formula**  
[Liabilities](#liabilities) + [Equity](#equity)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 

### Longterm Liabilities  
**Formula**  
The Longterm Liabilities measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Longterm Liabilities* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Longterm Liabilities (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
### Payroll Liabilities   
**Formula**  
The Payroll Liabilities measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Payroll Liabilities* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Payroll Liabilities (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
### Purchase Prepayments   
**Formula**  
The Purchase Prepayments measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Purchase Prepayments* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Purchase Prepayments (Level 3 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
### Shareholders Equity   
**Formula**  
The Shareholders Equity measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Common Stock* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Shareholder's Equity (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
   
### Working Capital 
**Formula**  
[Current Assets](#current-assets) + [Current Liabilities](#current-liabilities)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories 
 
## Income Statement Measures
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

### Cost of Goods Sold
**Formula**  
The Cost of Goods Sold measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Cost of Goods Sold* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Cost of Goods Sold (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Depreciation and Amortization
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

### Expense (Balance at Date)  
**Formula**  
The Expense measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Expense (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Expense (Beginning Balance)  
**Formula**  
The Expense (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [Expense](#expense) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary Expense
**Formula**  
The Extraordinary Expense measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Extraordinary Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Extraordinary Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary Expense (Balance at Date)
**Formula**  
The Extraordinary Expense (Balance at Date) measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Extraordinary Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Extraordinary Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary Expense (Beginning Balance)  
**Formula**  
The Extraordinary Expense (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [Extraordinary Expense](#extraordinary-expense) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary Revenue
**Formula**  
The Extraordinary Revenue measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Extraordinary Revenue* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Extraordinary Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary Revenue (Balance at Date)
**Formula**  
The Extraordinary Revenue (Balance at Date) measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Extraordinary Revenue* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Extraordinary Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Extraordinary Revenue (Beginning Balance)  
**Formula**  
The Extraordinary Revenue (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [Extraordinary Revenue](#extraordinary-revenue) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period. It then multiplies the result by -1 to display the balance as a positive value.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories


### FX Gains Revenue
**Formula**  
The FX Gains Revenue measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *FX Gains Revenue* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **FX Gains Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### FX Gains Revenue (Balance at Date)
**Formula**  
The FX Gains Revenue measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *FX Gains Revenue* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **FX Gains Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### FX Gains Revenue (Beginning Balance)  
**Formula**  
The FX Gains Revenue (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [FX Gains Revenue](#fx-gains-revenue) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### FX Losses Expense
**Formula**  
The FX Losses Expense measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *FX Losses Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **FX Losses (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### FX Losses Expense (Balance at Date)
**Formula**  
The FX Losses Expense measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *FX Losses Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **FX Losses Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### FX Losses Expense (Beginning Balance)  
**Formula**  
The FX Losses Expense (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [FX Losses Expense](#fx-losses-expense) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest Expense
**Formula**  
The Interest Expense measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Interest Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Interest Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest Expense (Balance at Date)  
**Formula**  
The Interest Expense measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Interest Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Interest Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest Expense (Beginning Balance)  
**Formula**  
The Interest Expense (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [Interest Expense](#interest-expense) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest Revenue
**Formula**  
The Interest Revenue measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Income, Interest* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Interest Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest Revenue (Balance at Date)
**Formula**  
The Interest Revenue measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Income, Interest* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Interest Revenue (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Interest Revenue (Beginning Balance)  
**Formula**  
The Interest Revenue (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [Interest Revenue](#interest-revenue) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating Expense - OPEX
**Formula**  
[Expense](#expense) - [Interest Expense](#interest-expense) - [FX Losses Expense](#fx-losses-expense) - [Tax Expense](#tax-expense) - [Extraordinary Expense](#extraordinary-expense)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating Expense - OPEX (Balance at Date) 
**Formula**  
[Expense (Balance at Date)](#expense-balance-at-date) - [Interest Expense (Balance at Date)](#interest-expense-balance-at-date) - [FX Losses Expense (Balance at Date)](#fx-losses-expense-balance-at-date) - [Tax Expense (Balance at Date)](#tax-expense-balance-at-date) - [Extraordinary Expense (Balance at Date)](#extraordinary-expense-balance-at-date)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating Expense - OPEX (Beginning Balance)  
**Formula**  
[Expense (Beginning Balance)](#expense-beginning-balance) - [Interest Expense (Beginning Balance)](#interest-expense-beginning-balance) - [FX Losses Expense (Beginning Balance)](#fx-losses-expense-beginning-balance) - [Tax Expense (Beginning Balance)](#tax-expense-beginning-balance) - [Extraordinary Expense (Beginning Balance)](#extraordinary-expense-beginning-balance)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating Revenue
**Formula**  
[Revenue](#revenue) - [Interest Revenue](#interest-revenue) - [FX Gains Revenue](#fx-gains-revenue) - [Extraordinary Revenue](#extraordinary-revenue)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating Revenue (Balance at Date)  
**Formula**  
[Revenue (Balance at Date)](#revenue-balance-at-date) - [Interest Revenue (Balance at Date)](#interest-revenue-balance-at-date) - [FX Gains Revenue (Balance at Date)](#fx-gains-revenue-balance-at-date) - [Extraordinary Revenue (Balance at Date)](#extraordinary-revenue-balance-at-date)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating Revenue (Beginning Balance)  
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

### Revenue (Balance at Date)  
**Formula**  
The Revenue measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Income* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Revenue (Level 1 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Revenue (Beginning Balance)  
**Formula**  
The Revenue (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [Revenue](#revenue) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Tax Expense
**Formula**  
The Tax Expense measure calculates the [Net Change](#net-change) for general ledger accounts categorized as *Tax Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Tax Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Tax Expense (Balance at Date)  
**Formula**  
The Tax Expense measure calculates the [Balance at Date](#balance-at-date) for general ledger accounts categorized as *Tax Expense* on the [G/L Account Category](https://businesscentral.dynamics.com?page=790) page and where this category is mapped to the **Tax Expense (Level 2 Category)** on the [Power BI Account Categories](https://businesscentral.dynamics.com?page=36961) page. 

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Tax Expense (Beginning Balance)  
**Formula**  
The Tax Expense (Beginning Balance) measure calculates the [Balance at Date](#balance-at-date) for [Tax Expense](#tax-expense) up to the earliest date in the selected period. The measure calculates the beginning balance by identifying the earliest date in the selected period, removing any existing date filters to consider all historical dates, and then limiting results to transactions on or before this earliest date. This approach yields the balance as of the start of the selected period.

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

## Liquidity KPIs
- [Cash Ratio](#cash-ratio) 
- [Current Ratio](#current-ratio) 
- [Quick Ratio](#quick-ratio) 

### Cash Ratio
**Formula**  
[Liquid Assets](#liquid-assets) / [Current Liabilities](#current-liabilities)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Current Ratio
**Formula**  
[Current Assets](#current-assets) / [Current Liabilities](#current-liabilities)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Quick Ratio
**Formula**  
 ( [Current Assets](#current-assets) - [Inventory](#inventory) - [Purchase Prepayments](#purchase-prepayments) ) / [Current Liabilities](#current-liabilities)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Profitability KPIs
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

### Debt Ratio 
**Formula**  
[Liabilities](#liabilities) / [Assets](#assets)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Debt/Equity Ratio 
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

### Gross Profit
**Formula**  
[Revenue](#revenue) - [Cost of Goods Sold](#cost-of-goods-sold)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Gross Profit Margin
**Formula**  
[Gross Profit](#gross-profit) / [Revenue](#revenue)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Net Profit
**Formula**  
[Revenue](#revenue) - [Cost of Goods Sold](#cost-of-goods-sold) - [Expense](#expense)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Net Profit Margin
**Formula**  
[Net Profit](#net-profit) / [Revenue](#revenue)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating Profit - EBIT
**Formula**  
[Operating Revenue](#operating-revenue) - [Operating Expense - OPEX](#operating-expense---opex)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating Profit - EBIT (Balance at Date)
**Formula**  
[Operating Revenue (Balance at Date)](#operating-revenue-balance-at-date) - [Operating Expense - OPEX (Balance at Date)](#operating-expense---opex-balance-at-date)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating Profit - EBIT (Beginning Balance)
**Formula**  
[Operating Revenue (Beginning Balance)](#operating-revenue-balance-at-date) - [Operating Expense - OPEX (Beginning Balance)](#operating-expense---opex-balance-at-date)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Operating Profit Margin
**Formula**  
[Operating Profit - EBIT](#operating-profit---ebit) / [Operating Revenue](#operating-revenue)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Return On Assets - ROA
**Formula**  
[Net Profit](#net-profit) / [Assets](#assets)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Return On Capital Employed - ROCE 
**Formula**  
[Operating Profit - EBIT](#operating-profit---ebit) / [Capital Employed](#capital-employed)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Return On Equity - ROE 
**Formula**  
[Net Profit](#net-profit) / [Shareholder's Equity](#shareholders-equity)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Return On Net Assets - RONA
**Formula**  
[Net Profit](#net-profit) / ( [Fixed Assets](#fixed-assets) + [Working Capital](#working-capital) )

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

### Shareholder Equity Ratio
**Formula**  
[Shareholder's Equity](#shareholders-equity) / [Assets](#assets)

**Data Sources**
- G/L Entry
- G/L Account Category
- Account Categories

## Customer Ledger Measures
- [Bucket 1 (Receivables)](#bucket-1-receivables)
- [Bucket 2 (Receivables)](#bucket-2-receivables)
- [Bucket 3 (Receivables)](#bucket-3-receivables)
- [Bucket 4 (Receivables)](#bucket-4-receivables)
- [Current (Receivables)](#current-receivables)
- [Amount Receivable (LCY)](#amount-receivable-lcy)
- [Balance (Accounts Receivable)](#balance-accounts-receivable)
- [Original Amount (LCY)](#original-amount-lcy)

### Bucket 1 (Receivables)
**Formula**   
The Bucket 1 (Receivables) measure  calculates the [Amount Receivable (LCY)](#amount-receivable-lcy) due, posted, or documented within the first aging bucket. The measure uses the value of the `Aging Bucket Period` to determine the length of each aging bucket, and then calculates the starting date for each bucket based on the current date.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

### Bucket 2 (Receivables)
**Formula**   
The Bucket 2 (Receivables) measure  calculates the [Amount Receivable (LCY)](#amount-receivable-lcy) due, posted, or documented within the second aging bucket. The measure uses the value of the `Aging Bucket Period` to determine the length of each aging bucket, and then calculates the starting date for each bucket based on the current date.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry
- Date

### Bucket 3 (Receivables)
**Formula**   
The Bucket 3 (Receivables) measure  calculates the [Amount Receivable (LCY)](#amount-receivable-lcy) due, posted, or documented within the third aging bucket. The measure uses the value of the `Aging Bucket Period` to determine the length of each aging bucket, and then calculates the starting date for each bucket based on the current date.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry
- Date

### Bucket 4 (Receivables)
**Formula**   
The Bucket 4 (Receivables) measure  calculates the [Amount Receivable (LCY)](#amount-receivable-lcy) due, posted, or documented within the fourth aging bucket. The measure uses the value of the `Aging Bucket Period` to determine the length of each aging bucket, and then calculates the starting date for each bucket based on the current date.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry
- Date

### Current (Receivables)
**Formula**
Current (Receivables) measure calculates the [Amount Receivable (LCY)](#amount-receivable-lcy) for the given period where the data is on or before the last date in the period.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry
- Date

### Amount Receivable (LCY)
**Formula**   
The Amount Receivable (LCY) measure calculates the total amount of receivables in the local currency for a given period. The measure sums up the amount (in local currency) of the Customer Ledger Entries table to determine the total amount of receivables.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

### Balance (Accounts Receivable)
**Formula**   
The Balance (Accounts Receivable) measure calculates the total balance of accounts receivable up to a specific date. The measure uses the [Amount Receivable (LCY)](#amount-receivable-lcy) measure and applies a filter to only include transactions on or before the selected date.

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry
- Date

### Original Amount (LCY)
**Formula**   
The Original Amount (LCY) measure calculates the total amount of original entries for customers in the local currency. The measure sums up the amount (in local currency) of the Customer Ledger Entries table, but only includes entries with the entry type of "Initial Entry".

**Data Sources**
- Customer Ledger Entry
- Detailed Customer Ledger Entry

## Vendor Ledger Measures
- [Bucket 1 (Payables)](#bucket-1-payables)
- [Bucket 2 (Payables)](#bucket-2-payables)
- [Bucket 3 (Payables)](#bucket-3-payables)
- [Bucket 4 (Payables)](#bucket-4-payables)
- [Current (Payables)](#current-payables)
- [Amount Payable (LCY)](#amount-payable-lcy)
- [Balance (Accounts Payable)](#balance-accounts-payable)
- [Original Amount](#original-amount)

### Bucket 1 (Payables)
**Formula**   
The Bucket 1 (Payables) measure calculates the [Amount Payable (LCY)](#amount-payable-lcy) within the first aging bucket. The first uses the `Aging Bucket Period` to determine the length of the first aging bucket and calculates the starting date for the bucket based on the current date.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Bucket 2 (Payables)
**Formula**   
The Bucket 2 (Payables) measure calculates the [Amount Payable (LCY)](#amount-payable-lcy) within the second aging bucket. The second uses the `Aging Bucket Period` to determine the length of the second aging bucket and calculates the starting date for the bucket based on the current date.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Bucket 3 (Payables)
**Formula**   
The Bucket 3 (Payables) measure calculates the [Amount Payable (LCY)](#amount-payable-lcy) within the third aging bucket. The third uses the `Aging Bucket Period` to determine the length of the third aging bucket and calculates the starting date for the bucket based on the current date.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Bucket 4 (Payables)
**Formula**   
The Bucket 4 (Payables) measure calculates the [Amount Payable (LCY)](#amount-payable-lcy) within the fourth aging bucket. The fourth uses the `Aging Bucket Period` to determine the length of the fourth aging bucket and calculates the starting date for the bucket based on the current date.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

#### Current (Payables)
**Formula**
Current Payables measures calculates the [Amount Payable (LCY)](#amount-payable-lcy) where the Due Date is on or after the last date in period.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Amount Payable (LCY)
**Formula**   
The Amount Payable (LCY) measure calculates the total amount of payables in the local currency for a given period. The measure sums up the values in the amount (in local currency) column of the Vendor Ledger Entry table to determine the total amount of payables.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry
- Date

### Balance (Accounts Payable)
**Formula**   
The Balance (Accounts Payable) measure  calculates the total balance of accounts payable up to a specific date. The measure uses the [Amount Payable (LCY)](#amount-payable-lcy) measure and applies a filter to only include transactions on or before the selected date.

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry

### Original Amount
**Formula**   
The Original Amount measure calculates the total amount of original entries for vendors. The measure uses the [Amount Payable (LCY)](#amount-payable-lcy) measure and applies a filter to the Vendor Ledger Entries table to only include entries with the Entry Type equal to "Initial Entry".

**Data Sources**
- Vendor Ledger Entry
- Detailed Vendor Ledger Entry

## G/L Entry Measures
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

### Balance at Date
**Formula**   
The Balance at Date measure calculates the cumulative [Amount](#amount) up to the latest date in the current filter context. It removes all date filters, then re-applies a filter to include only dates up to and including the maximum date within the selection. This provides a running balance up to the specified date.

**Data Sources**
- G/L Entry

### Balance at Date (Neg)
**Formula**   
The Balance at Date (Neg) measure, abbreviated for Balance at Date (Negative), shows the [Balance at Date](#balance-at-date) measure as a negative value.

*Balance at Date (Neg) = [Balance at Date](#balance-at-date) x -1*

**Data Sources**
- G/L Entry

### Net Change
**Formula**   
The Net Change measure is a filtered version of [Amount](#amount), focusing on non-closing entries to show only the net activity. Net Change filters out entries where **Closing Entry** is TRUE, excluding closing entries from its calculation.

**Data Sources**
- G/L Entry

### Net Change (Neg)
**Formula**   
The Net Change (Neg) measure, abbreviated for Net Change (Negative), shows the [Net Change](#net-change) measure as a negative value.

*Net Change (Neg) = [Net Change](#net-change) x -1*

**Data Sources**
- G/L Entry

### Variance to Budget
**Formula**   
The Variance to Budget measure calculates the difference between the actual net change and the budget amount.

*Variance to Budget = [Net Change](#net-change) - [Budget Amount](#budget-amount)*

**Data Sources**
- G/L Entry
- G/L Budget Entry

### Variance to Budget %
**Formula**   
*Variance to Budget % = [Variance to Budget](#variance-to-budget) / [Net Change](#net-change)*

**Data Sources**
- G/L Entry
- G/L Budget Entry

## G/L Budget Entry Measures
- [Budget Amount](#budget-amount)
- [Budget Amount at Date](#budget-amount-at-date)

### Budget Amount
**Formula**   
The Budget Amount measure sums up all the budgeted amounts from the G/L Budget Entry table.

**Data Sources**
- G/L Budget Entry

### Budget Amount at Date
**Formula**   
The Budget Balance at Date measure calculates the budgeted balance at a specific date.

**Data Sources**
- G/L Budget Entry

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI finance app](finance-powerbi-app.md)  
[Ad hoc analysis on finance data](ad-hoc-analysis-finance.md)  
[Built-in core finance reports](finance-reports.md)  
[Built-in fixed assets reports](fa-reports.md)  
[Built-in accounts receivable reports](receivables-reports.md)  
[Built-in accounts payable reports](payables-reports.md)  
[Financial analytics overview](bi.md)  
[Finance overview](finance.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
