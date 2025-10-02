---
title: Power BI Sales app semantic model
description: Get an overview of all tables and fields in the Sales App Semantic Model.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: reporting
ms.search.form: 36998, 36999, 37000, 37001, 37002, 37003, 37004, 37005, 37006, 37007, 37008, 37066, 37100, 37101, 37102, 37103, 37104, 37105, 37109, 37119
ms.date: 05/20/2025
ms.service: dynamics-365-business-central
---

# Power BI Sales app semantic model

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The semantic model in the Power BI Sales app is organized in a [Star Schema Model](/power-bi/guidance/star-schema#star-schema-overview).

The fact tables contains information about individual transactions from sources such as sales orders, posted sales invoices, and posted credit memos from [!INCLUDE [prod_short](includes/prod_short.md)].

The dimension tables provide more context and attributes to the transactional data, such as customer and product information.

## Fact tables

Fact tables store transactional data and support summarizations such as SUM, AVG, COUNT, and more. There are three fact tables in the Power BI Sales app:

- [Opportunity Entries](#opportunity-entries)
- [Sales Budget](#sales-budget)
- [Project Ledger Entries](#project-ledger-entries)
- [Sales Credit Lines](#sales-credit-lines)
- [Sales Invoice Lines](#sales-invoice-lines)
- [Sales Lines](#sales-lines)
- [Sales Value Entries](#sales-value-entries)

### Opportunity entries

Data from the following table is used:

- Opportunity Entries

#### Table definition

| Power BI Field Name | Business Central Field Name | Description |
| ------ | -------------- | ---------- |
| Action Taken | Action Taken | Specifies what happened when the opportunity entry was last updated. |
| Active | Active | Specifies that the opportunity entry is active. |
| Date of Change | Date of Change | Specifies the date when the opportunity entry was last changed. |
| Estimated Close Date | Estimated Close Date | Specifies the estimated date when the opportunity entry will close. |
| Opportunity Entry No. | Entry No. | Specifies the opportunity entry's number. |
| Opportunity No. | Opportunity No. | Specifies the opportunity's number. |

### Project Ledger Entries

The app uses data from the following tables:

- Project Ledger Entries

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Description | Description | Specifies the description of the project ledger entry. |
| Project Ledger Entry No. | Entry No. | Specifies the number of the entry, as assigned from the specified number series when the entry was created. |
| Reason Code | Reason Code | Specifies the reason code, a supplementary source code that enables you to trace the entry. |
| Unit Cost (LCY) | Unit Cost (LCY) | Specifies the cost, in LCY, of one unit of the item or resource on the line. |

### Sales Credit Lines

The app uses data from the following tables:

- Sales Cr. Memo Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Description | Description | Specifies the name of the item or general ledger account, or some descriptive text. |
| Sales Credit Line No. | Line No. | Specifies the line number of the posted sales credit memo line. |

### Sales Invoice Lines

The app uses data from the following tables:

- Sales Invoice Line

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Description | Description | Specifies the name of the item or general ledger account, or some descriptive text. |
| Sales Invoice Line No. | Line No. | Specifies the line number of the posted sales invoice line. |

### Sales Lines

The app uses data from the following tables:

- Sales Line
- Sales Header

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Campaign No. |Campaign No. | Specifies the campaign number the document is linked to. |
| Description | Description | Specifies a description of the entry of the product to be sold. |
| Document Date | Document Date | Specifies the date when the related document was created. |
| Due Date | Due Date | Specifies when the sales invoice must be paid. |
| Order Date | Order Date | Specifies the order date on the sales document |
| Planned Delivery Date | Planned Delivery Date | Specifies the planned delivery date on the sales line. |
| Planned Shipment Date | Planned Shipment Date | Specifies the planned shipment date on the sales line. |
| Posting Date | Posting Date | Specifies the date when the posting of the sales document will be recorded. |
| Promised Delivery Date | Promised Delivery Date | Specifies the promised delivery date on the sales document. |
| Quote No. | Quote No. | Specifies the number of the sales quote that the sales order was created from. |
| Requested Delivery Date | Requested Delivery Date | Specifies the date that the customer has asked for the order to be delivered. |
| Sales Line No. | Line No. | Specifies the line number of the sales line. |

### Sales Value Entries

The app uses data from the following tables:

- Value Entries
- Item Ledger Entries

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Entry Type | Entry Type | Specifies the type of value described in this entry. |
| Item Ledger Entry No. | Entry No. | Specifies the number of the entry, of the related item ledger entry. |
| Item Ledger Entry Type | Entry Type | From the related Item Ledger Entry, specifies which type of transaction that the entry is created from. |
| Value Entry No. | Entry No. | Specifies the number of the entry on the value entry table. |

### Sales

> [!NOTE]
> This fact table is deprecated in Business Central 2025 release wave 2 and is no longer available.

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

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Budget Name | Budget Name | Specifies the name of the budget. |
| Date |  Date | Specifies the date for the budget entry. |
| Entry No. |  Entry No. | The unique number of the specific budget entry. |

## Dimension tables

The star schema model uses dimension tables and allows you to filter and group.

- [Close Opportunity Code](#close-opportunity-code)
- [Contact](#contact)
- [Customer](#customer)
- [Documents](#documents)
- [G/L Accounts](#gl-accounts)
- [Item](#item)
- [Item Category](#item-category)
- [Location](#location)
- [Opportunities](#opportunities)
- [Project](#project)
- [Reason Code](#reason-codes)
- [Resources](#resources)
- [Sales Cycle Stage](#sales-cycle-stages)
- [Salesperson](#salesperson)
- [Type](#type)

### Close Opportunity Code

The app uses data from the following table:

- Close Opportunity Code

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Close Opportunity Code | Code | Specifies the code for closing the opportunity. |
| Close Opportunity Description |  Description | Specifies the description of the reason for closing the opportunity. |
| Close Opportunity Type |  Type | Specifies whether the opportunity was a success or failure. |

### Contact

The app uses data from the following table:

- Contact

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Contact Name | Name | Specifies the contact name. |
| Contact No. | No. | Specifies the number for the contact. |
| Contact No. and Name | - | Specifies a combination of contact number and contact name in Power BI. |
| Contact Type | Type | Specifies the contact type, either company or person. |
| Company Name | Company Name | Specifies the name of the company for the contact. |
| Company No. | Company No. | Specifies the number for the contact's company |
| Contact Address | Address | Specifies the address for the contact. |
| Contact Address 2 | Address 2 | Specifies the secondary address details for the contact. |
| Contact City | City | Specifies the city for the contact. |
| Contact Country/Region Code | Country/Region Code | Specifies the country/region the contact's address is in. |
| Contact County | County | Specifies the state for the contact. |
| Contact Post Code | Post Code | Specifies the postal code of the address. |

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

### Documents

The app uses data from the following tables:

- Sales Lines
- Value Entries
- Invoice Lines
- Sales Cr. Memo Lines
- Project Ledger Entries

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Document No. | Document No. | Specifies the document number from the related fact table. |
| Document Type | Document Type | Specifies the type of document related to the fact. |
| Source Table | - | Specifies the source table where the document record originated from. |

### G/L Accounts

The app uses data from the following tables:

- G/L Account

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| G/L Account Income/Balance | Income/Balance | Specifies whether a general ledger account is an income statement account or a balance sheet account. |
| G/L Account Name | Name | Specifies the name of the general ledger account. |
| G/L Account No. | No. | Specifies the no. of the general ledger account. |
| G/L Account No. and Name | - | Specifies a concatenated name generated by combining the G/L Account No. and Name columns |
| G/L Account Type | Type | Specifies the purpose of the account such as Posting, Heading, Total, Begin-Total or End-Total. |

### Item

The app uses data from the following tables:

- Item

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Item No. | No. | Specifies the item number. |
| Item Name |  Description | Specifies the item description. |
| Item No. and Name |  - | Specifies a combination of item number and item name in Power BI. |
| Base Unit of Measure | Base Unit of Measure | Specifies the base unit of measure. |
| Unit Cost |  Unit Cost | Specifies the unit cost. |
| Inventory Posting Group | Inventory Posting Group | Specifies the inventory posting group. |

### Item Category

The app uses data from the following tables:

- Item Category

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Item Category Code | Code | Specifies the code for the item category. |
| Item Category Description |  Description | Specifies the description of the item category. |
| Item Category Code Hierarchy |  - | Specifies the related item category code levels, based on the parent category. |

### Location

The app uses data from the following table:

- Location

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Location Code | Code | Specifies the ID of the location. |
| Location Name |  Name | Specifies the name of the location. |

### Opportunities

The app uses data from the following table:

- Opportunity

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Opportunity No. | No. | Specifies the number of the opportunity. |
| Description | Description | Specifies the description of the opportunity. |
| Closed | Closed | Specifies that the opportunity is closed. |
| Opportunity Creation Date | Creation Date | Specifies the date the opportunity was created. |
| Sales Document No. | Sales Document No. | Specifies the number of the sales document assigned to the opportunity. |
| Sales Document Type | Sales Document Type | Specifies the type of the sales document assigned to the opportunity. |
| Status | Status | Specifies the status for the opportunity. |

### Project

The app uses data from the following table:

- Job

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Project Bill to Customer No. | Bill-to Customer No. | Specifies the number of the customer who pays for the project. |
| Project Blocked | Blocked | Specifies that the related Project is blocked from being posted in transactions. |
| Project Complete | Complete | Specifies if the current status of the project is complete. |
| Project Creation Date | Creation Date | Specifies the date on which the project was set up.' |
| Project Description | Description | Specifies a short description of the project. |
| Project Ending Date | Ending Date | Specifies the date on which the project is expected to be completed. |
| Project No. | No. | Specifies the number of Project record. |
| Project No. & Description | - | Specifies a concatenated name generated by combining the resource no. and name. | 
| Project Posting Group | Job Posting Group | Specifies the posting group that links transactions made for the project with the appropriate general ledger accounts according to the general posting setup. |
| Project Project Manager | Project Manager | Specifies the person who is assigned to manage the project. |
| Project Starting Date | Starting Date | Specifies the date on which the project actually starts. |
| Project Status | Status | Specifies a current status of the project. |

### Reason Codes

The app uses data from the following table:

- Return Reason

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Return Reason Code | Code | Specifies the code for the return reason. |
| Return Reason Description |  Description | Specifies the description for the return reason. |

### Resources

The app uses data from the following table:

- Resource

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Resource Base Unit of Measure | Base Unit of Measure | Specifies the base unit used to measure the resource. |
| Resource Name | Name | Specifies a description of the resource. |
| Resource No. | No. | Specifies the number of the resource record. |
| Resource No. and Name | - | Specifies a concatenated name generated by combining the resource no. and name |
| Resource Unit Cost | Unit Cost | Specifies the cost of one unit of resource. |
| Resource Unit Price | Unit Price | Specifies the price of one unit of the resource. |

### Sales Cycle Stages

The app uses data from the following table:

- Sales Cycle Stage

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Sales Cycle Code | Sales Cycle Code | Specifies the sales cycle code for the sales cycle stage. |
| Sales Cycle Stage | Stage | Specifies the number for the stage within the sales cycle. |
| Sales Cycle Description | Sales Cycle Description | Specifies the description for the sales cycle stage. |

### Salesperson

The app uses data from the following table:

- Salesperson/Purchaser

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Salesperson Code | Code | Specifies the ID of the salesperson. |
| Salesperson Name |  Name | Specifies the name of the salesperson. |

### Type

The app uses data from the following tables:

- Item
- Resource
- G/L Account

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| No. | No. or Account No. | Specifies the code of the Item/Resource/G/L Account. |
| Type |  - | Specifies the type of object being sold |
| Type Key | - | Specifies a concatenated value generated by combining the No and Type columns. |

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Related information

[Track your business KPIs with Power BI metrics](track-kpis-with-power-bi-metrics.md)  
[Ad-hoc analysis of sales data](ad-hoc-analysis-sales.md)  
[Built-in sales reports](sales-reports.md)  
[Sales analytics overview](sales-analytics-overview.md)  
[Sales overview](sales-manage-sales.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
