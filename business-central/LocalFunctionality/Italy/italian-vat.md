---
title: Italian VAT Reporting in Business Central
description: In the Italian version, companies can deduct VAT on goods or services purchased if they're used to generate business income.
author: brentholtorf
ms.topic: concept-article
ms.search.keywords: Italian VAT, VAT codes, VAT rates, VAT computation, non-deductible VAT, service tariffs, VAT transaction reports, Italian version
ms.search.form: 12100, 12104, 12105, 12111, 12112, 12113, 12122, 12126, 12127, 12133, 12135, 12151, 12158, 12187, 12189, 12198, 12199, 12202
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Italian VAT

Companies must pay VAT to the state for most purchased goods and services. VAT can be deducted if the goods or services purchased by a company are used in the production of its income.  

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can define periodic VAT reports on the **VAT Report** page. You can fill in the lines based on VAT entries, and then export the VAT report to the appropriate authorities.  

## VAT codes and rates

VAT codes and rates must be set up even though some transactions aren't subject to VAT rates. There are also many VAT-liable operations that are subject to a zero VAT rate by provision of the law.  

The related VAT code is printed for each invoice line. Invoices for VAT transaction entries that aren't subject to VAT rates must be recorded and printed with a note stating that VAT isn't owed.  

### Calculate VAT

VAT is computed for transactions to comply with the rules in effect on the day the transactions occur. Track the date on which a transaction legally occurs when you record the transaction.

### VAT dates

The date of issue is the document date, and the date of registration is the posting date. Different VAT processes use different dates:

- **VAT Report Suggest Lines** selects entries by **Posting Date** and applies the report-line threshold for that date.
- **Update VAT Transaction Data** uses **Operation Occurred Date** to find the applicable threshold.
- **Calculate and Post VAT Settlement** uses **Operation Occurred Date** to filter VAT entries for settlement.

Check the date fields for the process you're running rather than assuming that all VAT reports use the same date.

### Nondeductible VAT

VAT can't be deducted for some purchases because of:  

- The type of goods or services purchased – VAT is fully or partially non-deductible by provision of the law on goods like cars, mobile phones, food purchased at restaurants, and so on.  

- Partially deductible pro-rated VAT – VAT is pro-rated according to the ratio between sales operations for which VAT is owed, and all operations performed. VAT exceeding this ratio can't be deducted.  

## Service tariffs

The European Union (EU) has issued directives that change the VAT reporting for cross-border trade of goods and services in the EU.  

Service tariffs classify services for cross-border reporting. The service tariff specified on the **Foreign Trade** FastTab for a document can be changed on individual document lines.

For the current service-reporting workflow, use the **Service Declaration** page. Italian fields include **Statistics Period**, **Periodicity**, **Type**, and the fields for corrective declarations. Learn more in [Set up and use service declarations](../../finance-how-setup-use-service-declaration.md). For goods, use [Intrastat reporting](how-to-print-intrastat-reports-for-italy.md).

## VAT transaction reports

The **VAT Transactions Report** configuration creates report lines from sales and purchase VAT entries. Use the reporting requirements and thresholds that apply to the period you're reporting. This workflow is separate from VAT statements, periodic VAT payment communications, and Intrastat reporting.

**Suggest Lines** selects entries that have **Include in VAT Transac. Rep.** selected and fall within the report's posting-date range. It excludes entries whose **Unrealized VAT Entry No.** isn't zero. The following transaction identifiers are supported:

|**Transaction Type**|**Supported**|
|--------------------|-------------|  
|FE - Resident customer invoices|Yes|
|FR - Resident vendor invoices|Yes|
|NE - Resident customer credit memos|Yes|
|NR - Resident vendor credit memos|Yes|
|DF - Transactions without invoices (direct invoices) (customer)|No|  
|FN - Nonresident customer invoices|Yes|
|SE - Nonresident vendor invoices|Yes. The detailed export treats these as purchases of services. **Suggest Lines** doesn't distinguish goods from services for these lines.|

On sales and purchase document lines, the default value of **Include in VAT Transac. Rep.** depends on the document's **VAT Country/Region Code** and the inclusion setting in **VAT Posting Setup**. Domestic transactions can also be marked for inclusion. The default doesn't compare the line amount with a reporting threshold.

Sales and purchase posting marks prepayment deduction lines as excluded.

Entries are grouped by posting date, sales or purchase type, document type, and document number. The residency and the sign of the grouped amounts determine the transaction identifier. Report lines include the VAT base, VAT amount, and nondeductible or unrealized amounts recorded in the selected entries.

After generating the lines, **Suggest Lines** compares the absolute amount including VAT with **Threshold Amount Incl. VAT** for the line's posting date. Lines below the threshold are removed. An amount equal to the threshold is included.

The **Contract Payment Type** is set to **Contract** when the VAT entry has a **Contract No.** Otherwise, it's set to **Without Contract**. Review the suggested lines and their underlying VAT entries before export. Clear **Incl. in Report** to exclude a line.

To prepare the inclusion flags and thresholds, go to [Prepare for VAT Transactions Reports](how-to-prepare-for-vat-transactions-reports.md). To generate and review the report, go to [Create Electronic VAT Transactions Reports](how-to-create-electronic-vat-transactions-reports.md).

## Related information

- [Set Up VAT](../../finance-setup-vat.md)
- [Report VAT](../../finance-how-report-vat.md)
- [Prepare for VAT Transactions Reports](how-to-prepare-for-vat-transactions-reports.md)
- [Create Electronic VAT Transactions Reports](how-to-create-electronic-vat-transactions-reports.md)
- [Submit VAT Statements](how-to-submit-vat-statements.md)
- [Update VAT Transactions Data](how-to-update-vat-transactions-data.md)
- [Italy Local Functionality](italy-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
