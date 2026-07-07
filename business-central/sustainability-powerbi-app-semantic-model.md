---
title: Power BI Sustainability app semantic model
description: Learn how tables and fields in the Power BI Sustainability app semantic model map to Business Central data for emissions and workforce analysis.
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

# Power BI Sustainability app semantic model

[!INCLUDE[applies-to-2024w2](includes/applies-to-2024w2.md)]

The semantic model in the Power BI Sustainability app is organized in a [Star Schema Model](/power-bi/guidance/star-schema#star-schema-overview).

The fact tables contain information about individual transactions and targets, such as sustainability ledger entries, employee ledger entries, employee absences, employee qualifications, and sustainability goals from [!INCLUDE [prod_short](includes/prod_short.md)].

The dimension tables provide more context and attributes to the transactional data, such as sustainability accounts, employees, emission fees, responsibility centers, and country/region information.

## Fact tables

Fact tables store transactional data and support summarizations such as SUM, AVG, COUNT, and more. The Power BI Sustainability app includes several fact tables:

- [Employee Absences](#employee-absences)
- [Employee Ledger Entries](#employee-ledger-entries)
- [Employee Qualifications](#employee-qualifications)
- [Sustainability Goals](#sustainability-goals)
- [Sustainability Ledger Entries](#sustainability-ledger-entries)

### Employee absences

The app uses data from the following table:

- Employee Absence

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Entry No | Entry No. | Specifies the entry number assigned to the employee absence. |
| From Date | From Date | Specifies the first day of the employee absence. |
| To Date | To Date | Specifies the last day of the employee absence. |
| Cause of Absence | Cause of Absence Code | Specifies the cause of absence code that defines the absence type. |
| Description | Description | Specifies a description of the employee absence. |

### Employee Ledger Entries

The app uses data from the following table:

- Employee Ledger Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Entry No. | Entry No. | Specifies the entry number assigned to the employee ledger entry. |
| Document Type | Document Type | Specifies the document type of the employee ledger entry. |
| Document No. | Document No. | Specifies the document number of the employee ledger entry. |
| Description | Description | Specifies a description of the employee ledger entry. |

### Employee Qualifications

The app uses data from the following table:

- Employee Qualification

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Employee Qualification Codes | Qualification Code | Specifies the qualification code assigned to the employee. |

### Sustainability Goals

The app uses data from the following table:

- Sustainability Goal

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Score Card No. | Scorecard No. | Specifies the scorecard number of the sustainability goal. |
| No. | No. | Specifies the number of the sustainability goal. |
| Name | Name | Specifies the name of the sustainability goal. |
| Owner | Owner | Specifies the owner of the sustainability goal. |
| Target Value For CO2 | Target Value for CO2 | Specifies the target value for CO2 emissions. |
| Target Value For CH4 | Target Value for CH4 | Specifies the target value for CH4 emissions. |
| Target Value For N2O | Target Value for N2O | Specifies the target value for N2O emissions. |
| Target Value For Water Intensity | Target Value for Water Int. | Specifies the target value for water intensity. |
| Target Value For Waste Intensity | Target Value for Waste Int. | Specifies the target value for waste intensity. |
| Main Goal | Main Goal | Specifies whether the sustainability goal is the main goal. |
| Start Date | Start Date | Specifies the start date of the sustainability goal. |
| End Date | End Date | Specifies the end date of the sustainability goal. |
| Baseline Start Date | Baseline Start Date | Specifies the start date of the baseline period. |
| Baseline End Date | Baseline End Date | Specifies the end date of the baseline period. |

### Sustainability Ledger Entries

The app uses data from the following table:

- Sustainability Ledger Entry

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Entry No. | Entry No. | Specifies the entry number assigned to the sustainability ledger entry. |
| Description | Description | Specifies a description of the sustainability ledger entry. |
| Water Type | Water Type | Specifies the water type for the sustainability ledger entry. |
| Water/Waste Intensity Type | Water/Waste Intensity Type | Specifies the water or waste intensity type for the sustainability ledger entry. |
| Document Type | Document Type | Specifies the document type of the sustainability ledger entry. |

## Dimension tables

The star schema model uses dimension tables and you can filter and group data.

- [Country/Region](#countryregion)
- [Emission Fees](#emission-fees)
- [Employees](#employees)
- [Responsibility Centre](#responsibility-centre)
- [Sustainability Account Category](#sustainability-account-category)
- [Sustainability Accounts](#sustainability-accounts)
- [Sustainability Sub-Account Categories](#sustainability-sub-account-categories)

### Country/Region

The app uses data from the following table:

- Country/Region

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Country Region Code | Code | Specifies the country/region code. |
| Country Region Name | Name | Specifies the name of the country/region. |

### Emission fees

The app uses data from the following table:

- Emission Fee

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Emission Type | Emission Type | Specifies the type of emission that the fee applies to. |
| Scope Type | Scope Type | Specifies the emission scope that the fee applies to. |
| Starting Date | Starting Date | Specifies the starting date when the emission fee applies. |
| Ending Date | Ending Date | Specifies the ending date when the emission fee applies. |
| Country Region Code | Country/Region Code | Specifies the country/region code for the emission fee. |
| Responsibility Centre | Responsibility Center | Specifies the responsibility center for the emission fee. |
| Carbon Fee | Carbon Fee | Specifies the carbon fee amount. |
| Carbon Equivalent Factor | Carbon Equivalent Factor | Specifies the factor used to calculate carbon equivalent values. |

### Employees

The app uses data from the following table:

- Employee

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Employee No. | No. | Specifies the number of the employee. |
| Employee Full Name | - | Specifies a combination of the employee's first name and last name in Power BI. |
| Employee First Name | First Name | Specifies the first name of the employee. |
| Employee Last Name | Last Name | Specifies the last name of the employee. |
| Employee Gender | Gender | Specifies the gender of the employee. |
| Employee Union Code | Union Code | Specifies the union code assigned to the employee. |
| Employee Status | Status | Specifies the employment status of the employee. |
| Employee Cause of Inactivity | Cause of Inactivity Code | Specifies the cause of inactivity code assigned to the employee. |
| Employee Inactive Date | Inactive Date | Specifies the date when the employee became inactive. |
| Employee Grounds for Termination | Grounds for Term. Code | Specifies the grounds for termination code assigned to the employee. |
| Employee Date of Birth | Birth Date | Specifies the birth date of the employee. |
| Age | - | Specifies the employee's age calculated in Power BI. |
| Age Distribution | - | Specifies the employee's age group calculated in Power BI. |

### Responsibility Centre

The app uses data from the following table:

- Responsibility Center

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Responsibility Centre Code | Code | Specifies the responsibility center code. |
| Responsibility Centre Name | Name | Specifies the name of the responsibility center. |

### Sustainability Account Category

The app uses data from the following table:

- Sustain. Account Category

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Sustainability Account Category Description | Description | Specifies the description of the sustainability account category. |
| Sustainability Account Category Code | Code | Specifies the code of the sustainability account category. |
| Sustainability Account Category Emission Scope | Emission Scope | Specifies the emission scope of the sustainability account category. |

### Sustainability Accounts

The app uses data from the following table:

- Sustainability Account

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Sustainability Account No. | No. | Specifies the number of the sustainability account. |
| Sustainability Account Name | Name | Specifies the name of the sustainability account. |

### Sustainability Sub-Account Categories

The app uses data from the following table:

- Sustain. Account Subcategory

#### Table definition

| Power BI field name | Business Central field name | Description |
| ------ | -------------- | ---------- |
| Sub-Category Description | Description | Specifies the description of the sustainability account subcategory. |
| Renewable Energy | Renewable Energy | Specifies whether the sustainability account subcategory relates to renewable energy. |
| Sub-Category Code | Code | Specifies the code of the sustainability account subcategory. |

[!INCLUDE[powerbi-tip-track-kpis](includes/powerbi-tip-track-kpis.md)]

## Related information

[Power BI Sustainability app KPIs and measures](sustainability-powerbi-kpis.md)  
[Sustainability Power BI app](sustainability-powerbi-app.md)  
[Use Power BI with Business Central](admin-powerbi.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
