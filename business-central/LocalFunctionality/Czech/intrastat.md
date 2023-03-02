---
title: Czech local functionality - Intrastat
description: This article describes local functionality for Intrastat, Intrastat Engine Setup, Intrastat Tables, and additional features.
author: ACMartinKunes 
ms.author: v-makune
ms.reviewer: v-pejano
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 03/02/2023
ms.custom: bap-template
ms.search.keywords: Czech, Intrastat, Payables, Finance, CZ, Cash
---

# Intrastat in the Czech version

The standard Intrastat feature doesn't transfer all and only valid transactions into Intrastat journal. This results into a lot of manual work necessary to exclude and include excess and missing transactions, which often results in errors. According to the requirements of the Czech Republic, the following improvements are needed for the Intrastat feature:

- Particular options in the Intrastat engine need to be parameterized
- Handling of supplementary measure units needs to be improved
- Calculating Intrastat amount and statistical amounts must be improved
- The **Get Intrastat Entries** batch needs to be improved
- Export of Intrastat reports to .csv files according to local requirements

This feature adds improvement of data transferred into Intrastat journal and prepares the environment for correct Intrastat reporting.

## Intrastat engine setup

Additional Intrastat engine general parameters setup allows you to:

- Set mandatory fields of Intrastat transactions in sales, purchase, and transfer transactions.
- Set where the particular parts on Intrastat data related to items should be taken from, either item or posted entry and which item attributes will be mandatory in sales, purchase, and transfer transactions.
- Specify whether item charges related to sales, purchase, and transfer transactions will be ignored by the system. For example, not including them in Intrastat or statistical amounts.
- Define whether and how the statistical amount is calculated.
- Select Intrastat rounding type to set how Intrastat and statistical amounts are rounded.
- Set foreign currency exchange rates for Intrastat reporting.
- Set the object for the Intrastat report export.

### New setup tables 

New setup tables have been added for the following:

- Statistic indications
- Specific movements
- Intrastat delivery groups

### Additional setup for Intrastat 

Additional setup for Intrastat enables the following:

- Set a country/region code for entry and exit points.
- Set Tariff number supplementary units of measure if Tariff numbers have to be reported in supplementary units of measure.
- Set whether specific item charges must be included in Intrastat amount or Intrastat statistical value or both.
- Set Intrastat behavior for shipment methods. Select to include or exclude item charges for specific shipment methods and Intrastat delivery groups for reporting.
- Set an area value in a Location card.
- Set default values and enforce company policies following additional Intrastat data available on Customer and Vendor cards.
- Define on the Item card additional Intrastat data including statistic indication and specific movement.
- Create a special foreign currency exchange rate setup and object for the export setup for each Registration country.

## Posting sales, purchase, or transfer transactions

To identify and enter attributes of sales transaction that will be used in Intrastat reporting user, follows these steps:

- User verifies Intrastat data (Transaction Type, Specification and Transport Method, etc.) on the Foreign Trade tab. These were transferred to the document header from the relevant Customer or Vendor card and can be manually edited.
- Intrastat Transaction field (non-editable) informs the user whether the particular transaction is qualified as Intrastat transaction.
- Identification of the Physical Movement in the correction (Credit-Memo) documents using the Physical Transfer field.
- User can manually exclude an Intrastat Transaction from Intrastat reporting using the Intrastat Exclude field.
- User verifies Intrastat Data (Tariff No., Statistic Indication, Country/Region of Origin and Net Weight) in the document lines. These were transferred to the line from the relevant Item card and can be manually edited.
- User assigns Item Charge to the sales line and includes/excludes its value to Intrastat Amount and Statistical Amount.
- During the posting, system transfers all Intrastat relevant information to Item Ledger Entry.
- During the posting, system displays an error if any Intrastat field set as mandatory in Stat. Reporting Setup form is not filled in. This will prevent the user from posting the transaction.

## Preparing the Intrastat journal

The Intrastat journal contains the following new fields and functionalities:

- Shipment Method Code
- Statistic Indication
- Specific Movement
- Supplementary Units of Measure Calculation
- Declaration Numbering
- Declaration types for Statement Classification – Primary, Null, Replacing, Deleting
- Registration Country entries filtering

The fastest way to prepare the Intrastat journal and make sure all the rules set in the previous steps are followed is by using the **Get Entries** batch job. During the execution of the Get Entries batch job, the following occurs:

- The system considers the Item and Job ledger entries created by transaction identified as Intrastat transactions.
- The system ignores sales and purchase Intrastat transactions with the EU-3 Party Trade flag.
- The system includes Intrastat transactions with entry and exit points in EU countries.
- The system includes sales and purchase documents, such as credit memos that are posted with the **Correction** check box as inserted in the Intrastat journal. These documents are the same type as the documents they are correcting, but with the opposite sign for non-physical transfer documents and with the opposite type for documents marked as physical transfer.
- The system ensures the reversed Intrastat transactions (using Undo Receipt/Shipment) are excluded from reporting.
- The system ensures the item charges are (not) included, adjusted, and calculated in Intrastat Amount and Statistical Amount according to the user's setup in Stat. Reporting Setup, Item Charges, Shipment Methods, and Item Charge Assignments.
- The system ensures the Supplementary units of measure are used while preparing Intrastat journal lines.
- The system makes sure the correct data source is used for Tariff number, Net weight, and Country/Region of origin according to Stat. reporting setup.

## Intrastat report export to CSV format

Exporting Intrastat reports to .csv files according to local requirements (for INSTATDESK and INSTATONLINE applications) was added to the Intrastat journal.
Export use object for export based on setup in Stat. Reporting Setup or Registration Country.

## See also

[Czech Local Functionality](czech-local-functionality.md)  
[Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  
[Finance](finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
