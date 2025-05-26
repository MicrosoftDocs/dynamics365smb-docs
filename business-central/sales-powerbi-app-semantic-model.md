---
title: Power BI Sales app semantic model
description: Get an overview of all tables and fields in the Sales App Semantic Model.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 36998, 36999, 37000, 37001, 37002, 37003, 37004, 37005, 37006, 37007, 37008
ms.date: 10/26/2024
ms.service: dynamics-365-business-central
---

# Power BI Sales app semantic model

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The semantic model in the Power BI sales app is organized in a [Star Schema Model](/power-bi/guidance/star-schema#star-schema-overview).

The fact tables contains information about individual transactions from sources such as sales orders, posted sales invoices, and posted credit memos from [!INCLUDE [prod_short](includes/prod_short.md)].

The dimension tables provide more context and attributes to the transactional data, such as customer and product information.

## Fact tables

Fact tables store transactional data and support summarizations such as SUM, AVG, COUNT, and more. There are two fact tables in the Power BI Sales app:

- [Sales](#sales)
- [Sales Budget](#sales-budget)

### Sales

The app uses data from the following tables:

- Value Entries
- Sales Lines

Sales lines are broken down into **Shipped Not Invoiced** and **Outstanding Sales Lines**. Use the **Source Type** field to filter on these sources.

#### Table Definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Date | Order Date / Posting Date | The **Order Date** is used for data from sales lines. The **Posting Date** is used for data from value entries. |
| Document No. |  Document No. | Specifies the document number. |
| Document Type |  Document Type | Specifies the document type. |
| Entry No. |  Entry No. / Sales Line No. | When reporting on value entries, this is the value entry number. When reporting on sales lines, this is the sales line number. |
| Entry Type |  Entry Type | When reporting on value entries, this is the entry type of the value entry. When reporting on sales lines, the value reads **Sales Line**. |
| Source Type |  - | Defines the source table of the record. |

### Sales budget

The app uses data from the following table:

- Item Budget Entries

### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Budget Name | Budget Name | Specifies the name of the budget. |
| Date |  Date | Specifies the date for the budget entry. |
| Entry No. |  Entry No. | The unique number of the specific budget entry. |

## Dimension tables

The star schema model uses dimension tables to support the data model and allow you to filter and group.

- [Customer](#customer)
- [Item](#item)
- [Location](#location)
- [Salesperson](#salesperson)

### Customer

The app uses data from the following table:

- Customer

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Customer No. | No. | Specifies the customer number. |
| Customer Name |  Name | Specifies the customer name. |
| Customer No. and Name |  - | Specifies a combination of customer number and customer name in Power BI. |
| Address | Address | Specifies the address. |
| Address 2 |  Address 2 | Specifies the secondary address details. |
| City |  City | Specifies the city. |
| Post Code | Post Code | Specifies the postal code of the address. |
| County |  County | Specifies the state. |
| Country/Region Code |  Country/Region Code | Specifies the country/region the address is in. |
| Customer Posting Group | Customer Posting Group | Specifies the posting group. |
| Customer Price Group |  Customer Price Group | Specifies the price group. |
| Customer Disc. Group |  Customer Disc Group | Specifies the discount group. |

### Item

The app uses data from the following tables:

- Item
- Item Category

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Item No. | No. | Specifies the item number. |
| Item Name |  Description | Specifies the item description. |
| Item No. and Name |  - | Specifies a combination of item number and item name in Power BI. |
| Base Unit of Measure | Base Unit of Measure | Specifies the base unit of measure. |
| Unit Cost |  Unit Cost | Specifies the unit cost. |
| Inventory Posting Group | Inventory Posting Group | Specifies the inventory posting group. |
| Item Category Code |  Code | Specifies the item category. |
| Item Category Description |  Description | Specifies the description of the item category the item belongs to. |

### Location

The app uses data from the following table:

- Location

### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Location Code | Code | Specifies the ID of the location. |
| Location Name |  Name | Specifies the name of the location. |

### Salesperson

The app uses data from the following table:

- Salesperson/Purchaser

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Salesperson Code | Code | Specifies the ID of the salesperson. |
| Salesperson Name |  Name | Specifies the name of the salesperson. |

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad-hoc analysis of sales data](ad-hoc-analysis-sales.md)  
[Built-in sales reports](sales-reports.md)  
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
