---
title: Receivables reports in Russia
description: Learn about receivables reports and related enhancements available for Russia in Business Central.
author: DianaMalina
ms.topic: article
ms.search.keywords: receivables reports, customer reports, turnover, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Russian receivables reports

The receivables report feature enables you to view the customer general ledger turnover for finance entries of general ledger accounts with the source type Customer. The following reports are also provided:

- Customer General Ledger Turnover (report 12450)
- Customer Accounting Card (report 12441)
- Customer Turnover (report 12439)
- Customer Posting Group Turnover (report 12440)
- Customer Entries Analysis (report 12442)
- Customer Reconciliation Act (report 14910)

## Customer General Ledger Turnover Report (Report 12450)

The **Customer General Ledger Turnover** report is used to analyze the turnover and to analyze customer account balances. It's printed monthly, but it can be printed for any given period.

The **Options** FastTab contains the fields listed in the following table.

| Field | Description |
|--|--|
| **Rounding Precision** | Select this field to choose the required rounding precision: 0.001, 0.01, 1, or 1000. |
| **Blank zero values** | Select this field to replace zero values with blanks during printing. |
| **Skip zero lines** | Select this field to exclude lines with zero values. |
| **Print Agreements** | if it's selected, all amounts in reports are calculated and shown in the section of agreements. |

## Customer Accounting Card Report (Report 12441)

The **Customer Accounting Card** report provides the following information for all of a customer's entries for a specific period:

- Starting balance
- Posting date
- Document number
- Description
- Net change debit
- Net change credit
- Document type
- Ending balance

It's printed monthly and on the date of inventory, but can be printed for any given period.

The following procedure shows how to access the **Customer Accounting Card** report.

1. Search for **Customer G/L Turnover**, and open the page.
1. Choose **Print** > **Accounting Card**.

The **Customer** FastTab includes customer, posting group, dimension, agreement, and date filters. On the **Options** FastTab, select **New page for Customer** to print each customer on a separate sheet.

## Customer Turnover Report (Report 12439)

The **Customer Turnover** report is used to print the data about a customer's entries for a specific period. It can also be created for customers separately for agreements. The printed data contains the following information:

- Number
- Name
- Starting balance (debit or credit at beginning of the period)
- Net change (debit or credit)
- Ending balance (debit or credit at end of the period)

To access the **Customer Turnover** report:

Search for **Customer Turnover**, and open the report.

The **Customer** FastTab of the request page contains the same fields as the **Customer** FastTab of the **Customer General Ledger Turnover** report.

The **Options** FastTab contains the fields listed in the following table.

| Field | Description |
|--|--|
| **Rounding Precision** | Select this field to choose the required rounding precision: 0.001, 0.01, 1, or 1000. |
| **Replace zero values by blanks** | Select this field to replace zero values with blanks during printing. |
| **Skip accounts without net changes** | Select this field to exclude lines without net changes within the period. |
| **Skip accounts with zero ending balance** | Select this field to exclude lines with zero ending balances at the end of the period. |
| **Skip zero lines** | Select this field to exclude lines with zero values. |

## Customer Posting Group Turnover Report (Report 12440)

The **Customer Posting Group Turnover** report is used to print information on the customer's entries that are accumulated in the customer posting groups. The printed data contains the following information:

- Customer posting group code
- Customer posting group name
- Starting balance (debit or credit)
- Net change (debit or credit)
- Ending balance (debit or credit)

To access the **Customer Posting Group Turnover** report:

Search for **Customer Posting Group Turnover**, and open the report.

On the **Options** FastTab, you can specify the same format options as on the **Options** FastTab of the **Customer General Ledger Turnover** report.

## Customer Entries Analysis (Report 12442)

The **Customer Entries Analysis** report shows the customer's liabilities at the beginning and at the end of the period, entry analysis, and invoice discharging. The printed data contains the following information

- Posting date
- Document number
- Document name
- Type (payment, invoice)
- Amount
- Amount closed
- Payment date

This report shows all the entries of the customer for a certain period. The analysis of the report enables you to determine the invoice and payment interdependence, shows closed entries, due invoices, partially discharged invoices, and customer prepayment amounts.

To access the **Customer Entries Analysis** report:

Search for **Customer Entries Analysis**, and open the report.

On the **Customer** FastTab of the request page, define the customer number or a range of numbers, depending on whether you want to print the report for one customer or for a range of customers. On the **Customer Ledger Entry** FastTab, you can enter a filter value for one document or for a range of documents.

On the **Options** FastTab, you can specify the format options listed in the following table.

| Parameter | Description |
|--|--|
| **Starting Date** | Enter the start date of the period. |
| **Ending of period** | Enter the end date of the period |
| **Report Currency** | Select **LCY** or **Entry Currency** for the report amounts. |
| **New Page For Customer** | Select this field to print the data for each customer on a separate page. |

## Customer - Reconciliation Act (Report 14910)

The **Customer – Reconciliation Act** report shows the payments or liabilities of the customer. It's used for the reconciliation of mutual payments of contractors.

To access the **Customer – Reconciliation Act** report:

Search for **Customer Reconciliations**, and open the report. Before you run it, configure **C/V Recon. Act Template Code** in **General Ledger Setup**. Choose **OK** to export the reconciliation to Excel.

The following levels of detail are possible:

- All
- Partial
- None

### Full detail

If **Show Details** is **All**, the report includes the following data for each document for the current and previous periods:

- Document number and numbers of documents connected with it
- The balance on each document (debit or credit)
- Document date
- Description

When **Print Vendor Data** is selected, the report also includes the counterparty's corresponding data:

- Document amount
- Debit
- Credit

### Partial detail

If **Show Details** is **Partial**, the report shows the balance on each document for the current and previous periods, but no connections to invoices, credit notes, and payments.

### None

If None is selected as the detail level, the report shows, for each customer, the balance at the beginning of the period, net changes for the period, and the balance at the end of the period. It also shows the amount of the customer liabilities.

On the **Options** FastTab, you can specify the format options listed in the following table.

| Parameter | Description |
|--|--|
| **Starting Date** | Enter the start date of the period. |
| **Ending Date** | Enter the end date of the period. |
| **Currency Code** | Enter the currency that you want to use in the report. |
| **Show Details** | Select **All**, **Partial**, or **None**. |

## Related information

- [Russian Payables Reports](russian-payables-reports.md)  
- [Set Up Customer and Vendor Agreements](how-to-set-up-customer-and-vendor-agreements.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
