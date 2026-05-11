---
title: Audit Trail (report)
description: Review the audit trail of G/L registers and entries, including creation dates, user IDs, reversed entries, and transaction details for auditing and compliance.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: reporting
ms.search.form: Report_330_Primary
ms.date: 05/11/2026
ms.service: dynamics-365-business-central
ms.custom:
 - ai-gen-docs-bap
 - ai-seo-date: 05/04/2026
ai.usage: ai-assisted
---

# Audit Trail (report)

The **Audit Trail** report provides a detailed register and entry trace for auditing purposes. It includes information about the creation of G/L registers, such as creation date, time, and user ID, as well as details about each G/L entry within the registers. This report is useful for tracking changes, verifying transactions, and ensuring compliance with accounting standards. It also highlights reversed entries and their corresponding details to maintain transparency in financial records.

For each G/L register, the report shows:

* Register number
* Creation date and time
* User ID
* Source code
* Journal batch name
* Entry range (from and to entry numbers)

For each G/L entry within a register, the report shows:

* Posting date
* Document type and number
* G/L account number and name
* Description
* Debit and credit amounts
* Whether the entry is reversed, and the reversed-by entry number

## Use cases

[!INCLUDE [report-330-scenario](../includes/report-330-scenario-include.md)]

<!-- 
Prompt

Below is a report in an ERP system. Provide 3-4 use cases for different personas working with core finance.
Format like this:    
  
As a <persona>, use the report to    
* use case 1  
* use case 2    

Do not capitalize the persona names. 
Do not start lines with "Use the data to"

## Report name
Audit Trail

## Report description
Shows the G/L registers and their entries in detail, including creation date, time, user ID, reversed entries, and transaction details for auditing and compliance.

### What the report does
The *Audit Trail* report prints a list of G/L registers and their G/L entries. For each register, the report shows the creation date, time, user ID, source code, and the entry number range. For each entry within a register, the report shows the posting date, document type and number, G/L account number and name, debit and credit amounts, and whether the entry was reversed along with the reversed-by entry number.

### Use cases
Review the audit trail of G/L registers and their entries, including reversed transactions, to verify posting activity and support compliance with accounting standards.

Please include your data sources and URLs

-->

Controllers and finance managers can use the report to:

* Trace posting activity by reviewing who created entries and when, ensuring accountability across the finance team.
* Investigate unusual or unexpected transactions by examining register details, source codes, and entry values.
* Prepare for period-end closings by reviewing the completeness and accuracy of posted entries.

Auditors can use the report to:

* Verify the completeness and accuracy of general ledger entries as part of financial statement audits.
* Track reversed entries and their corresponding adjustments to ensure that corrections are properly documented.
* Identify the timing and origin of postings to detect anomalies, unauthorized entries, or potential fraud.

Financial accountants can use the report to:

* Review posted entries for a specific period to ensure all transactions are properly recorded.
* Cross-reference G/L entries with source documents by using the document type, number, and source code fields.
* Identify and investigate reversed entries to confirm that adjustments are justified and correctly applied.

Compliance officers can use the report to:

* Ensure that financial records meet regulatory requirements for audit trails and traceability.
* Verify that user access and posting activities align with internal controls and segregation of duties policies.
* Document financial posting activity for internal and external compliance reviews.

## Try the report

Try the report here: [Audit Trail](https://businesscentral.dynamics.com?report=330)

[!INCLUDE[ctrl-right-click-to-open-in-new-tab](../includes/ctrl-right-click-to-open-in-new-tab.md)]

## Related information

[Built-in key finance reports](../finance-reports.md)  
[Ad hoc analysis on finance data](../ad-hoc-analysis-finance.md)  
[Financial analytics overview](../bi.md)  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
