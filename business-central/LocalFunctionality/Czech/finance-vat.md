---
title: VAT - Czech Local Functionality | Microsoft Docs
description: This section describes Czech local functionality for VAT.
author: ACMartinKunes

ms-service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: CZ, Czech, Finance, VAT
ms.date: 04/01/2020
ms.reviewer: v-pejano
ms.author: v-makune
---

# Finance - VAT

## VAT Date

The VAT date is important for tax documents according to §28 of VAT Law 235/2004. The VAT date can be different from the posting date or the document date. The VAT date is an important field for the VAT reporting.  

This feature focuses on improving the following:

### Setup of the VAT Date Feature

- Enabling VAT date usage in the system generally.
- Select the way the system will default the VAT date’s value in different areas (Posting Date or Document Date).
- Periods for reporting VAT and company accounting periods are often different. To allow users to seamlessly report and post VAT according to VAT periods, and to issue internal and other statutory reporting based on accounting periods, this VAT Date feature introduces VAT periods.
- Allow VAT Posting From/To – enter a date range in from/to fields to prevent mistakes of posting to closed accounting or VAT periods.

### Posting Sales, Purchase, and Service Transactions with VAT Date

To post transactions using a VAT date, the user must fill in the **VAT Date** field on the document headers and journal lines throughout the application.
After the posting of the VAT date, it becomes a part of the posted documents and G/L entries and VAT entries.

### Calculating and Posting VAT Settlement

The system filters VAT entries by the **VAT Date** field (instead of **Posting Date**) by selecting the VAT period and preparing a report showing which entries will be transferred to the Settlement account. Printouts also contains VAT date information.

### Reconciling VAT and G/L Entries

Users frequently reconcile amounts kept in VAT entries and VAT amounts posted to GL entries.
Amounts shown in new Net Change (VAT Date) columns on all the following pages will always be filtered by the **VAT Date** field:

- Chart of Accounts form
- G/L Balance form
- G/L Account Balance form

## VAT Statement

The VAT Statement report contains many improvements which enable the user to:

- Add Stat. Reporting Setup with general setup for VAT reporting.
- Add two new operation rows (Row Division and Row Multiplication) in the **Type** field.
- Add setup for VAT from advances.
- Filter the **VAT Entries** selection for the VAT statement line by the **EU Triangular Trade** field. This is required, as EU (European Union) triangular trade (middle person – 1 debtor) must be reported in separate rows.
- Print the VAT Statement report with a new option to round off calculated amounts in the VAT statement to the nearest whole value.
- Filter data based on VAT date using VAT periods.
- Filter data for the posted VAT statement of later date.
- More VAT statement types – Recapitulative, Corrective, Supplementary (by §43 part 1 of VAT Law 235/2004) – payer can submit a supplementary VAT statement.
- Export the VAT statement to an .xml file.
- Add comments and attachments to export to the tax authorities.

## Supplementary VAT Statement

According to §43 part 1 of VAT Law 235/2004, the payer can submit a supplementary VAT statement. In case the user wants to issue the **Supplementary VAT Statement** report, they must choose the **Supplementary** type of VAT statement when exporting the statement.
In the Calculate and Post VAT Settlement functionality, the posted document number is stored in closed VAT entries in the **VAT Settlement No.** field for further filtering in VAT statements and reports. This feature allows calculation and printing VAT statement for different VAT statements posted and submitted in one VAT period.

## VIES

The VIES report is used for sales declaration to tax authorities in EU (European Union) countries. According to §102 of VAT Law 235/2004, payers are obliged to submit VIES declaration („Souhrnné hlášení“). The VIES declaration has to be submitted to the tax authorities electronically.
The VIES functionality allows you to:

- Set up state reporting
- Select combinations of VAT business/product posting group (on the **VAT Posting Setup** page) to include in the VIES reporting
- Keep the VIES reporting history
- Input all information needed for electronic file submission
- Suggest Lines for VIES reporting
- Support corrective declarations
- Export data into file for electronic submission

## Unreliable Payer

The amendment of VAT Law 235/2004 (§106a) introduced the concept of *Unreliable Payer*. The treasury department is obliged to publish the names of unreliable payers.

This feature uses this service to obtain published information and indicate payer status on vendor cards and purchase documents.
The treasury department also publishes information about registered bank accounts of the payer (only these accounts are allowed for payments). Information about payer registered bank accounts is stored on the vendor bank account cards and used in cash management.

## VAT Exchange Rate
The exchange rate is located in documents, but Czech Republic requires the possibility to set different exchange rates for posting and VAT in sales and purchase documents. This feature adds the **VAT Currency Code** and **VAT Exchange Rate** fields in documents. Users can change the exchange rate for VAT before document posting.

## [VAT Control Report](vat-control-report.md)

[!INCLUDE[d365fin](../../includes/d365fin_md.md)] functionality has been extended by the VAT Control Report. VAT items are loaded by the VAT date or posting date (according to the general ledger setup) into the page for the selected period. To process the control report, you must set up VAT control report sections, tariff numbers, VAT statement, stat. reporting setup, and extend the VAT posting setup.  

## VAT Reports

To fulfil the requirements in legislation reporting and local reporting practices of Czech companies, this feature provides the following reports:

- Calc. and Post VAT Settlement – standard report adjusted
- Documentation for VAT
- VAT Document List
- VAT List on Sales Adv. Letter
- VAT List on Purch. Adv. Letter

## See Also

[Czech Local Functionality](czech-local-functionality.md)
