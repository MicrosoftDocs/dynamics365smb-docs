---
title: Power BI Inventory app semantic model
description: Learn how the Power BI Inventory app semantic model organizes inventory, supply, demand, warehouse, and item dimension data from Business Central.
author: SusanneWindfeldPedersen
ms.author: solsen
ms.reviewer: solsen
ms.topic: concept-article
ms.search.keywords: reporting
ms.date: 07/03/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
ai.usage: ai-assisted
---

# Power BI Inventory app semantic model

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The semantic model in the Power BI Inventory app is organized in a [Star Schema Model](/power-bi/guidance/star-schema#star-schema-overview).

The fact tables contain information about individual transactions, such as item ledger entries, purchase and sales lines, production order lines, and warehouse activity from [!INCLUDE [prod_short](includes/prod_short.md)].

The dimension tables provide more context and attributes to the transactional data, such as item, customer, vendor, location, bin, lot, and serial number information.

## Fact tables

Fact tables store transactional data and support summarizations such as SUM, AVG, COUNT, and more. The Power BI Inventory app includes several fact tables:

- [Assembly Headers](#assembly-headers)
- [Assembly Lines](#assembly-lines)
- [Item Ledger Entries](#item-ledger-entries)
- [Planning Component Lines](#planning-component-lines)
- [Prod Order Component Lines](#prod-order-component-lines)
- [Production Order Lines](#production-order-lines)
- [Project Planning Lines](#project-planning-lines)
- [Purchase Lines](#purchase-lines)
- [Requisition Line](#requisition-line)
- [Sales Lines](#sales-lines)
- [Service Lines](#service-lines)
- [Transfer Lines](#transfer-lines)
- [Warehouse Activity Lines](#warehouse-activity-lines)
- [Warehouse Entries](#warehouse-entries)
- [Warehouse Journal Lines (From Bin)](#warehouse-journal-lines-from-bin)
- [Warehouse Journal Lines (To Bin)](#warehouse-journal-lines-to-bin)

### Assembly Headers

The app uses data from the following table:

- Assembly Header

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Document No. | No. | Specifies the number of the assembly order. |
| Status | Status | Specifies the status of the assembly order. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the assembly order unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the assembly item is measured. |

### Assembly Lines

The app uses data from the following table:

- Assembly Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Document No. | Document No. | Specifies the number of the assembly order that the line belongs to. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the assembly line unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the assembly component is measured. |

### Item Ledger Entries

The app uses data from the following table:

- Item Ledger Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Entry No. | Entry No. | Specifies the number of the item ledger entry. |
| Entry Type | Entry Type | Specifies the type of inventory transaction, such as purchase, sale, positive adjustment, or negative adjustment. |
| Expiration Date | Expiration Date | Specifies the date when the item on the entry expires. |
| Open | Open | Specifies whether the item ledger entry is still open for application. |
| Document No. | Document No. | Specifies the document number that created the item ledger entry. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the entry unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the item is measured. |
| Document Type | Document Type | Specifies the type of document that created the item ledger entry. |

### Planning Component Lines

The app uses data from the following table:

- Planning Component

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the planning component unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the planning component is measured. |

### Prod Order Component Lines

The app uses data from the following table:

- Prod. Order Component

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Status | Status | Specifies the status of the production order that the component belongs to. |
| Document No. | Prod. Order No. | Specifies the number of the related production order. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the component unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the production order component is measured. |

### Production Order Lines

The app uses data from the following table:

- Prod. Order Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Status | Status | Specifies the status of the production order that the line belongs to. |
| Document No. | Prod. Order No. | Specifies the number of the related production order. |
| Starting Date | Starting Date | Specifies the date when production is planned to start. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the production order unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the produced item is measured. |

### Project Planning Lines

The app uses data from the following table:

- Project Planning Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Document No. | Document No. | Specifies the document number for the project planning line. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the planning line unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the item on the project planning line is measured. |

### Purchase Lines

The app uses data from the following table:

- Purchase Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Document No. | Document No. | Specifies the document number of the purchase line. |
| Expected Receipt Date | Expected Receipt Date | Specifies the date when the purchased items are expected to be received. |
| Document Type | Document Type | Specifies the type of purchase document. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the purchase line unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the purchased item is measured. |

### Requisition Line

The app uses data from the following table:

- Requisition Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the requisition line unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the requisition line item is measured. |
| Auxiliary Index 1 | - | Specifies an auxiliary index used by the semantic model for requisition line calculations. |

### Sales Lines

The app uses data from the following table:

- Sales Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Document No. | Document No. | Specifies the document number of the sales line. |
| Shipment Date | Shipment Date | Specifies the date when the items on the sales line are expected to ship. |
| Document Type | Document Type | Specifies the type of sales document. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the sales line unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the sold item is measured. |

### Service Lines

The app uses data from the following table:

- Service Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Document No. | Document No. | Specifies the document number of the service line. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the service line unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the service line item is measured. |

### Transfer Lines

The app uses data from the following table:

- Transfer Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Document No. | Document No. | Specifies the document number of the transfer line. |
| Receipt Date | Receipt Date | Specifies the date when the transfer-to location is expected to receive the items. |
| Transfer To Location Code | Transfer-to Code | Specifies the code of the location that the items are transferred to. |
| Transfer From Location Code | Transfer-from Code | Specifies the code of the location that the items are transferred from. |
| Shipment Date | Shipment Date | Specifies the date when the transfer-from location is expected to ship the items. |
| In Transit Location Code | In-Transit Code | Specifies the in-transit location code for the transfer. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the transfer line unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the transferred item is measured. |

### Warehouse Activity Lines

The app uses data from the following table:

- Warehouse Activity Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Action Type | Action Type | Specifies whether the warehouse activity line is a take or place action. |
| Assemble to Order | Assemble to Order | Specifies whether the warehouse activity line is related to an assemble-to-order item. |
| ATO Component | ATO Component | Specifies whether the warehouse activity line handles an assemble-to-order component. |
| Quantity (Base) | Qty. (Base) | Specifies the quantity on the warehouse activity line in the base unit of measure. |
| Bin Key | - | Specifies a semantic model key that combines the bin code and location code. |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the warehouse activity unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit on the warehouse activity line is measured. |

### Warehouse Entries

The app uses data from the following table:

- Warehouse Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the warehouse entry unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit on the warehouse entry is measured. |

### Warehouse Journal Lines (From Bin)

The app uses data from the following table:

- Warehouse Journal Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the warehouse journal line unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit on the warehouse journal line is measured. |

### Warehouse Journal Lines (To Bin)

The app uses data from the following table:

- Warehouse Journal Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Quantity Per Unit of Measure | Qty. per Unit of Measure | Specifies the number of base units in the warehouse journal line unit of measure. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit on the warehouse journal line is measured. |

## Dimension tables

The star schema model uses dimension tables and you can filter and group data.

- [ABC Classification](#abc-classification)
- [Bin](#bin)
- [Customer](#customer)
- [Item](#item)
- [Item Availability Filter](#item-availability-filter)
- [Item Category](#item-category)
- [Location](#location)
- [Lot No](#lot-no)
- [Serial No](#serial-no)
- [Vendor](#vendor)
- [Zone](#zone)

### ABC Classification

The app builds this table in the semantic model from the following tables:

- ABC Analysis Setup

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| ABC Class | - | Specifies the ABC class used to group items by sales contribution. |
| Class Boundaries | - | Specifies the lower and upper percentage boundaries for each ABC class in Power BI. |

### Bin

The app uses data from the following table:

- Bin

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Bin Description | Description | Specifies the description of the bin. |
| Bin Type Code | Bin Type Code | Specifies the bin type code that defines how the bin is used in warehouse activities. |
| Bin Code | Code | Specifies the code of the bin. |
| Adjustment Bin | - | Specifies whether the bin is the adjustment bin for the location in Power BI. |
| Bin Zone Code | Zone Code | Specifies the zone code that the bin belongs to. |

### Customer

The app uses data from the following table:

- Customer

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Customer No. & Name | - | Specifies a combination of customer number and customer name in Power BI. |
| Customer No. | No. | Specifies the number of the customer. |
| Customer Name | Name | Specifies the name of the customer. |
| Customer Address | Address | Specifies the address of the customer. |
| Customer Address 2 | Address 2 | Specifies additional address information. |
| Customer City | City | Specifies the city of the customer. |
| Customer Post Code | Post Code | Specifies the postal code. |
| Customer State | County | Specifies the state, province, or county as part of the address. |
| Customer Country/Region Code | Country/Region Code | Specifies the country/region of the address. |
| Customer Posting Group | Customer Posting Group | Specifies the customer's posting group. |
| Customer Price Group | Customer Price Group | Specifies the customer price group. |
| Customer Discount Group | Customer Disc. Group | Specifies the customer discount group. |

### Item

The app uses data from the following tables:

- Item
- Item Category

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Item No. & Description | - | Specifies a combination of item number and item description in Power BI. |
| Item No. | No. | Specifies the number of the item. |
| Item Description | Description | Specifies the description of the item. |
| Item Base Unit of Measure | Base Unit of Measure | Specifies the base unit used to measure the item. |
| Item Unit Cost (LCY) | Unit Cost | Specifies the unit cost of the item in the local currency. |
| Item Inventory Posting Group | Inventory Posting Group | Specifies the inventory posting group for the item. |
| Item Routing No. | Routing No. | Specifies the routing number used to produce the item. |
| Item Production BOM No. | Production BOM No. | Specifies the production BOM number used to produce the item. |
| Item Replenishment System | Replenishment System | Specifies the replenishment system that supplies the item. |
| Item Single-Level Cap. Ovhd Cost | Single-Level Cap. Ovhd Cost | Specifies the single-level capacity overhead cost of the item. |
| Item Single-Level Capacity Cost | Single-Level Capacity Cost | Specifies the single-level capacity cost of the item. |
| Item Single-Level Material Cost | Single-Level Material Cost | Specifies the single-level material cost of the item. |
| Item Single-Level Mfg. Ovhd Cost | Single-Level Mfg. Ovhd Cost | Specifies the single-level manufacturing overhead cost of the item. |
| Item Single-Level Subcontrd. Cost | Single-Level Subcontrd. Cost | Specifies the single-level subcontracted cost of the item. |
| Item Single-Lvl Mat. Non-Invt. Cost | Single-Lvl Mat. Non-Invt. Cost | Specifies the single-level material non-inventory cost of the item. |
| Item Rolled-up Cap. Overhead Cost | Rolled-up Cap. Overhead Cost | Specifies the rolled-up capacity overhead cost of the item. |
| Item Rolled-up Capacity Cost | Rolled-up Capacity Cost | Specifies the rolled-up capacity cost of the item. |
| Item Rolled-up Mat. Non-Invt. Cost | Rolled-up Mat. Non-Invt. Cost | Specifies the rolled-up material non-inventory cost of the item. |
| Item Rolled-up Material Cost | Rolled-up Material Cost | Specifies the rolled-up material cost of the item. |
| Item Rolled-up Mfg. Ovhd Cost | Rolled-up Mfg. Ovhd Cost | Specifies the rolled-up manufacturing overhead cost of the item. |
| Item Rolled-up Subcontracted Cost | Rolled-up Subcontracted Cost | Specifies the rolled-up subcontracted cost of the item. |
| Item Scrap % | Scrap % | Specifies the percentage of the item that is expected to be scrapped during production. |

### Item Availability Filter

The app builds this table in the semantic model from the following tables:

- Date

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| View As | - | Specifies whether item availability values show net change or balance at date in Power BI. |
| Ordinal | - | Specifies the sort order for the item availability view options in Power BI. |

### Item Category

The app uses data from the following table:

- Item Category

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Item Category Code | Code | Specifies the code for the item category. |
| Item Category Description | Description | Specifies the description of the item category. |

### Location

The app uses data from the following table:

- Location

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Location Code | Code | Specifies the code of the inventory location. |
| Location Name | Name | Specifies the name of the inventory location. |
| Location Adjustment Bin Code | - | Specifies a semantic model key that combines the adjustment bin code and location code. |

### Lot No

The app builds this table in the semantic model from the following tables:

- Item Ledger Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Lot No. | Lot No. | Specifies the lot number assigned to item ledger and warehouse transactions. |

### Serial No

The app builds this table in the semantic model from the following tables:

- Item Ledger Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Serial No. | Serial No. | Specifies the serial number assigned to item ledger and warehouse transactions. |

### Vendor

The app uses data from the following table:

- Vendor

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Vendor No. & Name | - | Specifies a combination of vendor number and vendor name in Power BI. |
| Vendor No. | No. | Specifies the number of the vendor. |
| Vendor Name | Name | Specifies the name of the vendor. |
| Vendor Address | Address | Specifies the address of the vendor. |
| Vendor Address 2 | Address 2 | Specifies additional address information. |
| Vendor City | City | Specifies the city of the vendor. |
| Vendor Post Code | Post Code | Specifies the postal code. |
| Vendor State | County | Specifies the state, province, or county as part of the address. |
| Vendor Country/Region Code | Country/Region Code | Specifies the country/region of the address. |
| Vendor Posting Group | Vendor Posting Group | Specifies the vendor's posting group. |

### Zone

The app uses data from the following table:

- Zone

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Zone Description | Description | Specifies the description of the zone. |
| Zone Bin Type Code | Bin Type Code | Specifies the bin type code used for bins in the zone. |
| Zone Code | Code | Specifies the code of the zone. |

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Related information

[Inventory KPIs](inventory-powerbi-kpis.md)  
[Power BI inventory app](inventory-powerbi-app.md)  
[Use Power BI with Business Central](admin-powerbi.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
