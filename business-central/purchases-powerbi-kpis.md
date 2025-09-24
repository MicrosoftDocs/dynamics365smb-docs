---
title: Purchases KPIs and measures (Power BI)
description: Get an overview of all the KPIs and measures in the semantic model for the Purchases Power BI app.
author: kennienp
ms.author: kepontop
ms.reviewer:
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 
ms.date: 11/06/2024
ms.service: dynamics-365-business-central
---

# Power BI Purchases app KPIs and measures

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This page provides a list of all Key Performance Indicators (KPIs) included in the semantic model for the Power BI Purchases report. 

Explore the list of KPIs below to learn more about how they can help you achieve your business goals. 

Each KPI is described, including how it is calculated and what data was used in the calculations.

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]


## Budget Measures
- [Budget Amount](#budget-amount)
- [Budget Amount Variance](#budget-amount-variance)
- [Budget Amount Variance %](#budget-amount-variance-)
- [Budget Quantity](#budget-quantity)
- [Budget Quantity Variance](#budget-quantity-variance)
- [Budget Quantity Variance %](#budget-quantity-variance-)

### Budget Amount

**Formula**  
The Budget Amount measure calculates the sum of Purchase Amount column from the Purchase Budget table.

**Data Sources**
- Item Budget Entries

### Budget Amount Variance

**Formula**
*Budget Amount Variance = [Purchase Amount](#purchase-amount) - [Budget Amount](#budget-amount)*

**Data Sources**
- Item Budget Entry
- Purchase Line
- Value Entry

### Budget Amount Variance %

**Formula**  
*Budget Amount Variance % = [Budget Amount Variance](#budget-amount-variance) / [Budget Amount](#budget-amount)*

**Data Sources**
- Item Budget Entry
- Purchase Line
- Value Entry

### Budget Quantity

**Formula**  
The Budget Quantity measure sums the Quantity column from the Purchase Budget table.

**Data Sources**
- Item Budget Entry


### Budget Quantity Variance

**Formula**  
*Budget Quantity Variance = [Purchase Quantity](#purchase-quantity) - [Budget Quantity](#budget-quantity)*

**Data Sources**
- Item Budget Entry
- Purchase Line
- Value Entry

### Budget Quantity Variance %

**Formula**  
*Budget Quantity Variance % = [Budget Quantity Variance](#budget-quantity-variance) / [Budget Quantity](#budget-quantity)*

**Data Sources**
- Item Budget Entry
- Purchase Line
- Value Entry

## Documents

- [Invoiced Prepayment Amount (LCY)](#invoiced-prepayment-amount-lcy)
- [Purchase (LCY)](#purchase-lcy)
- [Purchase (LCY) Forecasting](#purchase-lcy-forecasting)
- [Purchase Quantity](#purchase-quantity)
- [Return Rate (Amount)](#return-rate-amount)
- [Return Rate (Qty.)](#return-rate-qty)
- [Total Credit (Amount)](#total-credit-amount)
- [Total Credit (Qty.)](#total-credit-qty)
- [Total Purchase (Amount)](#total-purchase-amount)
- [Total Purchase (Qty)](#total-purchase-qty)

### Purchase Amount

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**
The Purchase Amount measure sums the the Purchase Amount column of the Purchases table.

**Data Sources**
- Value Entry

### Purchase Quantity

**Formula**
The Purchase Quantity measure sums the the Purchase Quantity column of the Purchases table.

**Data Sources**
- Value Entry

### Purchase (LCY)

**Formula**  
The Purchase (LCY) measure calculates the purchase amount across all invoiced purchase transactions by calculating the sum of [Purchase Value Entries Amount](#purchase-value-entries-amount), [Purchase Credit Line Amount](#purchase-credit-line-amount) and [Purchase Invoice Line Amount](#purchase-invoice-line-amount). Reconcile this measure to the Vendor Statistics page.

**Data Sources**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Purchase (LCY) Forecasting

**Formula**  
The Purchase (LCY) Forecasting measure calculates the [Purchase (LCY)](#purchase-lcy) within the period of dates with purchase transactions and inserts zero values for dates without purchase entries, for compatibility with forecasting.

**Data Sources**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Return Rate (Amount)

**Formula**  
*Return Rate (Amount) = - [Total Credit (Amount)](#total-credit-amount) / [Total Purchase (Amount)](#total-purchase-amount)*

**Data Sources**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Return Rate (Qty.)

**Formula**  
*Return Rate (Qty.) = - [Total Credit (Qty.)](#total-credit-qty) / [Total Purchase (Qty.)](#total-purchase-qty)*

**Data Sources**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Total Credit (Amount)

**Formula**  
*Total Credit (Amount) = [Posted Purchase CR/Adj Note Amount](#posted-purchase-cradj-note-amount) + [Purchase Credit Line Amount](#purchase-credit-line-amount)*

**Data Sources**  
- Value Entry
- Purchase Credit Memo Line

### Total Credit (Qty.)

**Formula**  
*Total Credit (Qty.)= [Posted Purchase CR/Adj Note Quantity](#posted-purchase-cradj-note-quantity) + [Purchase Credit Line Quantity Base](#purchase-credit-line-quantity-base)*

**Data Sources**  
- Value Entry
- Purchase Credit Memo Line

### Total Purchase (Amount)

**Formula**  
*Total Purchase (Amount) = [Posted Purchase Invoice Amount](#posted-purchase-invoice-amount) + [Purchase Invoice Line Amount](#purchase-invoice-line-amount)*

**Data Sources**  
- Value Entry
- Purchase Invoice Line

### Total Purchase (Qty.)

**Formula**  
*Total Purchase (Qty.)= [Posted Purchase Invoice Quantity](#posted-purchase-invoice-quantity) + [Purchase Invoice Quantity Base](#purchase-invoice-line-quantity-base)*

**Data Sources**  
- Value Entry
- Purchase Invoice Line

### Invoiced Prepayment Amount (LCY)

**Formula**  
The Invoiced Prepayment Amount (LCY) measure calculates the sum of the Prepayment Amount Invoiced (LCY) from the Purchase Lines table.

**Data Sources**  
- Purchase Line

## Purchase Value Entries

- **Counters**
  - [No. of Distinct Items](#no-of-distinct-items)
  - [No. of Posted Purchase Invoices](#no-of-posted-purchase-invoices)
  - [No. of Single Supplier Items](#no-of-single-supplier-items)
  - [No. of Vendors](#no-of-vendors)

- **Purchase Invoice**
  - [Posted Purchase Invoice Amount](#posted-purchase-invoice-amount)
  - [Posted Purchase Invoice Quantity](#posted-purchase-invoice-quantity)

- **Purchase CR/Adj Note**
  - [Posted Purchase CR/Adj Note Amount](#posted-purchase-cradj-note-amount)
  - [Posted Purchase CR/Adj Note Quantity](#posted-purchase-cradj-note-quantity)

- [Purchase Value Entries Amount](#purchase-value-entries-amount)
- [Purchase Value Entries Discount %](#purchase-value-entries-discount-)
- [Purchase Value Entries Discount Amount](#purchase-value-entries-discount-amount)
- [Purchase Value Entries Quantity](#purchase-value-entries-quantity)

### No. of Distinct Items

**Formula**  
The No. of Distinct Items calculates the number of unique items that have been purchased by counting the distinct values of the Item No. column of the Purchase Value Entry table.

**Data Sources**  
- Value Entry 

### No. of Posted Purchase Invoices

**Formula**  
The No. of Purchase Invoices measure calculates the number of unique posted purchase invoices by counting the distinct count of the Document No. column from the Purchases Value Entries table where Document Type = Posted Purchase Invoice.

**Data Sources**  
- Value Entry

### No. of Purchase Invoices

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The No. of Purchase Invoices measure calculates the number of unique posted purchase invoices by counting the distinct count of the Document No. column from the Purchases table where Document Type = Purchase Invoice and Source Type = Value Entries Invoiced.

**Data Sources**  
- Purchase Line
- Value Entry

### No. of Vendors

**Formula**  
The No. of Vendors calculates the number of unique items that have been purchased by counting the distinct values of the Vendor No. column of the Purchase Value Entry table.

**Data Sources**  
- Value Entry 

### No. of Single Supplier Items

**Formula**  
The No. of Single Supplier Items calculates the number of items that have been purchased from a single vendor, by filtering to items where [No. of Vendors](#no-of-vendors) equals one.

**Data Sources**  
- Value Entry 

### Posted Purchase Invoice Amount

**Formula**  
The Posted Purchase Invoice Amount calculates the total cost amount that has been purchased and invoiced, by summing the Purchase Value Entries Amount column of the Purchase Value Entries table, where Document Type = Posted Purchase Invoice.

**Data Sources**  
- Value Entry

### Posted Purchase Invoice Quantity

**Formula**  
The Posted Purchase Invoice Quantity calculates the total quantity that has been purchased and invoiced, by summing the Purchase Value Entries Quantity column of the Purchase Value Entries table, where Document Type = Posted Purchase Invoice.

**Data Sources**  
- Value Entry

### Invoiced Amount

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**
The Invoiced Amount calculates the total amount of items that have been purchased and invoiced, by summing the Purchase Amount column of the Purchases table, where Source Type = Purchase Value Entries Invoiced.

**Data Sources**  
- Value Entry

### Invoiced Quantity

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**
The Invoiced Quantity measure calculates the total quantity of items that have been purchased and invoiced, by summing the Purchase Quantity column of the Purchases table, where Source Type = Purchase Value Entries Invoiced.

**Data Sources**  
- Value Entry

### Posted Purchase CR/Adj Note Amount

**Formula**
The Posted Purchase CR/Adj Note Amount calculates the total cost amount that has been credited and invoiced, by summing the Purchase Value Entries Amount column of the Purchase Value Entries table, where Document Type = Posted Purchase CR/Adj Note.

**Data Sources**  
- Value Entry

### Posted Purchase CR/Adj Note Quantity

**Formula**  
The Posted Purchase CR/Adj Note Quantity calculates the total quantity that has been credited and invoiced, by summing the Purchase Value Entries Quantity column of the Purchase Value Entries table, where Document Type = Posted Purchase CR/Adj Note.

**Data Sources**  
- Value Entry

### Purchase Value Entries Amount

**Formula**  
The Purchase Value Entries Amount calculates the total amount that has been purchased, by summing the Cost Amount Actual column of the Purchase Value Entries table, where Value Entry Type = Direct Cost and Adjustment is false.

**Data Sources**  
- Value Entry

### Purchase Value Entries Quantity

**Formula**  
The Purchase Value Entries Quantity calculates the total quantity that has been purchased and invoiced, by summing the Invoiced Quantity column of the Purchase Value Entries table.

**Data Sources**  
- Value Entry

### Purchase Value Entries Discount Amount

**Formula**  
The Purchase Value Entries Quantity calculates the total quantity that has been purchased and invoiced, by summing the Invoiced Quantity column of the Purchase Value Entries table.

**Data Sources**  
- Value Entry

### Purchase Value Entries Discount %

**Formula**  
*Purchase Value Entries Discount % = [Purchase Value Entries Discount Amount](#purchase-value-entries-discount-amount) / [Purchase Value Entries Amount](#purchase-value-entries-amount)*

**Data Sources**  
- Value Entry

## Purchase Lines

- **Counters**
  - [No. of Outstanding Invoices](#no-of-outstanding-invoices)
  - [No. of Outstanding Purchase Orders](#no-of-outstanding-purchase-orders)
  - [No. of Outstanding Return Orders](#no-of-outstanding-return-orders)
  - [No. of Purchase Quotes](#no-of-purchase-quotes)
  - [No. of Received Not Invd. Purchase Orders](#no-of-received-not-invd-purchase-orders)

- **Outstanding**
  - [Outstanding Invoices (LCY)](#outstanding-invoices-lcy)
  - [Outstanding Orders (LCY)](#outstanding-orders-lcy)

- **Quote**
  - [Purchase Quote Purchase (LCY)](#purchase-quote-purchase-lcy)
  - [Purchase Quote Quantity](#purchase-quote-quantity)

- **Received Not Invoiced**
  - [Amt. Rcd. Not Invoiced (LCY)](#amt-rcd-not-invoiced-lcy)

- **Return Order**
  - [Outstanding Return Order (LCY)](#outstanding-return-order-lcy)
  - [Return Order Amount](#return-order-amount)
  - [Return Order Quantity](#return-order-quantity)
  - [Return Qty. Invoiced](#return-qty-invoiced)
  - [Return Qty. Shipped](#return-qty-shipped)
  - [Return Qty. to Invoice](#return-qty-to-invoice)
  - [Return Qty. to Ship](#return-qty-to-ship)
  - [Returned Quantity](#returned-quantity)

### No. of Outstanding Invoices

**Formula**  
The No. of Outstanding Invoices calculates the number of unique purchase invoices that are currently outstanding, by counting the distinct values of the Document No. column of the Purchase Lines table, where Document Type = Invoice.

**Data Sources**  
- Purchase Line

### No. of Outstanding Purchase Orders

**Formula**  
The No. of Outstanding Purchase Orders calculates the number of unique purchase orders that are currently outstanding, by counting the distinct values of the Document No. column of the Purchase Lines table, where Document Type = Order.

**Data Sources**  
- Purchase Line

### No. of Outstanding Return Orders

**Formula**  
The No. of Outstanding Return Orders calculates the number of unique purchase return orders that are currently outstanding, by counting the distinct values of the Document No. column of the Purchase Lines table, where Document Type = Return Order.

**Data Sources**  
- Purchase Line

### No. of Purchase Quotes

**Formula**  
The No. of Purchase Quotes calculates the number of unique purchase quotes, by counting the distinct values of the Document No. column of the Purchase Lines table, where Document Type = Quote.

**Data Sources**  
- Purchase Line

### No. of Received Not Invd. Purchase Orders
**Formula**
The No. of Received Not Invd. Purchase Orders measure calculates the number of unique purchase orders that are received but not invoiced, by counting the distinct count of Document No. column from the Purchases table where Document Type = Order.

**Data Sources**  
- Purchase Line

### Outstanding Invoices (LCY)

**Formula**  
The Outstanding Invoices (LCY) measure calculates the sum of the Outstanding Amount (LCY) column from the Purchase Line table where Document Type = Invoice.

**Data Sources**  
- Purchase Line

### Outstanding Orders (LCY)

**Formula**  
The Outstanding Orders (LCY) measure calculates the sum of the Outstanding Amount (LCY) column from the Purchase Line table where Document Type = Order.

**Data Sources**  
- Purchase Line

### Outstanding Amount (Excl. VAT)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Outstanding Amount (Excl. VAT) measure calculates the sum of Purchase Amount column from the Purchases table where Source Type = Purchase Order Outstanding, excluding VAT.

**Data Sources**
- Purchase Line

### Outstanding Quantity

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Outstanding Quantity measure calculates the sum of Purchase Qty. (Base) column from the Purchases table where Source Type = Purchase Order Outstanding.

**Data Sources**
- Purchase Line

### Purchase Quote Purchase (LCY)

**Formula**  
The Purchase Quote Purchase (LCY) measure calculates the sum of the Outstanding Amount (LCY) column from the Purchase Line table where Document Type = Quote.

**Data Sources**  
- Purchase Line

### Purchase Quote Quantity

**Formula**  
The Purchase Quote Quantity measure calculates the sum of the Outstanding Quantity (Base) column from the Purchase Line table where Document Type = Quote.

**Data Sources**  
- Purchase Line

### Amt. Rcd. Not Invoiced (LCY)

**Formula**  
The Amt. Rcd. Not Invoiced (LCY) measure calculates the sum of the Amount Received Not Invoiced (LCY) column from the Purchase Line table where Document Type = Order.

**Data Sources**
- Purchase Line

### Amt. Rcd. Not Invd. (Excl. VAT)

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Amt. Rcd. Not Invd. (Excl. VAT) measure calculates the sum of Purchase Amount column from the Purchases table where Source Type = Purchase Order Received Not Invoiced, excluding VAT.

**Data Sources**
- Purchase Line

### Quantity Rcd. Not Invd.

[!INCLUDE[powerbi_deprecated_measure](includes/deprecated-measures.md)]

**Formula**  
The Quantity Rcd. Not Invd. measure calculates the sum of Purchase Qty. (Base) column from the Purchases table. where Source Type = Purchase Order Received Not Invoiced.

**Data Sources**
- Purchase Line

### Outstanding Return Order (LCY)

**Formula**  
The Outstanding Return Order (LCY) measure calculates the sum of the Outstanding Amount (LCY) column from the Purchase Line table where Document Type = Return Order or Cr/Adj Note.

**Data Sources**  
- Purchase Line

### Return Order Amount

**Formula**  
The Return Order Amount measure calculates the sum of the Amount column from the Purchase Line table where Document Type = Return Order or Cr/Adj Note.

**Data Sources**  
- Purchase Line

### Return Order Quantity

**Formula**  
The Return Order Quantity measure calculates the sum of the Quantity (Base) column from the Purchase Line table where Document Type = Return Order or Cr/Adj Note.

**Data Sources**  
- Purchase Line

### Return Qty. Invoiced

**Formula**  
The Return Qty. Invoiced measure calculates the sum of the Quantity Invoiced column from the Purchase Line table where Document Type = Return Order or Cr/Adj Note.

**Data Sources**  
- Purchase Line

### Return Qty. Shipped

**Formula**  
*Return Qty. Shipped = [Return Order Quantity](#return-order-quantity) - [Return Qty. to Ship](#return-qty-to-ship)*

**Data Sources**  
- Purchase Line

### Return Qty. to Invoice

**Formula**  
*Return Qty. to Invoice = [Return Order Quantity](#return-order-quantity) - [Return Qty. Invoiced](#return-qty-invoiced)*

**Data Sources**  
- Purchase Line

### Return Qty. to Ship

**Formula**  
The Return Qty. to Ship measure calculates the sum of the Outstanding Quantity (Base) column from the Purchase Line table where Document Type = Return Order or Cr/Adj Note.

**Data Sources**  
- Purchase Line

### Returned Quantity

**Formula**  
*Returned Quantity = [Posted Purchase CR/Adj Note Quantity](#posted-purchase-cradj-note-quantity) + [Return Qty. to Invoice](#return-qty-to-invoice)*

**Data Sources**  
- Purchase Line
- Value Entry

## Purchase Credit Lines

- [Purchase Credit Line Amount](#purchase-credit-line-amount)
- [Purchase Credit Line Quantity Base](#purchase-credit-line-quantity-base)

### Purchase Credit Line Amount

**Formula**  
The Purchase Credit Line Amount measure calculates the negative sum of the Amount column from the Purchase Credit Line table.

**Data Sources**  
- Purchase Credit Memo Line

### Purchase Credit Line Quantity Base

**Formula**  
The Purchase Credit Line Quantity Base measure calculates the sum of the Quantity Base column from the Purchase Credit Line table.

**Data Sources**  
- Purchase Credit Memo Line

## Purchase Invoice Lines

- [Purchase Invoice Line Amount](#purchase-invoice-line-amount)
- [Purchase Invoice Line Quantity Base](#purchase-invoice-line-quantity-base)

### Purchase Invoice Line Amount

**Formula**  
The Purchase Invoice Line Amount measure calculates the sum of the Amount column from the Purchase Invoice Line table.

**Data Sources**  
- Purchase Invoice Line

### Purchase Invoice Line Quantity Base

**Formula**  
The Purchase Invoice Line Quantity Base measure calculates the sum of the Quantity Base column from the Purchase Invoice Line table.

**Data Sources**  
- Purchase Invoice Line

## Pareto Measures

- [Pareto Color Cutoff](#pareto-color-cutoff)
- [Pareto Cumulative Purchase (LCY)](#pareto-cumulative-purchase-lcy)
- [Pareto Cumulative Purchase (LCY) %](#pareto-cumulative-purchase-lcy-)
- [Pareto Cutoff Cumulative Purchase (LCY)](#pareto-cutoff-cumulative-purchase-lcy)
- [Pareto Cutoff Purchase (LCY) %](#pareto-cutoff-purchase-lcy-)
- [Pareto Cutoff Vendor](#pareto-cutoff-vendor)
- [Pareto Cutoff Vendor Rank](#pareto-cutoff-vendor-rank)
- [Pareto Vendor Cutoff Rank](#pareto-vendor-cutoff-rank)
- [Pareto Vendor Rank by Purchase (LCY)](#pareto-vendor-rank-by-purchase-lcy)
- [Pareto Total Purchase (LCY)](#pareto-total-purchase-lcy)

### Pareto Color Cutoff

**Formula**  
The color cutoff where [Pareto Vendor Rank by Purchase (LCY)](#pareto-vendor-rank-by-purchase-lcy) exceeds the [Pareto Vendor Cutoff Rank](#pareto-vendor-cutoff-rank).

**Data Sources**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Pareto Cumulative Purchase (LCY)

**Formula**  

The [Purchase (LCY)](#purchase-lcy) based on the [Pareto Vendor Rank by Purchase (LCY)](#pareto-vendor-rank-by-purchase-lcy).

**Data Source**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Pareto Cumulative Purchase (LCY) %

**Formula**  

The [Pareto Cumulative Purchase (LCY)](#pareto-cumulative-purchase-lcy) divided by the [Pareto Total Purchase (LCY)](#pareto-total-purchase-lcy).

**Data Source**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Pareto Cutoff Cumulative Purchase (LCY)

**Formula**  

The [Pareto Cumulative Purchase (LCY)](#pareto-cumulative-purchase-lcy) for the [Pareto Cutoff Vendor](#pareto-cutoff-vendor).

**Data Source**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Pareto Cutoff Purchase (LCY) %

**Formula**  

The [Pareto Cumulative Purchase (LCY) %](#pareto-cumulative-purchase-lcy-) for the [Pareto Cutoff Vendor](#pareto-cutoff-vendor).

**Data Source**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Pareto Cutoff Vendor

**Formula**  

The Vendor with the maximum difference of the [Pareto Cumulative Purchase (LCY) %](#pareto-cumulative-purchase-lcy-) minus the **Pareto Value**.

**Data Source**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Pareto Cutoff Vendor Rank

**Formula**  

The [Pareto Vendor Rank by Purchase (LCY)](#pareto-vendor-rank-by-purchase-lcy) for the [Pareto Cutoff Vendor](#pareto-cutoff-vendor).

**Data Source**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Pareto Vendor Cutoff Rank

**Formula**  

The maximum [Pareto Cutoff Vendor Rank](#pareto-cutoff-vendor-rank) value across all vendors.

**Data Source**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Pareto Vendor Rank by Purchase (LCY)

**Formula**  

The Pareto Vendor Rank by Purchase (LCY) measure calculates the vendor rank, ordered by the [Purchase (LCY)](#purchase-lcy) for all purchases from the **Purchase Value Entries**, **Purchase Credit Lines** and **Purchase Invoice Lines** tables.

**Data Source**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

### Pareto Total Purchase (LCY)

**Formula**  

The total [Purchase (LCY)](#purchase-lcy) for all purchases from the **Purchase Value Entries**, **Purchase Credit Lines** and **Purchase Invoice Lines** tables.

**Data Source**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Memo Line

## Vendor Measures

- [Item Reliance %](#item-reliance-)
- [Spend Reliance %](#spend-reliance-)

### Item Reliance %

**Formula**  
The Item Reliance % measure calculates the proportion of transactions for an item based on either the number of unique vendors or number of unique items, from the Purchase Value Entry Table. In a Vendor context, the Item Reliance % measure is calculated as [No. of Distinct Items](#no-of-distinct-items) divided by the total [No. of Distinct Items](#no-of-distinct-items) for all vendors. In an Item context, the Item Reliance % measure is calculated as one divided by the total [No. of Vendors](#no-of-vendors) who have supplied the item.

### Spend Reliance %

**Formula**  
The Spend Reliance % measure calculates the [Purchase (LCY)](#purchase-lcy) divided by the total [Purchase (LCY)](#purchase-lcy) across all vendors.

**Data Sources**  
- Value Entry
- Purchase Invoice Line
- Purchase Credit Line


**Data Sources**  
- Value Entry

## Purchase Amount Moving Annual Total
- [Purchase Amount MAT (Fiscal)](#purchase-amount-mat-fiscal)  
- [Purchase Amount PYMAT (Fiscal)](#purchase-amount-pymat-fiscal)  
- [Purchase Amount MATG (Fiscal)](#purchase-amount-matg-fiscal)  
- [Purchase Amount MATG % (Fiscal)](#purchase-amount-matg--fiscal)

### Purchase Amount MAT (Fiscal)

**Formula**  
The Purchase Amount MAT (Fiscal) measure calculates the purchases for the last 12 months (moving annual total) using the fiscal calendar by summing up the purchases between the calculated first and last days of the 365-day period.

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Purchase Amount PYMAT (Fiscal)

**Formula**  
The Purchase Amount PYMAT (Fiscal) measure calculates the total purchases for the prior 12 months based on the fiscal calendar. It then determines the maximum available date and calculates the range from 24 months prior to the last available day to 12 months prior. Using these dates, it sums the purchases amount for this period while maintaining filters for the day type and week day.

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Purchase Amount MATG (Fiscal)

**Formula**  
The Purchase Amount MATG (Fiscal) measure compares the current period's moving annual total purchases to the previous period's moving annual total purchases. If both values are not blank, it subtracts the previous period's purchases from the current period's purchases to determine the growth. The result is returned, representing the change in purchases between the two periods.

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Purchase Amount MATG % (Fiscal)

**Formula**  
*Purchase Amount MATG % (Fiscal) = [Purchase Amount MATG (Fiscal)](#purchase-amount-matg-fiscal)  / [Purchase Amount PYMAT (Fiscal)](#purchase-amount-pymat-fiscal)* 

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

## Purchase Amount Moving Averages
- [Purchase Amount AVG 30D (Fiscal)](#purchase-amount-avg-30d-fiscal)  

### Purchase Amount AVG 30D (Fiscal)

**Formula**  
The Purchase Amount AVG 30D (Fiscal) measure calculates the average purchase amount for the past 30 days.
  
**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

## Purchase Amount Period-over-Period Growth
- [Purchase Amount PP (Fiscal)](#purchase-amount-pp-fiscal)  
- [Purchase Amount PY (Fiscal)](#purchase-amount-py-fiscal)  
- [Purchase Amount POP (Fiscal)](#purchase-amount-pop-fiscal)  
- [Purchase Amount POP % (Fiscal)](#purchase-amount-pop--fiscal)  
- [Purchase Amount YOY (Fiscal)](#purchase-amount-yoy-fiscal)  

### Purchase Amount PP (Fiscal)

**Formula**  
The Purchase Amount PP (Fiscal) measure calculates the purchase amount in the previous period. The period is based on the date range you select. For example, if you select a month, the measure will show the purchase amount in the previous month.

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Purchase Amount PY (Fiscal)

**Formula**  
The Purchase Amount PY (Fiscal) measure calculates the purchase amount in the previous year.

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Purchase Amount POP (Fiscal)

**Formula**  
The Purchase Amount POP (Fiscal) measure calculates the change in purchases between the current period and the previous period. The period is based on the date range you select. For example, if you select a month, the measure will show the purchase amount period-over-period compared to the previous month.

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Purchase Amount POP % (Fiscal)

**Formula**  
*Purchase Amount POP % (Fiscal) = [Purchase Amount POP (Fiscal)](#purchase-amount-pop-fiscal) / [Purchase Amount PP (Fiscal)](#purchase-amount-pp-fiscal)*

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Purchase Amount YOY (Fiscal)

**Formula**  
The Purchase Amount YOY (Fiscal) measure shows the purchase amount of a specific period compared to the same period in the previous year. It helps you understand whether your purchases have increased or decreased over time.

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

## Budget Amount Moving Annual Total
- [Budget Amount MAT (Fiscal)](#budget-amount-mat-fiscal)
- [Budget Amount MATG (Fiscal)](#budget-amount-matg-fiscal)
- [Budget Amount MATG % (Fiscal)](#budget-amount-matg--fiscal)
- [Budget Amount PYMAT (Fiscal)](#budget-amount-pymat-fiscal)

### Budget Amount MAT (Fiscal)

**Formula**  
The Budget Amount MAT (Fiscal) measure calculates the purchases for the last 12 months (moving annual total) using the fiscal calendar by summing up the purchases between the calculated first and last days of the 365-day period.

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Budget Amount MATG (Fiscal)

**Formula**  
The Budget Amount MATG (Fiscal) measure compares the current period's moving annual total purchases to the previous period's moving annual total purchases. If both values are not blank, it subtracts the previous period's purchases from the current period's purchases to determine the growth. The result is returned, representing the change in purchases between the two periods.

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Budget Amount MATG % (Fiscal)

**Formula**  
*Budget Amount MATG % (Fiscal) = [Budget Amount MATG (Fiscal)](#budget-amount-matg-fiscal) / [Budget Amount PYMAT (Fiscal)](#budget-amount-pymat-fiscal)* 

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Budget Amount PYMAT (Fiscal)

**Formula**  
The Budget Amount PYMAT (Fiscal) measure calculates the previous year moving annual total (PYMAT) of the Budget Amount by subtracting one year from the current date.

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

## Budget Amount Moving Averages
- [Budget Amount AVG 1Y (Fiscal)](#budget-amount-avg-1y-fiscal)
- [Budget Amount AVG 30D (Fiscal)](#budget-amount-avg-30d-fiscal)
- [Budget Amount AVG 3M (Fiscal)](#budget-amount-avg-3m-fiscal)

### Budget Amount AVG 1Y (Fiscal)

**Formula**  
The Budget Amount AVG 1Y (Fiscal) measure calculates the average budet amount for the past year.
  
**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Budget Amount AVG 30D (Fiscal)
**Formula**  
The Budget Amount AVG 30D (Fiscal) measure calculates the average budet amount for the past 30 days.
  
**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### Budget Amount AVG 3M (Fiscal)
**Formula**  
The Budget Amount AVG 3M (Fiscal) measure calculates the average budet amount for the past 3 months.
  
**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

## Gross Totals
- [% GT Purchase Amount](#-gt-purchase-amount)
- [% GT Purchase Quantity](#-gt-purchase-quantity)
- [% GT Purchase Amount PY (Fiscal)](#-gt-purchase-amount-py-fiscal)  

### % GT Purchase Amount

**Formula**  
*% GT Purchase Amount = [Purchase Amount](#purchase-amount) / Grand Total Purchase Amount*

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### % GT Purchase Quantity

**Formula**  
*% GT Purchase Quantity = [Purchase Quantity](#purchase-quantity) / Grand Total Purchase Quantity*

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)

### % GT Purchase Amount PY (Fiscal)

**Formula**  
*% GT Purchase Amount = [Purchase Amount](#purchase-amount) / Grand Total Purchase Amount (Previous Year)*

**Data Sources**
- Value Entry
- Purchase Line
- Date (Fiscal Calendar)


## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Purchasing app](purchases-powerbi-app.md)  
[Ad hoc analysis of purchasing data](ad-hoc-analysis-purchasing.md)   
[Built-in purchasing reports](purchase-reports.md)  
[Purchasing analytics overview](purchasing-analytics-overview.md)  
[Purchasing overview](purchasing-manage-purchasing.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
