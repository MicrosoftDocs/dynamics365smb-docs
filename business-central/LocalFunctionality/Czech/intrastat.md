---
title: Czech Local Functionality - Intrastat | Microsoft Docs
description: This section describes local functionality - Intrastat
author: ACMartinKunes

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: Czech, Intrastat, Payables, Finance, CZ, Cash
ms.date: 04/01/2020
ms.reviewer: v-pejano
ms.author: v-makune
---

# Intrastat

The standard Intrastat feature does not transfer all and only valid transactions into Intrastat journal. This results into a lot of manual work necessary to exclude/include the excess/missing transactions, often rendering a lot of errors. According to the requirements of the Czech Republic, the following improvements are needed for the Intrastat feature:

- Particular options in the Intrastat engine need to be parameterized
- Handling of supplementary measure units needs to be improved
- Calculation of Intrastat amount and statistical amounts must be improved
- The **Get Intrastat Entries** batch needs to be improved
- Exporting of Intrastat reports to .csv files according to local requirements

This feature adds improvement of data transferred into Intrastat journal and prepares the environment for correct Intrastat reporting.

## Intrastat Engine Setup

Additional Intrastat engine general parameters setup allows to:

- Set mandatory fields of Intrastat transactions in sales, purchase, and transfer transaction
- Set where the particular parts on Intrastat data related to items should be taken from (item or posted entry) and which item attributes will be mandatory in sales, purchase, and transfer transaction
- Set if any item charges related to sales, purchase, and transfer transaction will be ignored by the system (i.e. not including them in Intrastat or statistical amounts)
- Define if the statistical amount is calculated and calculation method for it
- Select Intrastat rounding type to set how Intrastat and statistical amounts will be rounded
- Set foreign currency exchange rate for Intrastat reporting
- Set object for Intrastat report export

### New Setup Tables Added for:

- Statistic Indications
- Specific Movements
- Intrastat Delivery Groups

### Additional Setup for Intrastat Enables:

- Set a country/region code for Entry/Exit Point
- Set Tariff Number Supplementary Units of Measure if Tariff numbers have to be reported in Supplementary Units of Measure
- Set if particular item charges have to be included in either Intrastat Amount or Intrastat Statistical Value or both
- Set Intrastat behavior for Shipment Methods – select if item charges should be included/excluded for particular Shipment Methods and Intrastat Delivery Group for reporting
- Set Area value in Location Card
- Set default values and enforce company policies following additional Intrastat data available on Customer and Vendor Cards
- Define on the Item Card additional Intrastat data – Statistic indication and Specific movement
- Make special foreign Currency Exchange Rate setup and object for export setup for each Registration Country

## Posting Sales, Purchase or Transfer Transaction

To identify and enter attributes of sales transaction that will be used in Intrastat reporting user, follows these steps:

- User verifies Intrastat data (Transaction Type, Specification and Transport Method, etc.) on the Foreign Trade tab. These were transferred to the document header from the relevant Customer or Vendor card and can be manually edited.
- Intrastat Transaction field (non-editable) informs the user whether the particular transaction is qualified as Intrastat transaction.
- Identification of the Physical Movement in the correction (Credit-Memo) documents using the Physical Transfer field.
- User can manually exclude an Intrastat Transaction from Intrastat reporting using the Intrastat Exclude field.
- User verifies Intrastat Data (Tariff No., Statistic Indication, Country/Region of Origin and Net Weight) in the document lines. These were transferred to the line from the relevant Item card and can be manually edited.
- User assigns Item Charge to the sales line and includes/excludes its value to Intrastat Amount and Statistical Amount.
- During the posting, system transfers all Intrastat relevant information to Item Ledger Entry.
- During the posting, system displays an error if any Intrastat field set as mandatory in Stat. Reporting Setup form is not filled in. This will prevent the user from posting the transaction.

## Preparing Intrastat Journal

The Intrastat Journal contains the following new fields and functionalities:

- Shipment Method Code
- Statistic Indication
- Specific Movement
- Supplementary Units of Measure Calculation
- Declaration Numbering
- Declaration types for Statement Classification – Primary, Null, Replacing, Deleting
- Registration Country entries filtering

The fastest way to prepare the Intrastat journal and make sure all the rules set in the previous steps are followed is by using the **Get Entries** batch job. During the execution of the Get Entries batch job, the system will take care of the following:

- System considers Item and Job Ledger Entries created by transaction identified as Intrastat transactions
- System ignores sales and purchase Intrastat transactions with the EU-3 Party Trade flag
- System makes sure to include Intrastat transactions with Entry/Exit Points in EU Country
- System makes sure to include sales and purchase documents (i.e. Credit Memos) posted with the **Correction** check box as inserted in the Intrastat journal with the same type as documents they are correcting, but with opposite sign for Non-physical Transfer documents and with the opposite type for documents marked as Physical Transfer
- System makes sure the reversed Intrastat transactions (i.e. using Undo Receipt/Shipment) are excluded from reporting (both revered and reversing Intrastat transactions)
- System makes sure the Item Charges are (not) included, adjusted and calculated in Intrastat Amount and Statistical Amount according to the user’s setup in Stat. Reporting Setup, Item Charges, Shipment Methods and Item Charge Assignments
- System makes sure the Supplementary Units of Measure are used while preparing Intrastat Journal lines
- System makes sure the correct data source is used for Tariff No., Net Weight and Country/Region of Origin according to Stat. Reporting Setup

## Intrastat Report Export to CSV Format

Export of Intrastat reports to .csv files according to local requirements (for INSTATDESK and INSTATONLINE applications) was added to Intrastat Journal.
Export use object for export based on setup in Stat. Reporting Setup or Registration Country.

## See Also
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](finance.md)
