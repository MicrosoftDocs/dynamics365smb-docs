---
title: Power BI Finance app semantic model
description: Learn about the finance tables and fields in the Power BI Finance app semantic model for Business Central reporting and analysis.
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

# Power BI Finance app semantic model

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The semantic model in the Power BI Finance app is organized in a [Star Schema Model](/power-bi/guidance/star-schema#star-schema-overview).

The fact tables contain information about individual transactions, such as general ledger entries, G/L budget entries, and customer and vendor ledger entries from [!INCLUDE [prod_short](includes/prod_short.md)].

The dimension tables provide more context and attributes to the transactional data, such as account, budget, customer, and vendor information.

## Fact tables

Fact tables store transactional data and support summarizations such as SUM, AVG, COUNT, and more. The Power BI Finance app includes several fact tables:

- [Customer Ledger Entries](#customer-ledger-entries)
- [G/L Budget Entries](#gl-budget-entries)
- [G/L Entries](#gl-entries)
- [Vendor Ledger Entries](#vendor-ledger-entries)

### Customer Ledger Entries

The app uses data from the following tables:

- Cust. Ledger Entry
- Detailed Cust. Ledg. Entry
- Sales Invoice Header

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| CLE Entry No. | Entry No. | Specifies the entry number of the customer ledger entry. |
| CLE Due Date | Due Date | Specifies the date when the customer ledger entry is due. |
| CLE Open | Open | Specifies whether the customer ledger entry is still open. |
| CLE Posting Date | Posting Date | Specifies the posting date of the customer ledger entry. |
| CLE Document Date | Document Date | Specifies the document date of the customer ledger entry. |
| DCLE Entry No. | Entry No. | Specifies the entry number of the detailed customer ledger entry. |
| Ledger Entry Amount | Ledger Entry Amount | Specifies whether the detailed customer ledger entry amount updates the customer ledger entry balance. |
| Entry Type | Entry Type | Specifies the type of detailed customer ledger entry, such as initial entry or application. |
| Document Type | Document Type | Specifies the document type of the detailed customer ledger entry. |
| Document No. | Document No. | Specifies the document number of the detailed customer ledger entry. |
| DCLE Initial Entry Due Date | Initial Entry Due Date | Specifies the due date of the initial customer ledger entry. |
| Customer No. | Customer No. | Specifies the number of the customer account. |
| Application No. | Application No. | Specifies the application number of the detailed customer ledger entry. |
| Applied Customer Ledger Entry No. | Applied Cust. Ledger Entry No. | Specifies the customer ledger entry number that was applied. |
| Sales Invoice Header Document No. | No. | Specifies the posted sales invoice number. |
| Payment Terms Code | Payment Terms Code | Specifies the payment terms that apply to the posted sales invoice. |
| Payment Discount Date | Pmt. Discount Date | Specifies the date when the payment discount is available. |
| CLE Closed At Date | Closed at Date | Specifies the date when the customer ledger entry was closed. |
| Late Payment | - | Specifies whether the payment was posted after the due date in Power BI. |
| Late Payment Invoice No. | - | Specifies the invoice number related to a late payment in Power BI. |

### G/L Budget Entries

The app uses data from the following table:

- G/L Budget Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Entry No. | Entry No. | Specifies the entry number of the G/L budget entry. |

### G/L Entries

The app uses data from the following tables:

- G/L Account
- G/L Entry
- PBI C. Income St. Source Code

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Posting Date | Posting Date | Specifies the posting date of the general ledger entry. |
| Closing Entry | - | Specifies whether the general ledger entry is treated as a closing entry in Power BI. |
| Source Code | Source Code | Specifies the source code that identifies where the general ledger entry was created. |
| Source Type | Source Type | Specifies the type of source that the general ledger entry is related to. |
| Source No. | Source No. | Specifies the number of the source that the general ledger entry is related to. |
| Entry No. | Entry No. | Specifies the entry number of the general ledger entry. |
| Description | Description | Specifies a description of the general ledger entry. |

### Vendor Ledger Entries

The app uses data from the following tables:

- Vendor Ledger Entry
- Detailed Vendor Ledg. Entry
- Purch. Inv. Header

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| VLE Entry No. | Entry No. | Specifies the entry number of the vendor ledger entry. |
| VLE Due Date | Due Date | Specifies the date when the vendor ledger entry is due. |
| VLE Open | Open | Specifies whether the vendor ledger entry is still open. |
| VLE Posting Date | Posting Date | Specifies the posting date of the vendor ledger entry. |
| VLE Document Date | Document Date | Specifies the document date of the vendor ledger entry. |
| DVLE Entry No. | Entry No. | Specifies the entry number of the detailed vendor ledger entry. |
| DVLE Ledger Entry Amount | Ledger Entry Amount | Specifies whether the detailed vendor ledger entry amount updates the vendor ledger entry balance. |
| Entry Type | Entry Type | Specifies the type of detailed vendor ledger entry, such as initial entry or application. |
| Document Type | Document Type | Specifies the document type of the detailed vendor ledger entry. |
| Document No. | Document No. | Specifies the document number of the detailed vendor ledger entry. |
| DVLE Initial Entry Due Date | Initial Entry Due Date | Specifies the due date of the initial vendor ledger entry. |
| Vendor No. | Vendor No. | Specifies the number of the vendor account. |
| Application No. | Application No. | Specifies the application number of the detailed vendor ledger entry. |
| Applied Vendor Ledger Entry No. | Applied Vend. Ledger Entry No. | Specifies the vendor ledger entry number that was applied. |
| PIH Document No. | No. | Specifies the posted purchase invoice number. |
| Payment Terms Code | Payment Terms Code | Specifies the payment terms that apply to the posted purchase invoice. |
| Payment Discount Date | Pmt. Discount Date | Specifies the date when the payment discount is available. |
| VLE Closed At Date | Closed at Date | Specifies the date when the vendor ledger entry was closed. |

## Dimension tables

The star schema model uses dimension tables and you can filter and group data.

- [Customers](#customers)
- [G/L Account](#gl-account)
- [G/L Account Category](#gl-account-category)
- [G/L Budget](#gl-budget)
- [Vendors](#vendors)

### Customers

The app uses data from the following table:

- Customer

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Customer No. | No. | Specifies the number of the customer. |
| Customer Name | Name | Specifies the name of the customer. |
| Customer Address | Address | Specifies the address of the customer. |
| Customer Address 2 | Address 2 | Specifies additional address information. |
| Customer City | City | Specifies the city of the customer. |
| Customer Post Code | Post Code | Specifies the postal code of the customer. |
| Customer State | County | Specifies the state, province, or county as part of the customer address. |
| Country/Region Code | Country/Region Code | Specifies the country/region of the customer address. |
| Customer Posting Group | Customer Posting Group | Specifies the customer's posting group. |
| Customer Price Group | Customer Price Group | Specifies the customer price group. |
| Customer Discount Group | Customer Disc. Group | Specifies the customer discount group. |
| Customer No. & Name | - | Specifies a combination of customer number and customer name in Power BI. |

### G/L Account

The app uses data from the following table:

- G/L Account

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| G/L Account No./Name | - | Specifies a combination of general ledger account number and name in Power BI. |
| G/L Account No. | No. | Specifies the number of the general ledger account. |
| G/L Account Name | Name | Specifies the name of the general ledger account. |
| Income/Balance | Income/Balance | Specifies whether the general ledger account is an income statement account or a balance sheet account. |

### G/L Account Category

The app uses data from the following table:

- G/L Account Category

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| G/L Acc. Category Description | Description | Specifies the description of the general ledger account category. |

### G/L Budget

The app uses data from the following table:

- G/L Budget Name

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| G/L Budget Name | Name | Specifies the name of the general ledger budget. |
| G/L Budget Description | Description | Specifies the description of the general ledger budget. |

### Vendors

The app uses data from the following table:

- Vendor

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Vendor No. | No. | Specifies the number of the vendor. |
| Vendor Name | Name | Specifies the name of the vendor. |
| Vendor Address | Address | Specifies the address of the vendor. |
| Vendor Address 2 | Address 2 | Specifies additional address information. |
| Vendor City | City | Specifies the city of the vendor. |
| Vendor Post Code | Post Code | Specifies the postal code of the vendor. |
| Vendor State | County | Specifies the state, province, or county as part of the vendor address. |
| Vendor Country/Region Code | Country/Region Code | Specifies the country/region of the vendor address. |
| Vendor Posting Group | Vendor Posting Group | Specifies the vendor's posting group. |
| Vendor No. & Name | - | Specifies a combination of vendor number and vendor name in Power BI. |

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Related information

[Finance KPI overview](finance-powerbi-kpis.md)  
[Power BI finance app](finance-powerbi-app.md)  
[Use Power BI with Business Central](admin-powerbi.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
