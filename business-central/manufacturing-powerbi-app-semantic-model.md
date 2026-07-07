---
title: Power BI Manufacturing app semantic model
description: Get an overview of the Power BI Manufacturing app semantic model, including its business fact and dimension tables and visible fields.
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

# Power BI Manufacturing app semantic model

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The semantic model in the Power BI Manufacturing app is organized in a [Star Schema Model](/power-bi/guidance/star-schema#star-schema-overview).

The fact tables contain information about individual transactions, such as capacity ledger entries, production order lines, and value entries from [!INCLUDE [prod_short](includes/prod_short.md)].

The dimension tables provide more context and attributes to the transactional data, such as item, location, routing, and work center information.

## Fact tables

Fact tables store transactional data and support summarizations such as SUM, AVG, COUNT, and more. The Power BI Manufacturing app includes several fact tables:

- [Calendar Entries](#calendar-entries)
- [Capacity Ledger Entries](#capacity-ledger-entries)
- [Item Ledger Entries](#item-ledger-entries)
- [Prod Order Capacity Need](#prod-order-capacity-need)
- [Prod Order Components](#prod-order-components)
- [Prod Order Routing Lines](#prod-order-routing-lines)
- [Production Order Lines](#production-order-lines)
- [Value Entries](#value-entries)

### Calendar entries

The app uses data from the following table:

- Calendar Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Capacity Type | Capacity Type | Specifies whether the calendar entry is for a work center or a machine center. |

### Capacity Ledger Entries

The app uses data from the following table:

- Capacity Ledger Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Order Type | Order Type | Specifies the type of order that created the capacity ledger entry. |
| Order Line No. | Order Line No. | Specifies the line number of the order that created the capacity ledger entry. |
| Type | Type | Specifies whether the capacity ledger entry is for a machine center or a work center. |
| No. | No. | Specifies the number of the machine center or work center on the capacity ledger entry. |
| Description | Description | Specifies a description of the capacity ledger entry. |
| Routing No. | Routing No. | Specifies the routing number for the capacity ledger entry. |
| Routing Reference No. | Routing Reference No. | Specifies the routing reference number for the capacity ledger entry. |
| Operation No. | Operation No. | Specifies the operation number for the capacity ledger entry. |
| Scrap Code | Scrap Code | Specifies the scrap code for the capacity ledger entry. |
| Entry No. | Entry No. | Specifies the number of the capacity ledger entry. |
| Work Shift Code | Work Shift Code | Specifies the work shift code for the capacity ledger entry. |
| Capacity Unit of Measure | Cap. Unit of Measure Code | Specifies the unit of measure code for the capacity used by the entry. |
| Qty. Per Unit of Measure | Qty. per Unit of Measure | Specifies the quantity per unit of measure for the capacity ledger entry. |
| Qty. Per Capacity Unit of Measure | Qty. per Cap. Unit of Measure | Specifies the quantity per capacity unit of measure for the capacity ledger entry. |

### Item Ledger Entries

The app uses data from the following table:

- Item Ledger Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Serial No. | Serial No. | Specifies the serial number of the item on the item ledger entry. |
| Lot No. | Lot No. | Specifies the lot number of the item on the item ledger entry. |
| Entry Type | Entry Type | Specifies the type of item transaction, such as consumption or output. |
| Order Type | Order Type | Specifies the type of order that created the item ledger entry. |
| Order Line No. | Order Line No. | Specifies the line number of the order that created the item ledger entry. |
| Positive | Positive | Specifies whether the item ledger entry increases inventory. |

### Prod Order Capacity Need

The app uses data from the following table:

- Prod. Order Capacity Need

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Routing Reference No. | Routing Reference No. | Specifies the routing reference number for the capacity need. |
| Operation No. | Operation No. | Specifies the operation number for the capacity need. |
| Requested Only | Requested Only | Specifies whether the capacity need is requested only. |
| Type | Type | Specifies whether the capacity need is for a machine center or a work center. |
| Prod Order Capacity Need Line No. | Line No. | Specifies the line number of the production order capacity need. |

### Prod Order Components

The app uses data from the following table:

- Prod. Order Component

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Prod Order Components Line No. | - | Specifies the line number generated for the production order component in Power BI. |

### Prod Order Routing Lines

The app uses data from the following tables:

- Prod. Order Routing Line
- Work Center
- Machine Center

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| No. | No. | Specifies the number of the machine center or work center on the routing line. |
| Routing Link Code | Routing Link Code | Specifies the routing link code for the routing line. |
| Description | Description | Specifies the description of the routing line. |
| Routing No. | Routing No. | Specifies the routing number for the routing line. |
| Routing Reference No. | Routing Reference No. | Specifies the routing reference number for the routing line. |
| Operation No. | Operation No. | Specifies the operation number for the routing line. |
| Setup Time | Setup Time | Specifies the setup time for the operation. |
| Run Time | Run Time | Specifies the run time for the operation. |
| Wait Time | Wait Time | Specifies the wait time after the operation. |
| Move Time | Move Time | Specifies the move time after the operation. |
| Routing Status | Routing Status | Specifies the status of the routing line. |
| Work/Machine Center Name | - | Specifies the name of the related work center or machine center in Power BI. |
| Ending Date Time | Ending Date-Time | Specifies the ending date and time for the routing line. |
| Starting Date Time | Starting Date-Time | Specifies the starting date and time for the routing line. |

### Production Order Lines

The app uses data from the following table:

- Prod. Order Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Prod. Order Line No. | Line No. | Specifies the line number of the production order line. |
| Routing No. | Routing No. | Specifies the routing number for the production order line. |
| Routing Reference No. | Routing Reference No. | Specifies the routing reference number for the production order line. |
| Routing Type | Routing Type | Specifies the routing type for the production order line. |
| Scrap Percent | Scrap % | Specifies the percentage of the item that you expect to be scrapped during production. |
| Planning Level Code | Planning Level Code | Specifies the planning level code for the production order line. |

### Value Entries

The app uses data from the following table:

- Value Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Entry No. | Entry No. | Specifies the number of the value entry. |
| Valuation Date | Valuation Date | Specifies the date used to include the value entry in inventory valuation. |
| Cost Per Unit | Cost per Unit | Specifies the cost per unit for the value entry. |
| Item Ledger Entry Type | Item Ledger Entry Type | Specifies the type of item ledger entry that caused the value entry. |
| Type | Type | Specifies the type of value entry when the entry relates to capacity. |
| No. | No. | Specifies the number of the item, resource, machine center, or work center on the value entry. |
| Capacity Ledger Entry No. | Capacity Ledger Entry No. | Specifies the capacity ledger entry that the value entry is linked to. |
| Entry Type | Entry Type | Specifies the type of value that the entry represents. |
| Order Type | Order Type | Specifies the type of order that created the value entry. |
| Order No. | Order No. | Specifies the number of the order that created the value entry. |

## Dimension tables

The star schema model uses dimension tables and you can filter and group data.

- [Item](#item)
- [Item Category](#item-category)
- [Location](#location)
- [Machine Center](#machine-center)
- [Production Orders](#production-orders)
- [Routing](#routing)
- [Work Center](#work-center)
- [Work Center Group](#work-center-group)

### Item

The app uses data from the following tables:

- Item
- Item Category

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Item No. & Description | - | Specifies a combination of item number and description in Power BI. |
| Item No. | No. | Specifies the number of the item. |
| Item Description | Description | Specifies the description of the item. |
| Item Unit Cost (LCY) | Unit Cost | Specifies the unit cost of the item. |
| Item Inventory Posting Group | Inventory Posting Group | Specifies the inventory posting group of the item. |
| Item Routing No. | Routing No. | Specifies the routing number assigned to the item. |
| Item Production BOM No. | Production BOM No. | Specifies the production bill of materials assigned to the item. |
| Item Replenishment System | Replenishment System | Specifies how the item is replenished, such as purchase, production order, or assembly. |
| Item Single-Level Cap. Ovhd Cost | Single-Level Cap. Ovhd Cost | Specifies the single-level capacity overhead cost of the item. |
| Item Single-Level Capacity Cost | Single-Level Capacity Cost | Specifies the single-level capacity cost of the item. |
| Item Single-Level Material Cost | Single-Level Material Cost | Specifies the single-level material cost of the item. |
| Item Single-Level Mfg. Ovhd Cost | Single-Level Mfg. Ovhd Cost | Specifies the single-level manufacturing overhead cost of the item. |
| Item Single-Level Subcontrd. Cost | Single-Level Subcontrd. Cost | Specifies the single-level subcontracted cost of the item. |
| Item Base Unit of Measure | Base Unit of Measure | Specifies the base unit used to measure the item. |
| Item Rolled-up Cap. Overhead Cost | Rolled-up Cap. Overhead Cost | Specifies the rolled-up capacity overhead cost of the item. |
| Item Rolled-up Capacity Cost | Rolled-up Capacity Cost | Specifies the rolled-up capacity cost of the item. |
| Item Rolled-up Material Cost | Rolled-up Material Cost | Specifies the rolled-up material cost of the item. |
| Item Rolled-up Mfg. Ovhd Cost | Rolled-up Mfg. Ovhd Cost | Specifies the rolled-up manufacturing overhead cost of the item. |
| Item Rolled-up Subcontracted Cost | Rolled-up Subcontracted Cost | Specifies the rolled-up subcontracted cost of the item. |
| Item Scrap % | Scrap % | Specifies the percentage of the item that you expect to be scrapped during production. |
| Item Single-Lvl Mat. Non-Invt. Cost | Single-Lvl Mat. Non-Invt. Cost | Specifies the single-level material non-inventory cost of the item. |
| Item Rolled-up Mat. Non-Invt. Cost | Rolled-up Mat. Non-Invt. Cost | Specifies the rolled-up material non-inventory cost of the item. |

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
| Location Code | Code | Specifies the location code for the warehouse or distribution center. |
| Location Name | Name | Specifies the name of the location. |
| Location Adjustment Bin Code | - | Specifies a combination of adjustment bin code and location code in Power BI. |

### Machine Center

The app uses data from the following tables:

- Machine Center
- Work Center

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Machine Center No. | No. | Specifies the number of the machine center. |
| Machine Center Name | Name | Specifies the name of the machine center. |
| Work Center No. | Work Center No. | Specifies the work center that the machine center belongs to. |
| Work Center Unit of Measure | Unit of Measure Code | Specifies the unit of measure code for the related work center. |
| Work Center Name | Name | Specifies the name of the related work center. |

### Production Orders

The app uses data from the following tables:

- Production Order
- Item

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Prod Order Status | Status | Specifies the status of the production order. |
| Prod Order No. | No. | Specifies the number of the production order. |
| Prod Order Source No. | Source No. | Specifies the number of the source item or family for the production order. |
| Prod Order Routing No. | Routing No. | Specifies the routing number used for the production order. |
| Prod Order Starting Date | Starting Date | Specifies the starting date of the production order. |
| Prod Order Ending Date | Ending Date | Specifies the ending date of the production order. |
| Prod Order Due Date | Due Date | Specifies the due date of the production order. |
| Prod Order Description | Description | Specifies the description of the production order. |
| Prod Order Source Type | Source Type | Specifies the source type of the production order. |
| Production Order | - | Specifies a combination of production order status and number in Power BI. |
| Prod Order Source No. Scrap % | Scrap % | Specifies the scrap percentage for the source item of the production order. |

### Routing

The app uses data from the following table:

- Routing Header

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Routing No. | No. | Specifies the number of the routing. |
| Routing Type | Type | Specifies how operations in the routing are performed. |
| Routing Status | Status | Specifies the status of the routing. |
| Routing Description | Description | Specifies the description of the routing. |

### Work Center

The app uses data from the following tables:

- Work Center
- Work Center Group

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Work Center Name | Name | Specifies the name of the work center. |
| Work Center Group Code | Work Center Group Code | Specifies the work center group that the work center belongs to. |
| Work Center Group Name | Name | Specifies the name of the related work center group. |
| Work Center No. | No. | Specifies the number of the work center. |
| Work Center Subcontractor No. | Subcontractor No. | Specifies the number of the subcontractor that supplies the work center. |
| Work Center Unit of Measure Code | Unit of Measure Code | Specifies the unit of measure code for the work center. |
| Subcontracting | - | Specifies whether the work center has a subcontractor in Power BI. |

### Work Center Group

The app uses data from the following table:

- Work Center Group

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Work Center Group Code | Code | Specifies the code for the work center group. |
| Work Center Group Name | Name | Specifies the name of the work center group. |

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Related information

[Manufacturing KPIs](manufacturing-powerbi-kpis.md)  
[Power BI manufacturing app](manufacturing-powerbi-app.md)  
[Use Power BI with Business Central](admin-powerbi.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
