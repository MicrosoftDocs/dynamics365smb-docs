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

## Counters
- [No. of Distinct Items](#no-of-distinct-items)
- [No. of Outstanding Purchase Orders](#no-of-outstanding-purchase-orders)
- [No. of Purchase Invoices](#no-of-purchase-invoices)
- [No. of Received Not Invd. Purchase Orders](#no-of-received-not-invd-purchase-orders)

### No. of Distinct Items

**Formula**  
The No. of Distinct Items calculates the number of unique items that have been purchased by counting the distinct values of the Item No. column of the Purchases table.

**Data Sources**
- Purchase Line
- Value Entry 

### No. of Outstanding Purchase Orders

**Formula**  
The No. of Outstanding Purchase Orders calculates the number of unique purchase orders that are currently outstanding, by counting the distinct values of the Document No. column of the Purchases table, where Document Type = Order and Source Type = Purchase Order Outstanding.

**Data Sources**
- Purchase Line
- Value Entry

### No. of Purchase Invoices

**Formula**
The No. of Purchase Invoices measure calculates the number of unique posted purchase invoices by countint the distinct count of the Document No. column from the Purchases table where Document Type = Purchase Invoice and Source Type = Value Entries Invoiced.

**Data Sources**
- Purchase Line
- Value Entry

### No. of Received Not Invd. Purchase Orders

**Formula**
The No. of Received Not Invd. Purchase Orders measure calculates the number of unique purchase orders that are received but not invoiced, by counting the distinct count of Document No. column from the Purchases table where Document Type = Order and Source Type = Purchase Orders Received Not Invoiced.

**Data Sources**
- Purchase Line
- Value Entry

## Purchase Measures
- [Purchase Amount](#purchase-amount)
- [Purchase Quantity](#purchase-quantity)

### Purchase Amount

**Formula**
The Purchase Amount measure sums the the Purchase Amount column of the Purchases table.

**Data Sources**
- Value Entry

### Purchase Quantity

**Formula**
The Purchase Quantity measure sums the the Purchase Quantity column of the Purchases table.

**Data Sources**
- Value Entry

## Invoiced
- [Invoiced Amount](#invoiced-amount)
- [Invoiced Quantity](#invoiced-quantity)

### Invoiced Amount

**Formula**
The Invoiced Amount calculates the total amount of items that have been purchased and invoiced, by summing the Purchase Amount column of the Purchases table, where Source Type = Purchase Value Entries Invoiced.

**Data Sources**
- Value Entry

### Invoiced Quantity

**Formula**
The Invoiced Quantity measure calculates the total quantity of items that have been purchased and invoiced, by summing the Purchase Quantity column of the Purchases table, where Source Type = Purchase Value Entries Invoiced.

**Data Sources**
- Value Entry

## Outstanding
- [Outstanding Amount (Excl. VAT)](#outstanding-amount-excl-vat)
- [Outstanding Quantity](#outstanding-quantity)

### Outstanding Amount (Excl. VAT)

**Formula**  
The Outstanding Amount (Excl. VAT) measure calculates the sum of Purchase Amount column from the Purchases table where Source Type = Purchase Order Outstanding, excluding VAT.

**Data Sources**
- Purchase Line

### Outstanding Quantity

**Formula**  
The Outstanding Quantity measure calculates the sum of Purchase Qty. (Base) column from the Purchases table where Source Type = Purchase Order Outstanding.

**Data Sources**
- Purchase Line

## Received Not Invoiced
- [Amt. Rcd. Not Invd. (Excl. VAT)](#amt-rcd-not-invd-excl-vat)
- [Quantity Rcd. Not Invd.](#amt-rcd-not-invd-excl-vat)

### Amt. Rcd. Not Invd. (Excl. VAT)

**Formula**  
The Amt. Rcd. Not Invd. (Excl. VAT) measure calculates the sum of Purchase Amount column from the Purchases table where Source Type = Purchase Order Received Not Invoiced, excluding VAT.

**Data Sources**
- Purchase Line

### Quantity Rcd. Not Invd.

**Formula**  
The Quantity Rcd. Not Invd. measure calculates the sum of Purchase Qty. (Base) column from the Purchases table. where Source Type = Purchase Order Received Not Invoiced.

**Data Sources**
- Purchase Line

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
