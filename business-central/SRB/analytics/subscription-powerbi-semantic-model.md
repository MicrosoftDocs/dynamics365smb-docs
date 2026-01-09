---
title: Power BI Subscription Billing app semantic model
description: Get an overview of all tables and fields in the Subscription Billing app semantic model.
author: vanessa-mi
ms.author: bholtorf
ms.reviewer: 
ms.topic: concept-article
ms.search.keywords: reporting
ms.date: 12/15/2025
ms.service: dynamics-365-business-central
---

# Power BI Subscription Billing app semantic model

The semantic model in the Power BI Subscription Billing app is organized in a [Star Schema Model](/power-bi/guidance/star-schema#star-schema-overview).

The fact tables contains information about individual transactions from sources such as customer subscription contracts and vendor subscription contracts.

The dimension tables provide more context and attributes to the transactional data, such as customer and product information.

## Fact tables

Fact tables store transactional data and support summarizations such as SUM, AVG, COUNT, and more. There are several fact tables in the Power BI Subscription Billing app:

- [Customer Contract Line](#customer-contract-line)
- [Customer Contract Changes](#customer-contract-changes)
- [Customer Contract Deferrals](#customer-contract-deferrals)
- [Customer Billing Forecast](#customer-billing-forecast)
- [Vendor Contract Line](#vendor-contract-line)
- [Vendor Contract Deferrals](#vendor-contract-deferrals)
- [Vendor Billing Forecast](#vendor-billing-forecast)

### Customer Contract Line

The app uses data from the following tables:

- Subscription Contract Analysis Entries

#### Table definition

| Power BI Field Name | Business Central Field Name | Description |
|------------------------------|------------------------------|-------------|
| Subscription Line No. | Entry No. | Unique identifier of the subscription line entry. |
| Template | Template | Specifies the code of the subscription package line template. |
| Customer Contract Line Desc. | Description | Specifies the description of the subscription line. |
| Subscription Start Date | Subscription Line Start Date | Specifies the date from which the subscription line is valid and will be invoiced. |
| Subscription End Date | Subscription Line End Date | Specifies the date up to which the subscription line is valid. |
| Next Billing Date | Next Billing Date | Specifies the date of the next billing possible. |
| Analysis Date | Analysis Date | Date used for analytical evaluations of subscription KPIs. |
| Billing Base Period | Billing Base Period | Specifies for which period the amount is valid. |
| Invoicing Item No. | Invoicing Item No. | Item number used for invoicing this subscription line. |
| Customer Contract Line No. | Subscription Contract Line No. | Specifies the line number in the subscription contract. |
| Notice Period | Notice Period | Specifies the notice period required before contract cancellation. |
| Initial Term | Initial Term | Specifies the minimum length of the initial subscription contract period. |
| Extension Term | Subsequent Term | Specifies the contract renewal term after the initial term expires. |
| Billing Rhythm | Billing Rhythm | Specifies how often billing occurs (e.g., monthly, yearly). |
| Cancellation Possible Until | Cancelation Possible Until | Specifies the last date cancellation is allowed before renewal. |
| Term Until | Term Until | Specifies the commitment end date for the subscription line. |
| Renewal Term | Renewal Term | Specifies the term by which the subscription line is renewed and the end of the subscription line is extended. |
| Dimension Set ID | Dimension Set ID | Specifies the value of the dimension set ID. |
| Remaining Term | - | Specifies the remaining number of months in the currenct subscription term. |
| Billing Rhythm Months | - | Specifies the billing rhythm in months. |
| Customer No. | Partner No. | Specifies the customer number. |
| Customer Contract No. | Subscription Contract No. | Specifies the number of the related customer subscription contract. |
| Customer Contract Line Key | - | Specifies a combination of customer subscription contract, customer subscription contract line and analysis date in order to create a unique identifier of each entry.  |
| Is Latest Version | - | Specifies if the line represents the latest state of the customer subscription contract line. |
| Is Usage Based Billing | Usage Based Billing | Specifies if the line is billed based on usage data. |
| Subscription Package Key | - | Specifies a combination of subscription and subscription package code in order to match subscription lines that originate from the same subscription package. |
| Source Type | Subscription Source Type | Specifies the type of the subscription (item, G/L account). |
| Source No. | Subscription Source No. | Specifies the item number or G/L account number of the subscription. |

### Customer Contract Changes

The app uses data from the following tables:

- Subscription Contract Analysis Entries

#### Table definition

| Power BI Field Name | Business Central Field Name | Description |
|------------------------------|------------------------------|-------------|
| Customer Contract Line Key | - | Specifies a combination of customer subscription contract, customer subscription contract line and analysis date in order to create a unique identifier of each entry. |
| Date |  | Specifies the period where the change in monthly recurring revenue occurred. |
| Change Type | - | Specifies the type of change in monthly recurring revenue (churn, downgrade, new, upgrade, UBB) |

### Customer Contract Deferrals

The app uses data from the following tables:

- Customer Subscription Contract Deferrals

#### Table definition

| Power BI Field Name | Business Central Field Name | Description |
|-------------------------------|-------------------------------|-------------|
| Contract No. | Subscription Contract No. | Specifies the number of the related customer subscription contract. |
| Document Type | Document Type | Specifies the document type used to create the deferral. |
| Document No. | Document No. | Specifies the document number used to create the deferral. |
| Is Released Key | Released | Specifies whether the deferral has been released. |
| Posting Date | Posting Date | Specifies the posting date of the deferral. |
| Document Line No. | Document Line No. | Specifies the number of the line in the related document. |
| Document Posting Date | Document Posting Date | Specifies the posting date of the document used to create the deferral. |
| Release Posting Date | Release Posting Date | Specifies the posting date on which the deferral was released. |
| G/L Entry No. | General Ledger Entry No. | Specifies the number of the G/L entry with which the deferral was released. |
| Discount | Discount | Specifies whether the Subscription Line is used as a basis for periodic invoicing or discounts. |
| Dimension Set ID | Dimension Set ID | Specifies the value of the Dimension Set ID. |
| Customer Contract Line Key | - | Specifies a combination of customer subscription contract, customer subscription contract line and analysis date in order to create a unique identifier of each entry. |
| Contract Line No. | Subscription Contract Line No. | Specifies the line number in the customer subscription contract. |

### Customer Billing Forecast

The app uses data from the following tables:

- Subscription Contract Analysis Entries

#### Table definition

| Power BI Field Name | Business Central Field Name | Description |
|------------------------------|------------------------------|-------------|
| Customer Contract Line Key | - | Specifies a combination of customer subscription contract, customer subscription contract line and analysis date in order to create a unique identifier of each entry. |
| Billing Date | - | Specifies the period of the forecast. |

### Vendor Contract Line

The app uses data from the following tables:

- Subscription Contract Analysis Entries

#### Table definition

| Power BI Field Name | Business Central Field Name | Description |
|------------------------------|------------------------------|-------------|
| Subscription Line No. | Entry No. | Unique identifier of the subscription line entry. |
| Template | Template | Specifies the code of the subscription package line template. |
| Vendor Contract Line Desc. | Description | Specifies the description of the subscription line. |
| Subscription Start Date | Subscription Line Start Date | Specifies the date from which the subscription line is valid and will be invoiced. |
| Subscription End Date | Subscription Line End Date | Specifies the date up to which the subscription line is valid. |
| Next Billing Date | Next Billing Date | Specifies the date of the next billing possible. |
| Analysis Date | Analysis Date | Date used for analytical evaluations of subscription KPIs. |
| Billing Base Period | Billing Base Period | Specifies for which period the amount is valid. |
| Invoicing Item No. | Invoicing Item No. | Item number used for invoicing this subscription line. |
| Vendor Contract Line No. | Subscription Contract Line No. | Specifies the line number in the subscription contract. |
| Notice Period | Notice Period | Specifies the notice period required before contract cancellation. |
| Initial Term | Initial Term | Specifies the minimum length of the initial subscription contract period. |
| Extension Term | Subsequent Term | Specifies the contract renewal term after the initial term expires. |
| Billing Rhythm | Billing Rhythm | Specifies how often billing occurs (e.g., monthly, yearly). |
| Cancellation Possible Until | Cancelation Possible Until | Specifies the last date cancellation is allowed before renewal. |
| Term Until | Term Until | Specifies the commitment end date for the subscription line. |
| Renewal Term | Renewal Term | Specifies the term by which the subscription line is renewed and the end of the subscription line is extended. |
| Dimension Set ID | Dimension Set ID | Specifies the value of the dimension set ID. |
| Remaining Term | - | Specifies the remaining number of months in the current subscription term. |
| Billing Rhythm Months | - | Specifies the billing rhythm in months. |
| Vendor No. | Partner No. | Specifies the vendor number. |
| Vendor Contract No. | Subscription Contract No. | Specifies the number of the related vendor subscription contract. |
| Vendor Contract Line Key | - | Specifies a combination of vendor subscription contract, vendor subscription contract line and analysis date in order to create a unique identifier of each entry. |
| Is Latest Version | - | Specifies if the line represents the latest state of the vendor subscription contract line. |
| Is Usage Based Billing | Usage Based Billing | Specifies if the line is billed based on usage data. |
| Subscription Package Key | - | Specifies a combination of subscription and subscription package code in order to match subscription lines that originate from the same subscription package. |
| Source Type | Subscription Source Type | Specifies the type of the subscription (item, G/L account). |
| Source No. | Subscription Source No. | Specifies the item number or G/L account number of the subscription. |

### Vendor Contract Deferrals

The app uses data from the following tables:

- Vendor Subscription Contract Deferrals

#### Table definition

| Power BI Field Name | Business Central Field Name | Description |
|-------------------------------|-------------------------------|-------------|
| Contract No. | Subscription Contract No. | Specifies the number of the related vendor subscription contract. |
| Document Type | Document Type | Specifies the document type used to create the deferral. |
| Document No. | Document No. | Specifies the document number used to create the deferral. |
| Is Released Key | Released | Specifies whether the deferral has been released. |
| Posting Date | Posting Date | Specifies the posting date of the deferral. |
| Document Line No. | Document Line No. | Specifies the number of the line in the related document. |
| Document Posting Date | Document Posting Date | Specifies the posting date of the document used to create the deferral. |
| Release Posting Date | Release Posting Date | Specifies the posting date on which the deferral was released. |
| G/L Entry No. | General Ledger Entry No. | Specifies the number of the G/L entry with which the deferral was released. |
| Discount | Discount | Specifies whether the Subscription Line is used as a basis for periodic invoicing or discounts. |
| Dimension Set ID | Dimension Set ID | Specifies the value of the Dimension Set ID. |
| Vendor Contract Line Key | - | Specifies a combination of vendor subscription contract, vendor subscription contract line and analysis date in order to create a unique identifier of each entry. |
| Contract Line No. | Subscription Contract Line No. | Specifies the line number in the vendor subscription contract. |

### Vendor Billing Forecast

The app uses data from the following tables:

- Subscription Contract Analysis Entries

#### Table definition

| Power BI Field Name | Business Central Field Name | Description |
|------------------------------|------------------------------|-------------|
| Vendor Contract Line Key | - | Specifies a combination of vendor subscription contract, vendor subscription contract line and analysis date in order to create a unique identifier of each entry. |
| Billing Date | - | Specifies the period of the forecast. |

## Dimension tables

The star schema model uses dimension tables and allows you to filter and group.

- [Customers](#customers)
- [Customer Contract](#customer-contract)
- [Subscription](#subscription)
- [Vendors](#vendors)
- [Vendor Contract](#vendor-contract)
- [Item](#item)
- [Salesperson](#salesperson)

### Customers

The app uses data from the following table:

- Customer

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Customer No. | No. | Specifies the customer number. |
| Customer Name |  Name | Specifies the customer name. |
| Customer No. & Name |  - | Specifies a combination of customer number and customer name in Power BI. |
| Address | Address | Specifies the address. |
| Address 2 |  Address 2 | Specifies the secondary address details. |
| City |  City | Specifies the city. |
| Post Code | Post Code | Specifies the postal code of the address. |
| State |  County | Specifies the state. |
| Country/Region Code |  Country/Region Code | Specifies the country/region the address is in. |
| Customer Posting Group | Customer Posting Group | Specifies the posting group. |
| Customer Price Group |  Customer Price Group | Specifies the price group. |
| Customer Disc. Group |  Customer Disc Group | Specifies the discount group. |

### Customer Contract

The app uses data from the following table:

- Customer Subscription Contract

#### Table definition

| Power BI field name | Business Central field name | Description |
|------------------------------|------------------------------|-------------|
| Customer Contract No. | No. | Specifies the customer subscription contract number from the related fact table. |
| Customer Contract Type | Contract Type | Specifies the contract type. |
| Customer Contract Description | Description | Specifies the description. |
| Customer Contract No. Desc. | - | Specifies a combination of customer subscription contract number and description in Power BI. |
| Salesperson Code | Salesperson Code | Specifies the salesperson responsible for the customer subscription contract. |

### Subscription

The app uses data from the following table:

- Subscription
- Subscription Line

#### Table definition

| Power BI field name | Business Central field name | Description |
|------------------------------|------------------------------|-------------|
| Subscription No. | No. | Specifies the subscription number from the related fact table. |
| Package Code | Subscription Package Code | Specifies the subscription package code. |
| Subscription Desc. | Description | Specifies the description. |
| Analysis Date | Analysis Date | Specifies the date of the latest subscription contract analysis entry from the related fact table. |
| Subscription Package Key | Subscription Package Key | Specifies a combination of subscription and subscription package code in order to match subscription lines that originate from the same subscription package. |
| Subscription No. Desc. | - | Specifies a combination of the subscription number and description in Power BI. |

### Vendors

The app uses data from the following table:

- Vendor

#### Table definition

| Power BI field name | Business Central field name | Description |
|----------------------|------------------------------|-------------|
| Vendor No. | No. | Specifies the vendor number. |
| Vendor Name | Name | Specifies the vendor name. |
| Vendor No. & Name | - | Specifies a combination of the vendor number and vendor name in Power BI. |
| Address | Address | Specifies the address. |
| Address 2 | Address 2 | Specifies the secondary address details. |
| City | City | Specifies the city. |
| Post Code | Post Code | Specifies the postal code of the address. |
| State | County | Specifies the state. |
| Country/Region Code | Country/Region Code | Specifies the country/region the address is in. |
| Vendor Posting Group | Vendor Posting Group | Specifies the posting group. |

### Vendor Contract

The app uses data from the following table:

- Vendor Subscription Contract

#### Table definition

| Power BI field name | Business Central field name | Description |
|------------------------------|------------------------------|-------------|
| Vendor Contract No. | No. | Specifies the customer subscription contract number from the related fact table. |
| Vendor Contract Type | Subscription Contract Type | Specifies the contract type. |
| Vendor Contract Description | Description | Specifies the description. |
| Vendor Contract No. Desc. | - | Specifies a combination of vendor subscription contract number and description in Power BI. |

### Item

The app uses data from the following table:

- Item
- Item Category

#### Table definition

| Power BI field name | Business Central field name | Description |
|------------------------------|------------------------------|-------------|
| Item No. | No. | Specifies the item number. |
| Item Name | Description | Specifies the item description. |
| Item No. & Description | - | Specifies a combination of the item number and description in Power BI. |
| Base Unit of Measure | Base Unit of Measure | Specifies the base unit of measure used for the item. |
| Item Category Code | Item Category Code | Specifies item category used for the item. |
| Item Category Description | Description | Specifies the item category description. |
| Inventory Posting Group | Inventory Posting Group | Specifies the inventory posting group. |

### Salesperson

The app uses data from the following table:

- Salesperson/Purchaser

#### Table definition

| Power BI field name | Business Central field name | Description |
|------------------------------|------------------------------|-------------|
| Salesperson Code | Code | Specifies the ID of the salesperson. |
| Salesperson Name | Name | Specifies the name of the salesperson. |

[!INCLUDE[powerbi-tip-track-kpis](../../includes/powerbi-tip-track-kpis.md)]

## Related information

[Track your business KPIs with Power BI metrics](../../track-kpis-with-power-bi-metrics.md)  
[Setting up the Subscription Billing Power BI app](subscription-powerbi-app-setup.md)  
[Subscription Billing controlling](../controlling.md)  
[Subscription Billing overview](../welcome.md)  
