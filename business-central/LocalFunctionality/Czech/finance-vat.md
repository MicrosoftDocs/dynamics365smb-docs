---
title: VAT - Czech Local Functionality | Microsoft Docs
description: This section describes Czech local functionality for VAT.
author: ACMartinKunes

ms-service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: CZ, Czech, Finance, VAT
ms.date: 05/15/2019
ms.reviewer: v-pejano
ms.author: v-makune
---

# Finance - VAT

## VAT Date

The VAT Date is important for tax documents by §28 of VAT Law 235/2004. The VAT Date can be different from the posting date or the document date. The VAT Date is an important field for the VAT reporting.  

This feature focuses on improving the following:

### Setup of VAT Date Feature

- Enabling VAT Date usage in system generally.
- Select the way the system will default the VAT Date’s value in different areas (Posting Date or Document Date).
- Periods for reporting VAT and company accounting periods are often different. To allow users to seamlessly report and post VAT according to VAT periods, and to issue internal and other statutory reporting based on accounting periods, this VAT Date feature introduces VAT Periods.
- Allow VAT Posting From/To – enter a date range in from/to fields to prevent mistakes of posting to closed Accounting or VAT periods.

### Posting Sales, Purchase and Service Transactions with VAT Date

To post transactions using the VAT Date, the user needs to be able to enter VAT Dates in the document headers and Journal lines throughout the application.
After the posting of the VAT Date, it becomes a part of the posted documents and G/L Entries and VAT Entries.

### Calculating and Posting VAT Settlement

System filters VAT Entries use the VAT Date (instead of the Posting Date) by selecting VAT Period and prepares a report showing which entries will be transferred to the Settlement Account. Printout also contains VAT Date information.

### Reconciling VAT and G/L Entries

Users frequently reconcile amount kept in VAT Entries and VAT amounts posted to GL Entries.
Amounts shown in new Net Change (VAT Date) columns in all following forms will always be filtered out by VAT Date:

- Chart of Accounts form
- G/L Balance form
- G/L Account Balance form 

## VAT Statement

The VAT Statement contains many improvements which enable the user to:

- Add Stat. Reporting Setup with general setup for VAT reporting.
- Add two new operation rows (Row Division and Row Multiplication) in the Type field.
- Add setup for VAT from advances.
- Filter the VAT Entries selection for the VAT Statement line by the EU Triangular Trade field. This is required, as EU (European Union) triangular trade (middle person – 1 debtor) must be reported in separate rows.
- Print the VAT Statement report with a new option to round off calculated amounts in the VAT statement to the nearest whole value.
- Filter data based on VAT Date using VAT Periods.
- Filter data for the posted VAT Statement of later date.
- More VAT Statement Types – Recapitulative, Corrective, Supplementary (by §43 part 1 of VAT Law 235/2004) – payer can submit Supplementary VAT Statement (see further). 
- Export the VAT statement to .xml file.
- Add Comments and Attachments to export for Tax Office.

## Supplementary VAT Statement

By §43 part 1 of VAT Law 235/2004, payer can submit Supplementary VAT Statement. In case user wants to issue the Supplementary VAT Statement, it is necessary to choose Supplementary type of VAT Statement by exporting the Statement.
In the Calculate and post VAT Settlement functionality, the Posted Document Number is stored in closed VAT entries as VAT Settlement No. for further filtering in VAT Statement and reports. This feature allows calculation and printing VAT statement for different VAT statements posted and submitted in one VAT Period.

## VIES

The VIES report is used for sales declaration to tax authorities in EU (European Union) countries. By §102 of VAT Law 235/2004, payers are obliged to submit VIES declaration („Souhrnné hlášení“). The VIES declaration has to be submitted to the Tax Office electronically.
The VIES functionality allows to:

- Set up State Reporting 
- Select combinations of VAT Business/Product posting group (VAT Posting Setup) to include into the VIES Reporting
- Keep the VIES Reporting history
- Input all information needed for electronic file submission
- Suggest Lines for VIES Reporting
- Support corrective declarations
- Export data into file for electronic submission

## Unreliable Payer

The amendment of VAT Law 235/2004 (§106a) introduced the institute of Unreliable Payer. The Treasury Department is obliged to publish the names of Unreliable Payers. 
This feature uses this service to obtain published information and indicate payer status on Vendor card and purchase documents. 
The Treasury Department also publishes information about registered bank accounts of the payer (only these accounts are allowed for payments). Information about payer registered bank accounts is stored on the Vendor Bank Accounts and used in Cash Management.

## VAT Exchange Rate
The exchange rate is located in documents, but Czech Republic requires the possibility to set different exchange rates for posting and VAT in sales and purchase documents. This feature adds VAT Currency Code field and VAT Exchange Rate in documents. Users can change the exchange rate for VAT before document posting.

## [VAT Control Report](vat-control-report.md)

[!INCLUDE[d365fin](../../includes/d365fin_md.md)] functionality has been extended by the VAT Control Report. VAT items are loaded by the VAT Date or Posting Date (according to the general ledger setup) into the form for the selected period. To process the control report you have to setup VAT control report sections, tariff numbers, VAT statement, stat. reporting setup and extended the VAT posting setup.  

## VAT Reports

In order to achieve requirements in legislation reporting and local reporting practices of Czech companies, this feature provides the following reports:

- Calc. and Post VAT Settlement – standard report adjusted
- Documentation for VAT
- VAT Document List 
- VAT List on Sales Adv. Letter
- VAT List on Purch. Adv. Letter

## See Also

[Czech Local Functionality](czech-local-functionality.md)