---
title: Power BI Projects app semantic model
description: Learn about the project tables and fields in the Power BI Projects app semantic model for Business Central reporting and analysis.
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

# Power BI Projects app semantic model

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The semantic model in the Power BI Projects app is organized in a [Star Schema Model](/power-bi/guidance/star-schema#star-schema-overview).

The fact tables contain information about individual transactions, such as project ledger entries, project planning lines, and project-related purchases from [!INCLUDE [prod_short](includes/prod_short.md)].

The dimension tables provide more context and attributes to the transactional data, such as project, customer, and resource information.

## Fact tables

Fact tables store transactional data and support summarizations such as SUM, AVG, COUNT, and more. The Power BI Projects app includes several fact tables:

- [Project Ledger Entries](#project-ledger-entries)
- [Project Planning Lines](#project-planning-lines)
- [Purchases](#purchases)

### Project Ledger Entries

The app uses data from the following table:

- Project Ledger Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| No. & Description | - | Specifies a combination of the number and description of the project ledger entry in Power BI. |
| Task No. | Project Task No. | Specifies the number of the related project task. |
| Posting Date | Posting Date | Specifies the posting date of the project ledger entry. |
| Entry Type | Entry Type | Specifies the entry type of the project ledger entry, either usage or sale. |
| Type | Type | Specifies the type of account that the project ledger entry is posted to. |
| No. | No. | Specifies the number of the resource, item, or general ledger account posted on the entry. |
| Description | Description | Specifies the description of the project ledger entry. |
| Location | Location Code | Specifies the location code if an item is posted. |
| Unit of Measure Code | Unit of Measure Code | Specifies how each unit of the item or resource is measured, such as in pieces or hours. |
| Unit Cost (LCY) | Unit Cost (LCY) | Specifies the cost, in the local currency, of one unit on the entry. |
| Unit Price (LCY) | Unit Price (LCY) | Specifies the price, in the local currency, of one unit on the entry. |

### Project Planning Lines

The app uses data from the following table:

- Project Planning Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Task No. | Project Task No. | Specifies the number of the related project task. |
| Line No. | Line No. | Specifies the planning line's entry number. |
| Type | Type | Specifies the type of account that the planning line relates to. |
| Line Type | Line Type | Specifies the type of planning line. |
| No. | No. | Specifies the number of the resource, item, or general ledger account on the planning line. |
| Description | Description | Specifies the description of the resource, item, or general ledger account on the planning line. |
| Unit Cost (LCY) | Unit Cost (LCY) | Specifies the cost, in the local currency, of one unit on the planning line. |
| Unit Price (LCY) | Unit Price (LCY) | Specifies the price, in the local currency, of one unit on the planning line. |
| Planning Date | Planning Date | Specifies the date of the planning line. |

### Purchases

The app uses data from the following table:

- Purchase Line

Purchase lines are broken down into **Purchase Orders (Outstanding)** and **Purchase Orders (Received Not Invoiced)**. Use the **Source Type** field to filter on these sources.

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Source Type | - | Specifies the source of the record, either outstanding purchase orders or purchase orders received but not invoiced. |
| Document Type | Document Type | Specifies the type of the purchase document. |
| Line No. | Line No. | Specifies the line number of the purchase line. |
| Document No. | Document No. | Specifies the document number of the purchase line. |
| No. | No. | Specifies the number of the item, resource, or general ledger account on the purchase line. |
| Type | Type | Specifies the type of the purchase line. |
| Description | Description | Specifies a description of the purchase line. |
| Project No. | Project No. | Specifies the number of the related project. |
| Task No. | Project Task No. | Specifies the number of the related project task. |
| Project No. & Task No. | - | Specifies a combination of the project number and project task number in Power BI. |

## Dimension tables

The star schema model uses dimension tables and you can filter and group data.

- [Customer](#customer)
- [G/L Accounts](#gl-accounts)
- [Items](#items)
- [Project](#project)
- [Resources](#resources)
- [Tasks](#tasks)
- [Type](#type)

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

### Items

The app uses data from the following tables:

- Item
- Item Category

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Item No. | No. | Specifies the number of the item. |
| Item Description | Description | Specifies the description of the item. |
| Item Base Unit of Measure | Base Unit of Measure | Specifies the base unit used to measure the item. |
| Item Unit Cost (LCY) | Unit Cost | Specifies the unit cost of the item. |
| Item Inventory Posting Group | Inventory Posting Group | Specifies the inventory posting group of the item. |
| Item Category Code | Code | Specifies the code for the item category. |
| Item Category Description | Description | Specifies the description of the item category. |
| Item No. & Description | - | Specifies a combination of item number and description in Power BI. |

### Project

The app uses data from the following table:

- Project

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Project No. | No. | Specifies the number of the project. |
| Project Description | Description | Specifies a short description of the project. |
| Project Creation Date | Creation Date | Specifies the date when the project was created. |
| Project Starting Date | Starting Date | Specifies the date when the project starts. |
| Project Ending Date | Ending Date | Specifies the date when the project is expected to be completed. |
| Project Status | Status | Specifies the current status of the project. |
| Project Posting Group | Project Posting Group | Specifies the posting group that links project transactions to the appropriate general ledger accounts. |
| Project Blocked | Blocked | Specifies that the project is blocked from being posted in transactions. |
| Project Project Manager | Project Manager | Specifies the person who's assigned to manage the project. |
| Project Complete | Complete | Specifies that the current status of the project is complete. |
| Project No. & Description | - | Specifies a combination of project number and description in Power BI. |

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

### Tasks

The app uses data from the following table:

- Project Task

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Task Project No. | Project No. | Specifies the number of the related project. |
| Task No. | Project Task No. | Specifies the number of the project task. |
| Task Description | Description | Specifies a description of the project task. |
| Task Project No. & Task No. | - | Specifies a combination of project number and project task number in Power BI. |
| Task Project Task & Description | - | Specifies a combination of project task number and description in Power BI. |
| Project Task Starting Date | Start Date | Specifies the start date of the project task. |
| Project Task Ending Date | End Date | Specifies the end date of the project task. |

### Type

The app builds this table in the semantic model from the following tables:

- Item
- Resource
- G/L Account

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| No. | No. or Account No. | Specifies the code of the item, resource, or general ledger account. |
| Type | - | Specifies the type of the object, either item, resource, or general ledger account. |
| Type Key | - | Specifies a concatenated value generated by combining the No. and Type columns. |

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Related information

[Projects KPI overview](projects-powerbi-kpis.md)  
[Power BI projects app](projects-powerbi-app.md)  
[Use Power BI with Business Central](admin-powerbi.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
