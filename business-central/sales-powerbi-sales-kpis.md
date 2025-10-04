---
title: Sales KPIs and measures (Power BI)
description: Get an overview of all the KPIs and measures in the semantic model for the Power BI Sales app.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 
ms.date: 05/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# KPIs and measures in the Power BI Sales app

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This article lists and describes the key performance indicators (KPIs) included in the semantic model for the Power BI Sales app. The descriptions include how the app calculates KPIs and the data it uses for its calculations.

Explore the KPIs to learn more about how they can help you achieve your business goals.

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Customer Table

**Customer Measures**

- [No. of Customers](#no-of-customers)
- [No. of Lost Customers](#no-of-lost-customers)
- [No. of New Customers](#no-of-new-customers)
- [No. of Recovered Customers](#no-of-recovered-customers)
- [No. of Returning Customers](#no-of-returning-customers)
- [No. of Temporarily Lost Customers](#no-of-temporarily-lost-customers)
- [Sales Lost Customers (12M)](#sales-lost-customers-12m)
- [Sales New Customers](#sales-new-customers)
- [Sales Recovered Customers](#sales-recovered-customers)
- [Sales Returning Customers](#sales-returning-customers)

### No. of Customers

**Formula**  

Distinct count of the **Customer No.** column from the **Sales** table.

**Data Sources**

- Value Entries
- Sales Invoice Line
- Sales Credit Line

### No. of Lost Customers

**Formula**  

This measure calculates the number of customers who were lost, meaning customers who stopped purchasing, within the current date selection. It determines the latest date in the selection, prepares a table of customers and the dates they were "lost," and then filters out the customers whose lost date is within the selected date range. Finally, it counts the rows in this filtered table to get the number of lost customers.

**Data Sources**

- Value Entries
- Sales Invoice Line
- Sales Credit Line

### No. of New Customers

**Formula**  

This measure counts new customers by finding the date of their first purchase. It includes customers if their first purchase happened within the date selection.

**Data Sources**

- Value Entries
- Sales Invoice Line
- Sales Credit Line

### No. of Recovered Customers

**Formula**  

This measure calculates the number of customers who were temporarily lost, that is, customers who stopped purchasing but later made a new purchase. It identifies customers who had a "lost" date before the selected date range, then determines which customers made a new purchase within the current period. The measure filters and counts only those customers whose new purchase occurred after their lost date, returning the total number of recovered customers.

**Data Sources**

- Value Entries
- Sales Invoice Line
- Sales Credit Line

### No. of Returning Customers

**Formula**  

This measure calculates the number of customers who made a repeat purchase during the current period. It identifies existing customers by filtering customers whose first purchase was before the selected date range, then determines which of these customers made another purchase within the current period. The measure returns the count of these returning customers.

**Data Sources**

- Value Entries
- Sales Invoice Line
- Sales Credit Line

### No. of Temporarily Lost Customers

**Formula**  

This measure calculates the number of customers who were temporarily lost, that is, customers who stopped purchasing. It identifies customers who were active in the previous period, then determines which customers have not made a purchase within the current period.The measure returns the total number of  these temporarily lost customers.

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Sales Credit Line

### Sales Lost Customers (12M)

**Formula**  

This measure calculates the total sales lost over the past 12 months due to customers who stopped purchasing ("lost" customers). It first identifies the most recent "lost" date, then filters customers who were lost before that date. It gets the sales from the previous 12 months for these lost customers and calculates the total revenue they generated before they stopped purchasing.

**Data Sources**

- Value Entries
- Sales Invoice Line
- Sales Credit Line

### Sales New Customers

**Formula**  

This measure calculates the total sales from customers who made their first purchase within the current date range. It identifies each customer's first purchase date, filters out customers whose first purchase occurred during the selected period, and then sums the sales amount from those new customers.

**Data Sources**

- Value Entries
- Sales Invoice Line
- Sales Credit Line

### Sales Recovered Customers

**Formula**  

This measure calculates the total sales generated by recovered customers. Recovered customers were previously lost but made a purchase afterward. It identifies temporarily lost customers, checks whether they made a new purchase in the current period, and then sums the sales figures for them.

**Data Sources**

- Value Entries
- Sales Invoice Line
- Sales Credit Line

### Sales Returning Customers

**Formula**  

This measure calculates the total sales generated by returning customers. Returning customers are customers who made their first purchase before the current period and made more purchases in the current period. It identifies returning customers by finding the intersection of active customers and customers who purchased previously, and then sums the sales from these returning customers.

**Data Sources**

- Value Entries
- Sales Invoice Line
- Sales Credit Line

## Opportunities Table

**Opportunities Measures**

- [Opportunity Sales Quote Amount](#opportunity-sales-quote-amount)

### Opportunity Sales Quote Amount

**Formula**  
This measure calculates the sales amount where the **Document Type** is **Quote** and the **Sales Opportunity No.** is related to an **Opportunity No.**

**Data Sources**

- Opportunity Entries
- Sales Line

## Opportunity Entries Table

**Counters**

- [No. of Lost Opportunities](#no-of-lost-opportunities)
- [No. of Opportunities](#no-of-opportunities)
- [No. of Won Opportunities](#no-of-won-opportunities)

**Opportunity Entry Measures**

- [Active Calculated Current Value](#active-calculated-current-value)
- [Active Chance of Success %](#active-chance-of-success-percent)
- [Active Estimated Value](#active-estimated-value)
- [Average Chance of Success %](#average-chance-of-success-percent)
- [Average Completed %](#average-completed-percent)
- [Average Probability %](#average-probability-percent)
- [Calculated Current Value](#calculated-current-value)
- [Estimated Value](#estimated-value)
- [Win/Loss %](#win-loss-percent)

### No. of Lost Opportunities

**Formula**  

Distinct count of **Opportunity No.** column from the Opportunity Entries table, where **Active** = **true** and the **Action Taken** = **Lost**.

**Data Sources**

- Opportunity Entries

### No. of Opportunities

**Formula**  
Distinct count of the **Opportunity No.** column from the **Opportunity Entries** table.

**Data Sources**

- Opportunity Entries

### No. of Won Opportunities

**Formula**  

Distinct count of the **Opportunity No.** column from the **Opportunity Entries** table where **Active** is selected and **Action Taken** is **Won**.

**Data Sources**

- Opportunity Entries

### Active Calculated Current Value

**Formula**  

Sum of the **Calculated Current Value** from the **Opportunity Entries** table, where **Active** is selected.

**Data Sources**

- Opportunity Entries

### Active Chance of Success Percent

**Formula**  

Average of the **Chance of Success** from the **Opportunity Entries table**, where **Active** is selected.

**Data Sources**

- Opportunity Entries

### Active Estimated Value

**Formula**  

Sum of the **Estimated Value** from the **Opportunity Entries** table, where **Active** os selected.

**Data Sources**

- Opportunity Entries

### Average Chance of Success Percent

**Formula**  

Average of the **Chance of Success** from the **Opportunity Entries** table.

**Data Sources**

- Opportunity Entries

### Average Completed Percent

**Formula**  

Average of the **Completed** value from the **Opportunity Entries** table.

**Data Sources**

- Opportunity Entries

### Average Probability Percent

**Formula**  

Average of the **Probability** value from the **Opportunity Entries** table.

**Data Sources**

- Opportunity Entries

### Calculated Current Value

**Formula**  

Sum of the **Calculated Current Value** from the **Opportunity Entries** table.

**Data Sources**

- Opportunity Entries

### Estimated Value

**Formula**  

Sum of the **Estimated Value** from the **Opportunity Entries** table.

**Data Sources**

- Opportunity Entries

### Win Loss Percent

**Formula**  

The **No. of Won Opportunities** divided by the sum of the  **No. of Won Opportunities** and the **No. of Lost Opportunities**.

**Data Sources**

- Opportunity Entries

## Documents Table

- **Sales Credits**
  - [Credit Adjusted Profit (LCY)](#credit-adjusted-profit-lcy)
  - [Total Credit (Amount)](#total-credit-amount)
  - [Total Credit (Qty.)](#total-credit-qty)
- **Sales Invoices**
  - [Total Sales (Amount)](#total-sales-amount)
  - [Total Sales (Qty.)](#total-sales-qty)
- [Adjusted Cost (LCY)](#adjusted-cost-lcy)
- [Adjusted Profit (LCY)](#adjusted-profit-lcy)
- [Adjusted Profit Margin](#adjusted-profit-margin)
- [Return Rate (Amount)](#return-rate-amount)
- [Return Rate (Qty.)](#return-rate-qty)
- [Sales (LCY)](#sales-lcy)
- [Sales (LCY) (Forecasting)](#sales-lcy-forecasting)
- [Sales Quantity](#sales-lcy)
- [Sales Quantity](#sales-quantity)

### Credit Adjusted Profit (LCY)

**Formula**  

*Credit Adjusted Profit (LCY) = [Total Credit (Amount)](#total-credit-amount) + ( [Posted Sales CR/Adj Note Cost Amount](#posted-sales-cradj-note-cost-amount) + [Posted Sales CR/Adj Note Cost Amount Non-Inv](#posted-sales-cradj-note-cost-amount-non-inv) + [Sales Credit Line Cost Amount](#sales-credit-line-cost-amount) )*

**Data Sources**  

- Value Entries
- Sales Credit Line
- Project Ledger Entry

### Total Credit (Amount)

**Formula**  

*Total Credit (Amount) = [Posted Sales CR/Adj Note Amount](#posted-sales-cradj-note-amount) + [Sales Credit Line Amount](#sales-credit-line-amount) + [Sales CR/Adj Total Price](#sales-cradj-total-price)*

**Data Sources**  

- Value Entries
- Sales Credit Line
- Project Ledger Entry

### Total Credit (Qty.)

**Formula**  

*Total Credit (Qty.) = [Posted Sales CR/Adj Note Quantity](#posted-sales-cradj-note-quantity) + [Sales Credit Line Quantity](#sales-credit-line-quantity) + [Sales CR/Adj Item Quantity](#sales-cradj-item-quantity)*

**Data Sources**  

- Value Entries
- Sales Credit Line
- Project Ledger Entry

### Total Sales (Amount)

**Formula**  

*Total Sales (Amount) = [Posted Sales Invoice Amount](#posted-sales-invoice-amount) + [Sales Invoice Line Amount](#sales-invoice-line-amount) + [Sales Invoice Total Price](#sales-invoice-total-price)*

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Project Ledger Entry

### Total Sales (Qty.)

**Formula**  

*Total Sales (Qty.) = [Posted Sales Invoice Quantity](#posted-sales-invoice-quantity) + [Sales Invoice Line Quantity](#sales-invoice-line-quantity) + [Sales Invoice Item Quantity](#sales-invoice-item-quantity)*

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Project Ledger Entry

### Adjusted Cost (LCY)

**Formula**  

*Adjusted Cost (LCY) = [Cost Amount Actual](#cost-amount-actual) + [Sales Invoice Line Cost Amount](#sales-invoice-line-cost-amount) + [Sales Credit Line Cost Amount](#sales-credit-line-cost-amount)*

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Adjusted Profit (LCY)

**Formula**  

*Adjusted Profit (LCY) = [Sales (LCY)](#sales-lcy) + ( [Adjusted Cost (LCY)](#adjusted-cost-lcy) + [Cost Amount Non-Inv](#cost-amount-non-inv) )*

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Adjusted Profit Margin

**Formula**  

*Adjusted Profit Margin = [Adjusted Profit (LCY)](#adjusted-profit-lcy) / [Sales (LCY)](#sales-lcy)*

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Return Rate (Amount)

**Formula**  

*Return Rate (Amount) = - [Total Credit (Amount)](#total-credit-amount) / [Total Sales (Amount)](#total-sales-amount)*

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Return Rate (Qty.)

**Formula**  

*Return Rate (Qty.) = - [Total Credit (Qty.)](#total-credit-qty) / [Total Sales (Qty.)](#total-sales-qty)*

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Sales (LCY)

**Formula**  

The Sales (LCY) measure calculates the total amount for all invoiced Sales, by calculating the sum of [Sales Amount Actual](#sales-amount-actual), [Total Price](#total-price), [Sales Invoice Line Amount](#sales-invoice-line-amount) and [Sales Credit Line Amount](#sales-credit-line-amount).

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Sales (LCY) (Forecasting)

**Formula**  

The Sales (LCY) (Forecasting) measure calculates the [Sales (LCY)](#sales-lcy) within the period of dates with sales transactions and inserts zero values for dates without sale entries, for compatibility with forecasting.

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Sales Quantity

**Formula**  

The Sales Quantity measure calculates the total quantity for all invoiced Sales, by calculating the sum of [Invoiced Quantity](#invoiced-quantity), [Project Ledger Item Quantity](#project-ledger-item-quantity), [Sales Invoice Line Quantity](#sales-invoice-line-quantity) and [Sales Credit Line Quantity](#sales-credit-line-quantity).

**Data Sources**  

- Value Entries
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Gross Profit

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The **Sales Amount** minus the **Cost Amount** minus the **Cost Amount Non-Inv.**

**Data Sources**

- Value Entries
- Sales Line

### Gross Profit Margin

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The **Gross Profit** divided by the **Sales Amount**.

**Data Sources**

- Value Entries
- Sales Line

### Return Rate

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

This measure calculates the sales amount where the **Document Type** is **Sales Credit Memo**, divided by the sales amount where the **Document Type** is **Sales Invoice**.

**Data Sources**

- Value Entries
- Sales Line

### Sales Amount

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The sum of the **Sales Amt. (LCY)** column from the **Sales** table.

**Data Sources**

- Value Entries
- Sales Line

## Pareto Measures

- [Pareto Color Cutoff](#pareto-color-cutoff)
- [Pareto Customer Cutoff Rank](#pareto-customer-cutoff-rank)
- [Pareto Cutoff Customer](#pareto-cutoff-customer)
- [Pareto Cutoff Customer Rank](#pareto-cutoff-customer-rank)
- [Pareto Cumulative Adjusted Profit (LCY)](#pareto-cumulative-adjusted-profit-lcy)
- [Pareto Cumulative Adjusted Profit %](#pareto-cumulative-adjusted-profit-)
- [Pareto Customer Rank by Adjusted Profit (LCY)](#pareto-customer-rank-by-adjusted-profit-lcy)
- [Pareto Cutoff Cumulative Adjusted Profit (LCY)](#pareto-cutoff-cumulative-adjusted-profit-lcy)
- [Pareto Cutoff Adjusted Profit %](#pareto-cutoff-adjusted-profit-)
- [Pareto Total Adjusted Profit (LCY)](#pareto-total-adjusted-profit-lcy)

### Pareto Color Cutoff

**Formula**  

The color cutoff where [Pareto Customer Rank by Adjusted Profit (LCY)](#pareto-customer-rank-by-adjusted-profit-lcy) exceeds the [Pareto Customer Cutoff Rank](#pareto-customer-cutoff-rank).

**Data Source**  
- Value Entry
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Pareto Customer Cutoff Rank

**Formula**  

The maximum [Pareto Cutoff Customer Rank](#pareto-cutoff-customer-rank) for all customers.

**Data Source**  
- Value Entry
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Pareto Cutoff Customer

**Formula**  

The Customer with the maximum difference of the [Pareto Cumulative Adjusted Profit %](#pareto-cumulative-adjusted-profit-) minus the **Pareto Value**.

**Data Source**  
- Value Entry
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Pareto Cutoff Customer Rank

**Formula**  

The [Pareto Customer Rank by Adjusted Profit (LCY)](#pareto-customer-rank-by-adjusted-profit-lcy) for the [Pareto Cutoff Customer](#pareto-cutoff-customer).

**Data Source**  
- Value Entry
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Pareto Cumulative Adjusted Profit (LCY)

**Formula**  

The [Adjusted Profit (LCY)](#adjusted-profit-lcy) based on the [Pareto Customer Rank by Adjusted Profit (LCY)](#pareto-customer-rank-by-adjusted-profit-lcy).

**Data Source**  
- Value Entry
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Pareto Cumulative Adjusted Profit %

**Formula**  

The [Pareto Cumulative Adjusted Profit (LCY)](#pareto-cumulative-adjusted-profit-lcy) divided by the [Pareto Total Adjusted Profit (LCY)](#pareto-total-adjusted-profit-lcy).

**Data Source**  
- Value Entry
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Pareto Customer Rank by Adjusted Profit (LCY)

**Formula**  

The Pareto Customer Rank by Adjusted Profit (LCY) measure calculates the customer rank, ordered by the [Adjusted Profit (LCY)](#adjusted-profit-lcy) for all sales from the **Sales Value Entries**, **Sales Credit Lines**, **Sales Invoice Lines** and **Project Ledger Entries** tables.

**Data Source**  
- Value Entry
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Pareto Cutoff Cumulative Adjusted Profit (LCY)

**Formula**  

The [Pareto Cumulative Adjusted Profit (LCY)](#pareto-cumulative-adjusted-profit-lcy)  for the [Pareto Cutoff Customer](#pareto-cutoff-customer).

**Data Source**  
- Value Entry
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Pareto Cutoff Adjusted Profit %

**Formula**  

The [Pareto Cumulative Adjusted Profit %](#pareto-cumulative-adjusted-profit-) for the [Pareto Cutoff Customer](#pareto-cutoff-customer).

**Data Source**  
- Value Entry
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Pareto Total Adjusted Profit (LCY)

**Formula**  

The total [Adjusted Profit (LCY)](#adjusted-profit-lcy) for all sales from the **Sales Value Entries**, **Sales Credit Lines**, **Sales Invoice Lines** and **Project Ledger Entries** tables.

**Data Source**  
- Value Entry
- Sales Invoice Line
- Sales Credit Line
- Project Ledger Entry

### Pareto Cumulative Gross Profit

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The **Cumulative Gross Profit** based on the **Pareto Customer Rank by Gross Profit**.

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Data Source**

- Sales Line

### Pareto Cumulative Gross Profit Percent

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The **Cumulative Gross Profit** divided by the **Total Gross Profit**.

**Data Source**

- Sales Line

### Pareto Customer Rank by Gross Profit

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The **Pareto Customer Rank** ordered by the **Gross Profit** on the **Sales** table.

**Data Source**

- Sales Line

### Pareto Cutoff Cumulative Gross Profit

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The **Cumulative Gross Profit** for the **Pareto Cutoff Customer**.

**Data Source**

- Sales Line

### Pareto Cutoff Gross Profit Percent

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The **Pareto Cumulative Gross Profit** for the **Pareto Cutoff Customer**.

**Data Source**

- Sales Line

### Pareto Total Gross Profit

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The **Total Gross Profit** from the **Sales** table for all sales.

**Data Source**

- Sales Line

## Project Ledger Entries Table

- **Sales CR/Adj**
  - [Sales CR/Adj Item Quantity](#sales-cradj-item-quantity)
  - [Sales CR/Adj Total Price](#sales-cradj-total-price)
- **Sales Invoices**
  - [Sales Invoice Item Quantity](#sales-invoice-item-quantity)
  - [Sales Invoice Total Price](#sales-invoice-total-price)
- [Project Ledger Gross Profit Margin](#project-ledger-gross-profit-margin)
- [Project Ledger Item Gross Profit](#project-ledger-item-gross-profit)
- [Project Ledger Item Quantity](#project-ledger-item-quantity)
- [Total Cost](#total-cost)
- [Total Price](#total-price)

### Sales CR/Adj Item Quantity

**Formula**  

The Sales CR/Adj Item Quantity measure calculates the [Project Ledger Item Quantity](#project-ledger-item-quantity) from the **Project Ledger Entries** table, where **Document Type** = **Posted Sales CR/Adj Note**.

**Data Source**  

- Project Ledger Entry

### Sales CR/Adj Total Price

**Formula**  

The Sales CR/Adj Total Price measure calculates the [Total Price](#total-price) from the **Project Ledger Entries** table, where **Document Type** = **Posted Sales CR/Adj Note**.

**Data Source**  

- Project Ledger Entry

### Sales Invoice Item Quantity

**Formula**  

The Sales CR/Adj Item Quantity measure calculates the [Project Ledger Item Quantity](#project-ledger-item-quantity) from the **Project Ledger Entries** table, where **Document Type** = **Posted Sales Invoice**.

**Data Source**  

- Project Ledger Entry

### Sales Invoice Total Price

**Formula**  

The Sales Invoice Total Price measure calculates the [Total Price](#total-price) from the **Project Ledger Entries** table, where **Document Type** = **Posted Sales Invoice**.

**Data Source**  

- Project Ledger Entry

### Project Ledger Gross Profit Margin

**Formula**  

*Project Ledger Gross Profit Margin = [Project Ledger Item Gross Profit](#project-ledger-item-gross-profit) / [Total Price](#total-price)*

**Data Source**  

- Project Ledger Entry

### Project Ledger Item Gross Profit

**Formula**  

*Project Ledger Item Gross Profit = [Total Price](#total-price) + [Total Cost](#total-cost)*

**Data Source**  

- Project Ledger Entry

### Project Ledger Item Quantity

**Formula**  

The Project Ledger Item Quantity measure calculates the total negative sum of the **Quantity (Base)** column from the **Project Ledger Entries** table.

**Data Source**  

- Project Ledger Entry

### Total Cost

**Formula**  

The Total Cost measure calculates the total sum of the **Total Cost (LCY)** column from the **Project Ledger Entries** table.

**Data Source**  

- Project Ledger Entry

### Total Price

**Formula**  

The Total Price measure calculates the total negative sum of the **Total Price (LCY)** column from the **Project Ledger Entries** table.

**Data Source**  

- Project Ledger Entry

## Sales Credit Line Table

- [Sales Credit Line Amount](#sales-credit-line-amount)
- [Sales Credit Line Cost Amount](#sales-credit-line-cost-amount)
- [Sales Credit Line Gross Profit](#sales-credit-line-gross-profit)
- [Sales Credit Line Gross Profit Margin](#sales-credit-line-gross-profit-margin)
- [Sales Credit Line Quantity](#sales-credit-line-quantity)

### Sales Credit Line Amount

**Formula**  

The Sales Credit Line Amount measure calculates the total negative sum of the **Amount** column from the Sales Credit Line table.

**Data Source**  

- Sales Credit Line

### Sales Credit Line Cost Amount

**Formula**  

The Sales Credit Line Cost Amount measure calculates the total sum of the **Unit Cost LCY** multiplied by the **Quantity Base** from the Sales Credit Line table.

**Data Source**  

- Sales Credit Line

### Sales Credit Line Gross Profit

**Formula**  

*Sales Credit Line Gross Profit = - [Sales Credit Line Amount](#sales-credit-line-amount) + [Sales Credit Line Cost Amount](#sales-credit-line-cost-amount)*

**Data Source**  

- Sales Credit Line

### Sales Credit Line Gross Profit Margin

**Formula**  

*Sales Credit Line Gross Profit Margin = - [Sales Credit Line Gross Profit](#sales-credit-line-gross-profit) / [Sales Credit Line Amount](#sales-credit-line-amount)*

**Data Source**  

- Sales Credit Line

### Sales Credit Line Quantity

**Formula**  

The Sales Credit Line Quantity measure calculates the total negative sum of the **Quantity (Base)** column from the Sales Credit Line table.

**Data Source**  

- Sales Credit Line

## Sales Invoice Line Table

- [Sales Invoice Line Amount](#sales-invoice-line-amount)
- [Sales Invoice Line Cost Amount](#sales-invoice-line-cost-amount)
- [Sales Invoice Line Gross Profit](#sales-invoice-line-gross-profit)
- [Sales Invoice Line Gross Profit Margin](#sales-invoice-line-gross-profit-margin)
- [Sales Invoice Line Quantity](#sales-invoice-line-quantity)

### Sales Invoice Line Amount

**Formula**  

The Sales Invoice Line Amount measure calculates the total sum of the **Amount** column from the Sales Invoice Line table.

**Data Source**  

- Sales Invoice Line

### Sales Invoice Line Cost Amount

**Formula**  

The Sales Invoice Line Cost Amount measure calculates the total sum of the **Unit Cost LCY** multiplied by the **Quantity Base** from the Sales Invoice Line table, where **Type** = **Resource**.

**Data Source**  

- Sales Invoice Line

### Sales Invoice Line Gross Profit

**Formula**  

*Sales Invoice Line Gross Profit = [Sales Invoice Line Amount](#sales-invoice-line-amount) + [Sales Invoice Line Cost Amount](#sales-invoice-line-cost-amount)*

**Data Source**  

- Sales Invoice Line

### Sales Invoice Line Gross Profit Margin

**Formula**  

*Sales Invoice Line Gross Profit Margin = [Sales Invoice Line Gross Profit](#sales-invoice-line-gross-profit) / [Sales Invoice Line Amount](#sales-invoice-line-amount)*

**Data Source**  

- Sales Invoice Line

### Sales Invoice Line Quantity

**Formula**  

The Sales Invoice Line Quantity measure calculates the total sum of the **Quantity (Base)** column from the Sales Invoice Line table.

**Data Source**  

- Sales Invoice Line

## Sales Line Table

- **Counters**
  - [No. of Outstanding Cr/Adj Notes](#no-of-outstanding-cradj-notes)
  - [No. of Outstanding Invoices](#no-of-outstanding-invoices)
  - [No. of Outstanding Return Orders](#no-of-outstanding-return-orders)
  - [No. of Outstanding Sales Orders](#no-of-outstanding-sales-orders)
  - [No. of Sales Quotes](#no-of-sales-quotes)
  - [No. of Shipped Not Invoiced Sales Orders](#no-of-shipped-not-invoiced-sales-orders)
- **Outstanding**
  - [Outstanding Invoices (LCY)](#outstanding-invoices-lcy)
  - [Outstanding Orders (LCY)](#outstanding-orders-lcy)
  - [Outstanding Quantity](#outstanding-quantity)
- **Quote**
  - [Sales Quote Adjusted Cost (LCY)](#sales-quote-adjusted-cost-lcy)
  - [Sales Quote Adjusted Profit (LCY)](#sales-quote-adjusted-profit-lcy)
  - [Sales Quote Adjusted Profit Margin](#sales-quote-adjusted-profit-margin)
  - [Sales Quote Quantity](#sales-quote-quantity)
  - [Sales Quote Sales (LCY)](#sales-quote-sales-lcy)
- **Received Not Invoiced**
  - [Received Not Invd. Amount](#received-not-invd-amount)
  - [Received Not Invd. Amount Excl. Tax](#received-not-invd-amount-excl-tax)
- **Return Order**
  - [Outstanding Return Order (LCY)](#outstanding-return-order-lcy)
  - [Return Amount](#return-amount)
  - [Return Qty. Invoiced](#return-qty-invoiced)
  - [Return Qty. Shipped](#return-qty-shipped)
  - [Return Qty. to Ship](#return-qty-to-ship)
  - [Return Quantity](#return-quantity)
- **Shipped Not Invoiced**
  - [Shipped Not Invoiced (LCY)](#shipped-not-invoiced-lcy)
  - [Shipped Not Invoiced Quantity](#shipped-not-invoiced-quantity)
- [Sales Line Cost Amount](#sales-line-cost-amount)
- [Sales Line Gross Profit](#sales-line-gross-profit)

### No. of Outstanding Cr/Adj Notes

**Formula**  

The No. of Outstanding Cr/Adj Notes measure calculates the number of unique Sales Cr/Adj Notes that are currently outstanding, by counting the distinct values of the **Document No.** column from the **Sales Lines** table where the **Document Type** is **Cr/Adj Note** and **Outstanding Quantity (Base)** is not zero.

**Data Sources**  

- Sales Line

### No. of Outstanding Invoices

**Formula**  

The No. of Outstanding Invoices measure calculates the number of unique Sales Invoices that are currently outstanding, by counting the distinct values of the **Document No.** column from the **Sales Lines** table where the **Document Type** is **Invoice** and **Outstanding Amount (LCY)** is not zero.

**Data Sources**  

- Sales Line

### No. of Outstanding Return Orders

**Formula**  

The No. of Outstanding Return Orders Notes measure calculates the number of unique Sales Return Orders that are currently outstanding, by counting the distinct values of the **Document No.** column from the **Sales Lines** table where the **Document Type** is **Return Order** and **Outstanding Quantity (Base)** is not zero.

**Data Sources**  

- Sales Line

### No. of Outstanding Sales Orders

**Formula**  

The No. of Outstanding Sales Orders measure calculates the number of unique Sales Orders that are currently outstanding, by counting the distinct values of the **Document No.** column from the **Sales Lines** table where the **Document Type** is **Order** and **Outstanding Quantity (Base)** is not zero.

**Data Sources**  

- Sales Line

### No. of Sales Quotes

**Formula**  

The No. of Sales Quotes measure calculates the number of unique Sales Quotes, by counting the distinct values of the **Document No.** column from the **Sales Lines** table where the **Document Type** is **Quote**.

**Data Sources**  

- Sales Line

### No. of Shipped Not Invoiced Sales Orders

**Formula**  

The No. of Shipped Not Invoiced Sales Orders measure calculates the number of unique Sales Orders that are currently shipped, by counting the distinct values of the **Document No.** column from the **Sales Lines** table where the **Document Type** is **Order** and **Shipped not Invoiced** is not zero.

**Data Sources**  

- Sales Line

### Outstanding Invoices (LCY)

**Formula**  

The Outstanding Invoices (LCY) measure calculates the total sum of the **Outstanding Amount (LCY)** column from the **Sales Lines** table where the **Document Type** is **Invoice**.

**Data Source**  

- Sales Line

### Outstanding Orders (LCY)

**Formula**  

The Outstanding Orders (LCY) measure calculates the total sum of the **Outstanding Amount (LCY)** column from the **Sales Lines** table where the **Document Type** is **Order**.

**Data Source**  

- Sales Line

### Outstanding Quantity

**Formula**  

The Outstanding Quantity measure calculates the total sum of the **Outstanding Quantity (Base)** column from the **Sales Lines** table where the **Document Type** is **Order**.

**Data Source**  

- Sales Line

### Sales Quote Adjusted Cost (LCY)

**Formula**  

The Sales Quote Adjusted Cost (LCY) measure calculates the sum of **Outstanding Quantity** multiplied by the **Unit Cost (LCY)** from the **Sales Lines** table, where the **Document Type** is **Quote** and **Type** is not **G/L Account** or **Resource**.

**Data Source**  

- Sales Line

### Sales Quote Adjusted Profit (LCY)

**Formula**  

*Sales Quote Adjusted Profit (LCY) = [Sales Quote Sales (LCY)](#sales-quote-sales-lcy) - [Sales Quote Adjusted Cost (LCY)](#sales-quote-adjusted-cost-lcy)*

**Data Source**  

- Sales Line

### Sales Quote Adjusted Profit Margin

**Formula**  

*Sales Quote Adjusted Profit Margin = [Sales Quote Adjusted Profit (LCY)](#sales-quote-adjusted-profit-lcy) / [Sales Quote Sales (LCY)](#sales-quote-sales-lcy)*

**Data Source**  

- Sales Line

### Sales Quote Quantity

**Formula**  

The Sales Quote Quantity measure calculates the sum of **Outstanding Quantity (Base)** from the **Sales Lines** table, where the **Document Type** is **Quote**.

**Data Source**  

- Sales Line

### Sales Quote Sales (LCY)

**Formula**  

The Sales Quote Sales (LCY) measure calculates the sum of **Outstanding Amount (LCY)** from the **Sales Lines** table, where the **Document Type** is **Quote**.

**Data Source**  

- Sales Line

### Received Not Invd. Amount

**Formula**  

The Received Not Invd. Amount measure calculates the sum of **Return Rcd. Not Invd. (LCY)** from the **Sales Lines** table.

**Data Source**  

- Sales Line

### Received Not Invd. Amount Excl. Tax

**Formula**  

The Received Not Invd. Amount Excl. Tax measure calculates the sum of the **Amount** multiplied by **Return Qty. Rcd. Not Invd.**, divided by the **Quantity (Base )** from the **Sales Line** table.

**Data Source**  

- Sales Line

### Outstanding Return Order (LCY)

**Formula**  

The Outstanding Return Order (LCY) measure calculates the sum of **Outstanding Amount (LCY)** column from the **Sales Lines** table, where the **Document Type** is **Return Order** or **Cr/Adj Note**.

**Data Source**  

- Sales Line

### Return Amount

**Formula**  

The Return Amount measure calculates the sum of **Amount** column from the **Sales Lines** table, where the **Document Type** is **Return Order** or **Cr/Adj Note**.

**Data Source**  

- Sales Line

### Return Qty. Invoiced

**Formula**  

The Return Qty. Invoiced measure calculates the sum of **Quantity Invoiced** column from the **Sales Lines** table, where the **Document Type** is **Return Order** or **Cr/Adj Note**.

**Data Source**  

- Sales Line

### Return Qty. Shipped

**Formula**  

*Return Qty. Shipped = [Return Quantity](#return-quantity) - [Return Qty. to Ship](#return-qty-to-ship)*

**Data Source**  

- Sales Line

### Return Qty. to Ship

**Formula**  

The Return Qty. to Ship measure calculates the sum of the **Outstanding Quantity (Base)** column from the **Sales Lines** table, where the **Document Type** is **Return Order** or **Cr/Adj Note**.

**Data Source**  

- Sales Line

### Return Quantity

**Formula**  

The Return Quantity measure calculates the sum of the **Quantity (Base)** column from the **Sales Lines** table, where the **Document Type** is **Return Order** or **Cr/Adj Note**.

**Data Source**  

- Sales Line

### Shipped Not Invoiced (LCY)

**Formula**  

The Shipped Not Invoiced (LCY) measure calculates the total sum of the **Shipped Not Invoiced** column from the **Sales Lines** table, where the **Document Type** is **Order**.

**Data Source**  

- Sales Line

### Shipped Not Invoiced Quantity

**Formula**  

The Shipped Not Invoiced Quantity measure calculates the total sum of the **Quantity Shipped Not Invoiced (Base)** column from the **Sales Lines** table.

**Data Source**  

- Sales Line

### Sales Line Cost Amount

**Formula**  

The Sales Line Cost Amount measure calculates the total sum of the **Outstanding Quantity** multiplied by the **Unit Cost LCY** from the **Sales Lines** table, where **Document Type** is not **CR/Adj Note**, **Return Order**, **Posted CR/Adj Note**, or **Posted Return Receipt**, and **Type** is not **Resource** or **G/L Account**.

**Data Source**  

- Sales Line

### Sales Line Gross Profit

**Formula**  

*Sales Line Gross Profit = [Outstanding Orders (LCY)](#outstanding-orders-lcy) - [Sales Line Cost Amount](#sales-line-cost-amount)*

**Data Source**  

- Sales Line

### No. of Return Orders

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

Distinct count of the **Document No.** column from the **Sales** table, where the **Document Type** is **Return Order**.

**Data Sources**

- Value Entries
- Sales Line

### Outstanding Amount

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The sum of the **Sales Amount** column from the **Sales** table where the **Source Type** is **Sales Order Outstanding**.

**Data Source**

- Sales Line

### Shipped Not Invoiced Amount

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The sum of the **Sales Amount** column from the **Sales** table where the **Source Type** is **Sales Order Shipped Not Invoiced**.

**Data Source**

- Sales Line

## Sales Value Entries Table

- **Counters**
  - [No. of Distinct Items](#no-of-distinct-items)
  - [No. of Posted Sales Invoices](#no-of-posted-sales-invoices)
- **Cr/Adj Notes**
  - [Posted Sales CR/Adj Note Amount](#posted-sales-cradj-note-amount)
  - [Posted Sales CR/Adj Note Cost Amount](#posted-sales-cradj-note-cost-amount)
  - [Posted Sales CR/Adj Note Cost Amount Non-Inv](#posted-sales-cradj-note-cost-amount-non-inv)
  - [Posted Sales CR/Adj Note Quantity](#posted-sales-cradj-note-quantity)
- **Sales Invoices**
  - [Posted Sales Invoice Amount](#posted-sales-invoice-amount)
  - [Posted Sales Invoice Quantity](#posted-sales-invoice-quantity)
- [Cost Amount Actual](#cost-amount-actual)
- [Cost Amount Non-Inv](#cost-amount-non-inv)
- [Cost Posted to G/L](#cost-posted-to-gl)
- [Invoiced Quantity](#invoiced-quantity)
- [Sales Amount Actual](#sales-amount-actual)

### No. of Distinct Items

**Formula**  

The No. of Distinct Items measure calculates a distinct count of the **Item No.** column from the **Sales Value Entries** table.

**Data Sources**  

- Value Entries

### No. of Posted Sales Invoices

**Formula**  

The No. of Posted Sales Invoices measure calculates a distinct count of the **Document No.** column from the **Sales Value Entries** table, where **Document Type** = **Sales Invoice**.

**Data Sources**  

- Value Entries

### Posted Sales CR/Adj Note Amount

**Formula**  

The Posted Sales CR/Adj Note Amount measure calculates the [Sales Amount Actual](#sales-amount-actual), where **Document Type** = **Posted Sales CR/Adj Note**.

**Data Sources**  

- Value Entries

### Posted Sales CR/Adj Note Cost Amount

**Formula**  

The Posted Sales CR/Adj Note Cost Amount measure calculates the [Cost Amount Actual](#cost-amount-actual), where **Document Type** = **Posted Sales CR/Adj Note**.

**Data Sources**  

- Value Entries

### Posted Sales CR/Adj Note Cost Amount Non-Inv

**Formula**  

The Posted Sales CR/Adj Note Cost Amount Non-Inv measure calculates the [Cost Amount Non-Inv](#cost-amount-non-inv), where **Document Type** = **Posted Sales CR/Adj Note**.

**Data Sources**  

- Value Entries

### Posted Sales CR/Adj Note Quantity

**Formula**  

The Posted Sales CR/Adj Note Quantity measure calculates the total sum of the **Invoiced Quantity** column from the **Sales Value Entries** table, where **Document Type** = **Posted Sales CR/Adj Note**.

**Data Sources**  

- Value Entries

### Posted Sales Invoice Amount

**Formula**  

The Posted Sales Invoice Amount measure calculates the [Sales Amount Actual](#sales-amount-actual), where **Document Type** = **Posted Sales Invoice**.

**Data Sources**  

- Value Entries

### Posted Sales Invoice Quantity

**Formula**  

The Posted Sales Invoice Quantity measure calculates the [Invoiced Quantity](#invoiced-quantity), where **Document Type** = **Posted Sales Invoice**.

**Data Sources**  

- Value Entries

### Cost Amount Actual

**Formula**  

The Cost Amount Actual measure calculates the total sum of the **Cost Amount Actual** column from the **Sales Value Entries** table.

**Data Sources**  

- Value Entries

### Cost Amount Non-Inv

**Formula**  

The Cost Amount Non-Inv measure calculates the total sum of the **Cost Amount (Non-Invtbl.)** column from the **Sales Value Entries** table.

**Data Sources**  

- Value Entries

### Cost Posted to G/L

**Formula**  

The Cost Posted to G/L measure calculates the total sum of the **Cost Posted to G/L** column from the **Sales Value Entries** table.

**Data Sources**  

- Value Entries

### Invoiced Quantity

**Formula**  

The Invoiced Quantity measure calculates the total sum of the **Invoiced Quantity** column from the **Sales Value Entries** table.

**Data Source**  

- Value Entries

### Sales Amount Actual

**Formula**  

The Sales Amount Actual measure calculates the total sum of the **Sales Amount Actual** column from the **Sales Value Entries** table.

**Data Sources**  

- Value Entries

### Invoiced Amount

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The sum of the **Sales Amount** column from the **Sales** table where the **Source Type** is **Value Entries Invoiced**.

**Data Source**

- Value Entries

### Cost Amount

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  

The sum of the **Cost Amt. (LCY)** column from the **Sales** table.

**Data Sources**

- Value Entries
- Sales Line

## Sales Budget Table

**Budget Measures**

- [Budget Amount](#budget-amount)
- [Budget Amount Variance](#budget-amount-variance)
- [Budget Amount Variance %](#budget-amount-variance-percent)
- [Budget Quantity](#budget-quantity)
- [Budget Quantity Variance](#budget-quantity-variance)
- [Budget Quantity Variance %](#budget-quantity-variance-percent)

### Budget Amount

**Formula**  

The sum of the **Sales Amount** column from the **Sales Budget** table.

**Data Source**

- Item Budget Entries

### Budget Amount Variance

**Formula**  

The **Sales Amount** minus the **Budget Amount**.

**Data Sources**

- Item Budget Entries
- Sales Lines
- Value Entries

### Budget Amount Variance Percent

**Formula**  

The **Budget Amount Variance** minus the **Budget Amount**.

**Data Sources**

- Item Budget Entries
- Sales Lines
- Value Entries

### Budget Quantity

**Formula**  

The sum of the **Quantity** column from the **Sales Budget** table.

**Data Source**

- Item Budget Entries

### Budget Quantity Variance

**Formula**  

The **Sales Quantity** minus the **Budget Quantity**.

**Data Sources**

- Item Budget Entries
- Sales Lines
- Value Entries

### Budget Quantity Variance Percent

**Formula**  

The **Budget Quantity Variance** minus the **Budget Quantity**.

**Data Sources**

- Item Budget Entries
- Sales Lines
- Value Entries

## Sales Amount Month-to-Date

- [Gross Profit MTD (Fiscal)](#gross-profit-mtd-fiscal)
- [Sales Amount MTD (Fiscal)](#sales-amount-mtd-fiscal)

### Gross Profit MTD (Fiscal)

**Formula**  

This measure calculates month-to-date gross profit using the fiscal calendar, considering only the sales up to the last available fiscal day of the current month and year.

**Data Sources**

- Value Entries
- Sales Line
- Date (Fiscal Calendar)

### Sales Amount MTD (Fiscal)

**Formula**  

This measure calculates the month-to-date sales amount using the fiscal calendar. It considers sales up to the last available fiscal day of the current month and year.

**Data Sources**

- Value Entries
- Sales Line
- Date (Fiscal Calendar)

## Sales Amount Moving Annual Totals

- [Sales Amount MAT (Fiscal)](#sales-amount-mat-fiscal)
- [Sales Amount PYMAT (Fiscal)](#sales-amount-pymat-fiscal)
- [Sales Amount MATG (Fiscal)](#sales-amount-matg-fiscal)
- [Sales Amount MATG % (Fiscal)](#sales-amount-matg--fiscal)

### Sales Amount MAT (Fiscal)

**Formula**  

This measure calculates the sales for the last 12 months (moving annual total). It uses the fiscal calendar and sums the sales between the calculated first and last days of the 365-day period.

**Data Sources**

- Value Entries
- Sales Line
- Date (Fiscal Calendar)

### Sales Amount PYMAT (Fiscal)

**Formula**  

This measure calculates the total sales for the prior 12 months based on the fiscal calendar. It then determines the maximum available date and calculates the range from the previous 24 months to the last available day to 12 months before. It uses these dates to sum the sales amount for this period while maintaining filters for the day type and weekday.

**Data Sources**

- Value Entries
- Sales Line
- Date (Fiscal Calendar)

### Sales Amount MATG (Fiscal)

**Formula**  

This measure calculates the year-over-year growth in sales by comparing the current period's moving annual total sales to the previous period's moving annual total sales. If both values aren't blank, it subtracts the previous period's sales from the current period's sales to determine the growth. The result is the change in sales between the two periods.

**Data Sources**

- Value Entries
- Sales Line
- Date (Fiscal Calendar)

### Sales Amount MATG % (Fiscal)

**Formula**  

This measure calculates the percentage growth in sales by dividing the year-over-year growth in sales (Sales Amount MATG (Fiscal)) by the previous period's moving annual total sales (Sales Amount PYMAT (Fiscal)).

**Data Sources**

- Value Entries
- Sales Line
- Date (Fiscal Calendar)

## Sales Amount Moving Averages

- [Sales Amount AVG 30D (Fiscal)](#sales-amount-avg-30d-fiscal)

### Sales Amount AVG 30D (Fiscal)

**Formula**  

This measure calculates the average sales over the last 30 days based on the fiscal calendar. The measure determines the maximum day in the dataset and defines the 30-day period ending on that day. It gets the days within this range while maintaining filters for day type and weekday. It also identifies the first day with sales data to ensure valid calculations. If the first day with data is within the 30-day period, it calculates the average sales amount over those days and returns the result.

**Data Sources**

- Value Entries
- Sales Line
- Date (Fiscal Calendar)

## Sales Amount Period-over-Period Growth

- [Sales Amount PP (Fiscal)](#sales-amount-pp-fiscal)
- [Sales Amount POP (Fiscal)](#sales-amount-pop-fiscal)
- [Sales Amount POP % (Fiscal)](#sales-amount-pop--fiscal)

### Sales Amount PP (Fiscal)

**Formula**  

This measure determines the appropriate sales amount based on the current context of the date hierarchy in the fiscal calendar. It uses the SWITCH function to evaluate whether the context is at the fiscal month, fiscal quarter, or fiscal year level. Depending on which level is active, it returns the corresponding sales amount, which is either:

- Previous month (Sales Amount PM (Fiscal))
- Previous quarter (Sales Amount PQ (Fiscal))
- Previous year (Sales Amount PY (Fiscal))

**Data Sources**

- Value Entries
- Sales Line
- Date (Fiscal Calendar)

### Sales Amount POP (Fiscal)

**Formula**  

This measure calculates the change in sales between the current period and the previous period based on the context of the fiscal calendar. It uses the SWITCH function to determine the appropriate previous period calculation depending on whether the current context is at the fiscal month, quarter, or year level. When at the fiscal month level, it references the month-over-month change from the Sales Amount MOM (Fiscal) measure, which computes the difference between the current month's sales and the previous month's sales. Similarly, for fiscal quarters and years, it uses quarter-over-quarter and year-over-year calculations, respectively.

**Data Sources**

- Value Entries
- Sales Line
- Date (Fiscal Calendar)

### Sales Amount POP % (Fiscal)

**Formula**  

This measure calculates the percentage growth in sales between the current and previous period based on the context of the fiscal calendar. It uses the SWITCH function to determine the appropriate previous period calculation depending on whether the current context is at the fiscal month, quarter, or year level. When at the fiscal month level, it references the month-over-month change from the Sales Amount MOM % (Fiscal) measure, which determines the percentage growth between the current month's sales and the previous month's sales. Similarly, for fiscal quarters and years, it uses quarter-over-quarter and year-over-year calculations, respectively.

**Data Sources**

- Value Entries
- Sales Line
- Date (Fiscal Calendar)

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad hoc analysis of sales data](ad-hoc-analysis-sales.md)  
[Built-in sales reports](sales-reports.md)  
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
