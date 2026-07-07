---
title: Power BI Purchases app semantic model
description: Learn about the fact and dimension tables and visible fields in the Power BI Purchases app semantic model for Business Central reports.
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

# Power BI Purchases app semantic model

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The semantic model in the Power BI Purchases app uses a [Star Schema Model](/power-bi/guidance/star-schema#star-schema-overview).

The fact tables hold details about individual transactions, like purchase budgets, purchase lines, and posted purchase entries from [!INCLUDE [prod_short](includes/prod_short.md)].

The dimension tables add context and attributes to the transactional data, including vendor, item, project, and purchaser information.

## Fact tables

Fact tables store transactional data and support summarizations such as SUM, AVG, COUNT, and more. The Power BI Purchases app includes several fact tables:

- [Purchase Budget](#purchase-budget)
- [Purchase Credit Lines](#purchase-credit-lines)
- [Purchase Invoice Lines](#purchase-invoice-lines)
- [Purchase Lines](#purchase-lines)
- [Purchase Value Entries](#purchase-value-entries)

### Purchase Budget

The app uses data from the following table:

- Item Budget Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Entry No. | Entry No. | Specifies the entry number of the purchase budget entry. |

### Purchase Credit Lines

The app uses data from the following tables:

- Purch. Cr. Memo Line
- Purch. Cr. Memo Hdr.

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Description | Description | Specifies a description of the posted purchase credit memo line. |
| Purchase Credit Line No. | Line No. | Specifies the line number of the posted purchase credit memo line. |
| Exprected Receipt Date | Expected Receipt Date | Specifies the expected receipt date on the posted purchase credit memo line. |

### Purchase Invoice Lines

The app uses data from the following tables:

- Purch. Inv. Line
- Purch. Inv. Header

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Description | Description | Specifies a description of the posted purchase invoice line. |
| Purchase Invoice Line No. | Line No. | Specifies the line number of the posted purchase invoice line. |
| Expected Receipt Date | Expected Receipt Date | Specifies the expected receipt date on the posted purchase invoice line. |

### Purchase Lines

The app uses data from the following tables:

- Purchase Header
- Purchase Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Order Date | Order Date | Specifies the date when the purchase order was created. |
| Document Date | Document Date | Specifies the date when the purchase document was created. |
| Due Date | Due Date | Specifies when the purchase invoice is due for payment. |
| Description | Description | Specifies a description of the purchase line. |
| Purchase Line No. | Line No. | Specifies the line number of the purchase line. |
| Planned Receipt Date | Planned Receipt Date | Specifies the date when the item is planned to arrive in inventory. |
| Expected Receipt Date | Expected Receipt Date | Specifies the date when you expect to receive the items. |
| Promised Receipt Date | Promised Receipt Date | Specifies the date that the vendor promised to deliver the order. |
| Requested Receipt Date | Requested Receipt Date | Specifies the date that you requested the vendor to deliver the order. |

### Purchase value entries

The app uses data from the following tables:

- Value Entry
- Item Ledger Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Item Ledger Entry No. | Entry No. | Specifies the entry number of the related item ledger entry. |
| Value Entry No. | Entry No. | Specifies the entry number of the value entry. |
| Value Entry Type | Entry Type | Specifies the type of value entry. |
| Document No. | Document No. | Specifies the document number of the value entry. |
| Document Type | Document Type | Specifies the type of document that created the value entry. |
| Item Ledger Entry Type | Entry Type | Specifies the entry type of the related item ledger entry. |
| Adjustment | Adjustment | Specifies whether the value entry is an adjustment. |
| Capacity Ledger Entry No. | Capacity Ledger Entry No. | Specifies the related capacity ledger entry number. |

### Dimension tables

The star schema model uses dimension tables and you can filter and group data.

- [Documents](#documents)
- [G/L Accounts](#gl-accounts)
- [Item](#item)
- [Item Category](#item-category)
- [Location](#location)
- [Project](#project)
- [Purchase Budget Name](#purchase-budget-name)
- [Purchaser](#purchaser)
- [Reason Codes](#reason-codes)
- [Resources](#resources)
- [Type](#type)
- [Vendor](#vendor)

### Documents

The app builds this table in the semantic model from the following tables:

- Purchase Credit Lines
- Purchase Invoice Lines
- Purchase Lines
- Purchase Value Entries

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Document No. | Document No. | Specifies the document number from the source purchase table. |
| Document Type | Document Type | Specifies the document type from the source purchase table. |
| Source Table | - | Specifies the semantic model table that contributed the document. |

### G/L Accounts

The app uses data from the following table:

- G/L Account

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| G/L Account No. | No. | Specifies the number of the general ledger account. |
| G/L Account Name | Name | Specifies the name of the general ledger account. |
| G/L Account Type | Account Type | Specifies the purpose of the account, such as Posting, Heading, Total, Begin-Total, or End-Total. |
| G/L Account Income/Balance | Income/Balance | Specifies whether the account is an income statement account or a balance sheet account. |
| G/L Account No. and Name | - | Specifies a combination of the general ledger account number and name in Power BI. |

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
| Item Unit Cost (LCY) | Unit Cost | Specifies the unit cost of the item in the local currency. |
| Item Category Description | Description | Specifies the description of the item category. |

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
| Location Code | Code | Specifies the code for the location. |
| Location Name | Name | Specifies the name of the location. |
| Location Adjustment Bin Code | - | Specifies a location-specific adjustment bin code in Power BI. |

### Project

The app uses data from the following table:

- Project

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Project No. | No. | Specifies the number of the project. |
| Project Description | Description | Specifies a short description of the project. |
| Project Bill to Customer No. | Bill-to Customer No. | Specifies the customer that the project is billed to. |
| Project Creation Date | Creation Date | Specifies the date when the project was created. |
| Project Starting Date | Starting Date | Specifies the date when the project starts. |
| Project Ending Date | Ending Date | Specifies the date when the project is expected to be completed. |
| Project Status | Status | Specifies the current status of the project. |
| Project Posting Group | Project Posting Group | Specifies the posting group that links project transactions to the appropriate general ledger accounts. |
| Project Blocked | Blocked | Specifies whether the project is blocked from posting. |
| Project Project Manager | Project Manager | Specifies the person who's assigned to manage the project. |
| Project Complete | Complete | Specifies whether the project is complete. |
| Project No. & Description | - | Specifies a combination of project number and description in Power BI. |

### Purchase Budget Name

The app uses data from the following table:

- Item Budget Name

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Purchase Budget Name | Name | Specifies the name of the purchase budget. |
| Purchase Budget Description | Description | Specifies the description of the purchase budget. |

### Purchaser

The app uses data from the following table:

- Salesperson/Purchaser

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Purchaser Code | Code | Specifies the code for the purchaser. |
| Purchaser Name | Name | Specifies the name of the purchaser. |

### Reason codes

The app uses data from the following table:

- Return Reason

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Return Reason Code | Code | Specifies the return reason code. |
| Return Reason Description | Description | Specifies the description of the return reason. |

### Resources

The app uses data from the following table:

- Resource

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Resource No. | No. | Specifies the number of the resource. |
| Resource Name | Name | Specifies the name of the resource. |
| Resource Base Unit of Measure | Base Unit of Measure | Specifies the base unit used to measure the resource. |
| Resource Unit Cost | Unit Cost | Specifies the cost of one unit of the resource. |
| Resource Unit Price | Unit Price | Specifies the price of one unit of the resource. |
| Resource No. and Name | - | Specifies a combination of resource number and name in Power BI. |

### Type

The app builds this table in the semantic model from the following tables:

- Item
- Resource
- G/L Account

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Type | - | Specifies the type of the object, either item, resource, or general ledger account. |
| Type Key | - | Specifies a concatenated value generated by combining the No. and Type columns. |
| No. | No. or Account No. | Specifies the code of the item, resource, or general ledger account. |

### Vendor

The app uses data from the following table:

- Vendor

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Vendor No. & Name | - | Specifies a combination of vendor number and vendor name in Power BI. |
| Vendor No. | No. | Specifies the number of the vendor. |
| Vendor Name | Name | Specifies the name of the vendor. |
| Vendor Address | Address | Specifies the street address of the vendor. |
| Vendor Address 2 | Address 2 | Specifies additional address information. |
| Vendor City | City | Specifies the city of the vendor. |
| Vendor Post Code | Post Code | Specifies the postal code. |
| Vendor State | County | Specifies the state, province, or county as part of the address. |
| Vendor Country/Region Code | Country/Region Code | Specifies the country/region of the address. |
| Vendor Posting Group | Vendor Posting Group | Specifies the vendor posting group. |

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Related information

[Purchases KPI overview](purchases-powerbi-kpis.md)  
[Power BI purchasing app](purchases-powerbi-app.md)  
[Use Power BI with Business Central](admin-powerbi.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
