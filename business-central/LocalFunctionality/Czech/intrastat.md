---
title: Czech local functionality - Intrastat
description: Learn about local functionality for Intrastat, Intrastat Engine Setup, Intrastat Tables, and other features.
author: ACMartinKunes 
ms.author: makune
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
ms.topic: article
ms.date: 06/05/2025
ms.custom: bap-template
ms.search.keywords: Czech, Intrastat, Payables, Finance, CZ, Cash
---

# Intrastat in the Czech version

The standard Intrastat feature doesn't transfer all and only valid transactions into the Intrastat journal. The result is a lot of manual work to exclude and include excess and missing transactions, which often cause errors. According to the requirements of the Czech Republic, the standard Intrastat feature needs the following improvements:

- Particular options in the Intrastat engine need to be parameterized.
- Handling of supplementary measure units needs to be improved.
- Calculating Intrastat amount and statistical amounts must be improved.
- The **Get Intrastat Entries** batch needs to be improved.
- Export of Intrastat reports to .csv files according to local requirements.

This feature improves the data transferred into the Intrastat journal and prepares the environment for correct Intrastat reporting.

## Intrastat engine setup

Extra Intrastat engine general parameters setup allows you to:

- Set mandatory fields of Intrastat transactions in sales, purchase, and transfer transactions.
- Set where the particular parts of Intrastat data related to items should be taken from, either item or posted entry and which item attributes are mandatory in sales, purchase, and transfer transactions.
- Specify whether the system should ignore item charges related to sales, purchase, and transfer transactions. For example, not including them in Intrastat or statistical amounts.
- Define whether and how the statistical amount is calculated.
- Select Intrastat rounding type to set how Intrastat and statistical amounts are rounded.
- Set foreign currency exchange rates for Intrastat reporting.
- Set the object for the Intrastat report export.

### New setup tables

New setup tables are added for the following purposes:

- Statistic indications
- Specific movements
- Intrastat delivery groups

### More setup for Intrastat

More setup for Intrastat enables you to define the following settings:

- Set a country/region code for entry and exit points.
- Set Tariff number supplementary units of measure if you have to report Tariff numbers in supplementary units of measure.
- Set whether specific item charges must be included in Intrastat amount or Intrastat statistical value or both.
- Set Intrastat behavior for shipment methods. Select to include or exclude item charges for specific shipment methods and Intrastat delivery groups for reporting.
- Set an area value in a Location card.
- Set default values and enforce company policies for extra Intrastat data available on Customer and Vendor cards.
- Define and add Intrastat data that includes statistic indication and specific movement on the Item card.
- Create a special foreign currency exchange rate setup and object for the export setup for each Registration country/region.

## Post sales, purchase, or transfer transactions

To identify and enter attributes of sales transactions that are in Intrastat reporting, you need to follow these steps:

- Verify Intrastat data (Transaction Type, Specification and Transport Method, etc.) on the Foreign Trade tab. This data is transferred to the document header from the relevant Customer or Vendor card and can be manually edited.
- Intrastat Transaction field (noneditable) informs the user whether the particular transaction is qualified as Intrastat transaction.
- Identify the Physical Movement in the correction (Credit-Memo) documents using the Physical Transfer field.
- You can manually exclude an Intrastat Transaction from Intrastat reporting using the Intrastat Exclude field.
- Verify Intrastat Data (Tariff No., Statistic Indication, Country/Region of Origin and Net Weight) in the document lines. These were transferred to the line from the relevant Item card and can be manually edited.
- Assign Item Charge to the sales line and include/exclude its value to Intrastat Amount and Statistical Amount.
- During the posting, the system transfers all Intrastat relevant information to Item Ledger Entry.
- During the posting, the system displays an error if any mandatory Intrastat field in Stat. Reporting Setup form isn't filled in. This error prevents the user from posting the transaction.

## Prepare the Intrastat journal

The Intrastat journal contains the following new fields and functionalities:

- Shipment Method Code
- Statistic Indication
- Specific Movement
- Supplementary Units of Measure Calculation
- Declaration Numbering
- Declaration types for Statement Classification – Primary, Null, Replacing, Deleting
- Registration Country/Region entries filtering

The fastest way to prepare the Intrastat journal and make sure all the rules set in the previous steps are followed is by using the **Get Entries** batch job. During the execution of the Get Entries batch job, the following occurs:

- The system considers the Item and Project Ledger Entries created by transactions identified as Intrastat transactions.
- The system ignores sales and purchase Intrastat transactions with the EU-3 Party Trade flag.
- The system includes Intrastat transactions with entry and exit points in EU countries/regions.
- The system includes sales and purchase documents, such as credit memos that are posted with the **Correction** check box as inserted in the Intrastat journal. These documents are the same type as the documents they're correcting, but with the opposite sign for nonphysical transfer documents and the opposite type for documents marked as physical transfer.
- The system excludes the reversed Intrastat transactions (using Undo Receipt/Shipment) from reporting.
- The system ensures the item charges are (not) included, adjusted, and calculated in Intrastat Amount and Statistical Amount according to the user's settings in Stat. Reporting Setup, Item Charges, Shipment Methods, and Item Charge Assignments.
- The system ensures the use of the Supplementary units of measure while preparing the Intrastat journal lines.
- The system makes sure the correct data source is used for Tariff number, Net weight, and Country/Region of origin according to Stat. Reporting setup.

## Export Intrastat report to CSV format

Exporting Intrastat reports to .csv files according to local requirements (for INSTATDESK and INSTATONLINE applications) was added to the Intrastat journal.
Export use object for export based on setup in Stat. Reporting Setup or Registration Country/Region.

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Set Up Intrastat Reporting](../../finance-how-setup-report-intrastat.md)  
- [Finance](finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
