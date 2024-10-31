---
title: Inventory App Semantic Model (Power BI report)
description: The Inventory App semantic model explores the inner works of the semantic model used in the Inventory App.
author: shaungibsonn
ms.author: 
ms.reviewer: 
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: 
ms.date: 10/28/2024
ms.service: dynamics-365-business-central
---

# Inventory Semantic Model (Power BI Report)

The Inventory semantic model is organized in a [Star Schema Model](https://learn.microsoft.com/en-us/power-bi/guidance/star-schema#star-schema-overview). 

The Fact tables contain information about individual entries from sources such as Item Ledger Entries, Warehouse Entries. Dimension tables provide additional context and attributes to the transactional data, such as Location or Item.

## Fact Tables
Fact tables store the transactional data and support summarizations such as SUM, AVG, COUNT and more. There are a variety of fact tables within the Inventory Semantic Model:
- [Item Ledger Entries](#)
- [Warehouse Entries](#)
- [Purchase Lines](#)
- [Sales Lines](#)
- [Assembly Lines](#)
- [Assembly Headers](#)
- [Warehouse Journal Lines (To Bin)](#)
- [Warehouse Journal Lines (From Bin)](#)
- [Warehouse Activity Lines](#)
- [Production Order Lines](#)
- [Prod Order Component Lines](#)
- [Service Lines](#)
- [Transfer Lines](#)
- [Requistion Lines](#)
- [Planning Component Lines](#)

### Item Ledger Entries
Source table(s):
- Item Ledger Entries

##### Table Definition
 Power BI Field Name | Business Central Field Name | Description |
| ------ | -------------- | ---------- |
| Date | Order Date / Posting Date | Order Date is used for data from Sales Lines. Posting Date is used for data from Value Entries. |

## Dimension Table
In the star schema model, the dimension tables are used to support the data model and allowing filtering and grouping.
- [Item](#)
- [Location](#)
- [Customer](#)
- [Vendor](#)
- [Zone](#)
- [Bin](#)
- [Lot No](#)
- [Serial No](#)

### Item
Source table(s):
- Item

##### Table Definition
 Power BI Field Name | Business Central Field Name | Description |
| ------ | -------------- | ---------- |
| Date | Order Date / Posting Date | Order Date is used for data from Sales Lines. Posting Date is used for data from Value Entries. |