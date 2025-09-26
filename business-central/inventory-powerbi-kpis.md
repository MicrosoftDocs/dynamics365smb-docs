---
title: Inventory KPIs and measures (Power BI)
description: The Inventory App KPIs provides a page to clearly identify all KPIs and Measures used in the Inventory Report.
author: kennienp
ms.author: kepontop
ms.reviewer: 
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 
ms.date: 11/08/2024
ms.service: dynamics-365-business-central
---

# Power BI Inventory app KPIs and measures

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

This page provides a list of all Key Performance Indicators (KPIs) included in the semantic model for the Power BI Inventory app. 

Explore the list of KPIs below to learn more about how they can help you achieve your business goals. 

Each KPI is described, including how it is calculated and what data was used in the calculations.

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]


## Assembly Header Measures
- [Qty. on Assembly Order](#qty-on-assembly-order)

### Qty. on Assembly Order
**Formula**  
- This measure shows how many items are yet to be assembled for assembly orders by summing up the remaining quantity of items on all assembly headers.

**Data Sources**
- Assembly Header

## Assembly Line Measures
- [Qty. on Asm. Component](#qty-on-asm-component)  

### Qty. on Asm. Component
**Formula**  
- This measure shows how many items are yet to be assembled for a finished product by summing up the remaining quantity of items on all assembly lines.

**Data Sources**
- Assembly Line

## Bins Measures
- [ATO Components Pick Qty.](#ato-components-pick-qty)  
- [Available Qty. to Take](#available-qty-to-take)
- [Negative Adjmt. Qty. (Base)](#negative-adjmt-qty-base)  
- [Pick Quantity (Base)](#pick-quantity-base)
- [Positive Adjmt. Qty. (Base)](#positive-adjmt-qty-base)
- [Put-away Quantity (Base)](#put-away-quantity-base)
- [Quantity in Adjustment Bin](#quantity-in-adjustment-bin)    
- [Warehouse Quantity](#warehouse-quantity)  

### ATO Components Pick Qty.
**Formula**  
- This measure calculates the total quantity taken from the warehouse for "Assemble to Order" components by summing the qtyBase from Warehouse Activity Lines where actionType is Take, assembleToOrder is TRUE, and atoComponent is TRUE. This measure captures only the quantities picked specifically for assembling made-to-order products.

**Data Sources**
- Warehouse Activity Line

### Available Qty. to Take
**Formula**  
- This measure calculates the quantity of an item that is available to be picked. It subtracts the [Pick Quantity (Base)](#pick-quantity-base), [ATO Components Pick Qty.](#ato-components-pick-qty), and [Negative Adjmt. Qty. (Base)](#negative-adjmt-qty-base) measures from [Warehouse Quantity](#warehouse-quantity), but only for the bins that are not marked as adjustment bins.

**Data Sources**
- Warehouse Entry
- Bin

### Negative Adjmt. Qty. (Base)
**Formula**  
- This measure calculates the total quantity of an item that has been removed from the warehouse due to adjustments. This includes any adjustments that result in inventory decreases in the Warehouse Journal Line table.

**Data Sources**
- Warehouse Journal Line

### Pick Quantity (Base)
**Formula**  
- This measure calculates the total quantity of an item that has been picked from the warehouse for sales or transfer orders. It only includes the quantity that has been picked, not received or moved within the warehouse.

**Data Sources**
- Warehouse Activity Line

### Positive Adjmt. Qty. (Base)
**Formula**  
- This measure calculates the total quantity of an item that has been added to the warehouse due to adjustments. This includes any adjustments that result in inventory increases in the Warehouse Journal Line table.

**Data Sources**
- Warehouse Journal Line

### Put-away Quantity (Base)
**Formula**  
- This measure calculates the total quantity of an item that has been placed in the warehouse for storage. It only includes the quantity that has been put away, not picked or moved within the warehouse.

**Data Sources**
- Warehouse Activity Line

### Quantity in Adjustment Bin
**Formula**
- This measure calculates the total quantity located in bins that are marked as adjustment bins. It first identifies the bins flagged as adjustment bins by creating a filtered table (AdjustmentBins). Then, it sums the Qty. (Base) values from the Warehouse Entries table, applying this filter to include only adjustment bins. The measure ensures the quantity reflects only the specified adjustment bins by removing other bin filters.

**Data Sources**
- Warehouse Entry
- Location

### Warehouse Quantity
**Formula**  
- This measure calculates the total quantity of an item that is currently in the warehouse by summing the base quantity from the Warehouse Entry table.

**Data Sources**
- Warehouse Entry


## Items Availability Measures
- [Gross Requirement](#gross-requirement)
- [Planned Order Receipt](#planned-order-receipt)  
- [Planned Order Releases](#planned-order-releases)    
- [Projected Available Balance](#projected-available-balance)
- [Scheduled Receipt](#scheduled-receipt)

### Gross Requirement
**Formula**  
- This measure calculates the total quantity of an item that is needed to fulfill various orders and projects. It includes the quantity that is on sales orders, service orders, projects, production order component lines, transaction order shipments, planning issues, assembly components, and purchased returns.

  *Gross Requirement = [Qty. on Sales Order](#qty-on-sales-order) + [Qty. on Service Order](#qty-on-service-order) + [Qty. on Projects](#qty-on-projects) + [Qty. on Prod. Order Comp. Lines](#qty-on-prod-order-comp-lines) + - [Trans. Order Shipment (Qty.)](#trans-order-shipment-qty) + [Planning Issues (Qty.)](#planning-issues-qty) + [Qty. on Asm. Component](#qty-on-asm-component) + [Qty. on Purch. Return](#qty-on-purch-return)*

**Data Sources**
- Sales Line
- Purchase Line
- Transfer Line
- Service Line
- Job Planning Line
- Prod. Order Component
- Planning Component
- Assembly Line

### Planned Order Receipt
**Formula**  
- This measure shows the total quantity of items that are planned to be received by the company through planned orders and purchase requisitions.

  *Planned Order Receipt = Planned Order Receipt (Qty.) + Purch. Req. Receipt (Qty.)*

**Data Sources**
- Production Order Line
- Requisition Line

### Planned Order Releases
**Formula**  
- This measure shows the total quantity of items that are planned to be released through planned orders and purchase requisitions.

  *Planned Order Releases = Planned Order Release (Qty.) + Purch. Req. Release (Qty.)*

**Data Sources**
- Production Order Line
- Requisition Line


### Projected Available Balance
**Formula**  
- This measure calculates the current inventory quantity, planned order receipts, scheduled receipts, and gross requirements based on the data up until the most recent date available.

  *Projected Available Balance = [Inventory (Quantity)](#inventory-quantity) + [Planned Order Receipt](#planned-order-receipt) + [Scheduled Receipt](#scheduled-receipt) - [Gross Requirement](#gross-requirement)*

**Data Sources**
- Sales Line
- Purchase Line
- Transfer Line
- Service Line
- Job Planning Line
- Prod. Order Component
- Planning Component
- Assembly Line
- Item Ledger Entry
- Requisition Line
- Production Order Line

### Scheduled Receipt
**Formula**  
- This measure shows the total quantity of items that are scheduled to be received by the company.

  *Scheduled Receipt = [FP Order Receipt (Qty.)](#fp-order-receipt-qty) + [Rel. Order Receipt (Qty.)](#rel-order-receipt-qty) + [Qty. on Purch. Order](#qty-on-purch-order) + [Qty. in Transit](#qty-in-transit) + [Trans. Order Receipt (Qty.)](#trans-order-receipt-qty) + [Qty. on Assembly Order](#qty-on-assembly-order) + [Qty. on Sales Return Order](#qty-on-sales-return-order)*

**Data Sources**
- Sales Line
- Purchase Line
- Transfer Line
- Assembly Header
- Production Order Line


## Item Ledger Entry Measures
- [Expired Inventory](#expired-inventory) 
- [Inventory (Quantity)](#inventory-quantity)  
- [Invoiced Quantity](#invoiced-quantity)
- [Net Qty. Purchased](#net-qty-purchased)  
- [Net Qty. Sold](#net-qty-sold)
- [Quantity](#quantity)
- [Quantity (Forecasting)](#quantity-forecasting)
- [Remaining Quantity](#remaining-quantity)

### Expired Inventory

**Formula**  
- This measure shows how much inventory has expired and is no longer available for sale or use by calculating the remaining quantity of items on all item ledger entries.

**Data Sources**
- Item Ledger Entry

### Inventory (Quantity)

**Formula**  
- This measure shows the total quantity of inventory on hand for all items by summing up the quantity of items on all item ledger entries.

**Data Sources**
- Item Ledger Entry

### Invoiced Quantity

**Formula**  
- This measure calculates the total quantity that has been invoiced by summing all values in the [invoicedQuantity] column from the Item Ledger Entries table. 

**Data Sources**
- Item Ledger Entry

###  Net Qty. Purchased

**Formula**  
- This measure shows the total quantity of items that have been purchased and received by the company by calculating the quantity, filtered to only include item ledger entries that have an entry type of "Purchase".

**Data Sources**
- Item Ledger Entry

###  Net Qty. Sold

**Formula**  
- This measure shows the total quantity of items that have been sold by the company by calculating the quantity, filtered to only include item ledger entries that have an entry type of "Sale".

**Data Sources**
- Item Ledger Entry

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

### Quantity

**Formula**  
- This measure shows the total quantity of items that have been processed through the item ledger by summing up the quantity of items on all item ledger entries including sales, purchases, adjustments, and other types of transactions.

**Data Sources**
- Item Ledger Entry

### Quantity (Forecasting)

**Formula**  
- This measure calculates the **Quantity** within the period of dates with item transactions and inserts zero values for dates without item ledger entries, for compatibility with forecasting.

**Data Sources**
- Item Ledger Entry

### Remaining Quantity

**Formula**  
- This measure calculates the total remaining quantity of items by summing all values in the [Remaining Qty.] column from the Item Ledger Entries table.
**Data Sources**
- Item Ledger Entry

## Planning Component Line Measures

- [Planning Issues (Qty.)](#planning-issues-qty)  

### Planning Issues (Qty.)

**Formula**  
- This measure shows how many items are expected to be consumed for planned production orders by summing up the expected quantity of items that are required for production.

**Data Sources**
- Planning Component


## Prod. Order Component Line Measures

- [Qty. on Prod. Order Comp. Lines](#qty-on-prod-order-comp-lines)  

### Qty. on Prod. Order Comp. Lines

**Formula**  
- This measure shows how many items are yet to be completed on a production order by summing up the total remaining quantity of items on all production order component lines.

**Data Sources**
- Prod. Order Component

## Production Order Line Measures

- [FP Order Receipt (Qty.)](#fp-order-receipt-qty) 
- [Qty. on Prod. Order](#qty-on-prod-order) 
- [Rel. Order Receipt (Qty.)](#rel-order-receipt-qty)
- [Scheduled Receipt (Qty.)](#scheduled-receipt-qty)

### FP Order Receipt (Qty.)

**Formula**  
- This measure is abbreviated for Firmed Planned Order Receipt (Qty.) and hows how many items are expected to be received for firm planned production orders by summing up the remaining quantity of items on all firm planned production order lines.

**Data Sources**
- Production Order Line

### Qty. on Prod. Order

**Formula**  
- This measure shows how many items are yet to be produced for production orders by summing up the remaining quantity of items on all planned, firm planned, and released production order lines.

**Data Sources**
- Production Order Line

### Rel. Order Receipt (Qty.)

**Formula**  
- This measure is abbreviated for Released Production Order Receipt (Qty.) and shows how many items are expected to be received for released production orders by summing up the remaining quantity of items on all released production order lines.

**Data Sources**
- Production Order Line

### Scheduled Receipt (Qty.)

**Formula**
- This measure calculates the total scheduled receipt quantity from production orders by summing the [remainingQtyBase] column in the Production Order Lines table. It includes only those orders where the [Status] is either "Firm Planned" or "Released," which represents production orders expected to be completed. This measure gives an overview of pending quantities that are scheduled for receipt in the near future.

**Data Source**
- Production Order Line

## Project Planning Line Measures

- [Qty. on Projects](#qty-on-projects)

### Qty. on Projects

**Formula**  
- This measure shows how many items or hours are yet to be completed on a project by summing up the total outstanding quantity of items or hours on all project lines.

**Data Sources**
- Project Planning Line

## Purchase Line Measures

- [Qty. on Purch. Order](#qty-on-purch-order)  
- [Qty. on Purch. Return](#qty-on-purch-return)

### Qty. on Purch. Order

**Formula**  
- This measure shows how many items are yet to be received for purchase orders by summing up the outstanding quantity of items on all purchase order lines.

**Data Sources**
- Purchase Line

### Qty. on Purch. Return

**Formula**  
- This measure shows how many items have been returned to the supplier but are yet to be received or credited by summing up the total outstanding quantity of items on all purchase return order lines.

**Data Sources**
- Purchase Line

## Sales Line Measures

- [Qty. on Sales Order](#qty-on-sales-order)
- [Qty. on Sales Return Order](#qty-on-sales-return-order)  

### Qty. on Sales Order

**Formula**  
- This measure shows how many items have been ordered by customers but are yet to be delivered or shipped by summing up the total outstanding quantity of items on all sales order lines. 

**Data Sources**
- Sales Line

### Qty. on Sales Return Order

**Formula**  
- This measure shows how many items are yet to be returned by customers for sales return orders by summing up the outstanding quantity of items on all sales lines that are associated with return orders.

**Data Sources**
- Sales Line


## Service Line Measures

- [Qty. on Service Order](#qty-on-service-order)  

### Qty. on Service Order

**Formula**  
- This measure represents how many service items or hours have been ordered by customers but are yet to be fulfilled by summing up the total outstanding quantity of items or hours on all service order lines.

**Data Sources**
- Service Line


## Transfer Line Measures

- [Qty. in Transit](#qty-in-transit)  
- [Trans. Order Outstanding Qty.](#trans-order-outstanding-qty)
- [Trans. Order Receipt (Qty.)](#trans-order-receipt-qty)
- [Trans. Order Shipment (Qty.)](#trans-order-shipment-qty)

### Qty. in Transit

**Formula**  
- This measure shows how many items are currently in transit between locations by summing up the quantity of items in transit on all transfer lines.

**Data Sources**
- Transfer Line

### Trans. Order Outstanding Qty.

**Formula**
- This measure calculates the total outstanding quantity for transfer orders by summing all values in the [outstandingQtyBase] column from the Transfer Lines table. 

**Data Sources**
- Transfer Line

### Trans. Order Shipment (Qty.)

**Formula**  
- This measure shows how many items have been shipped between two locations by summing up the total outstanding quantity of items on all transfer order lines that are associated with the specified location codes and shipment date.

**Data Sources**
- Transfer Line

### Trans. Order Receipt (Qty.)

**Formula**  
- This measure shows how many items are expected to be received for transfer orders by summing up the outstanding quantity of items on all transfer lines.

**Data Sources**
- Transfer Line

## Related information

[Track KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Power BI Inventory app](inventory-powerbi-app.md)  
[Ad hoc analysis of inventory data](ad-hoc-analysis-inventory.md)  
[Built-in inventory and warehouse reports](inventory-WMS-reports.md)  
[Inventory analytics overview](inventory-analytics-overview.md)  
[Inventory overview](inventory-manage-inventory.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
