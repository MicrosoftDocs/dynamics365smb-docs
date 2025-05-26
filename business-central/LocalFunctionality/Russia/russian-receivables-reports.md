---
title: Receivables reports in Russia
description: Russian enhancements include receivables reports.
author: DianaMalina


ms.topic: article
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Russian Receivables Reports

The receivables report feature enables you to view the customer general ledger turnover for finance entries of general ledger accounts with the source type Customer. The following reports are also provided:

- Customer General Ledger Turnover (report 12450)
- Customer Accounting Card (report 12441)
- Customer Turnover (report 12439)
- Customer Posting Group Turnover (report 12440)
- Customer Entries Analysis (report 12442)
- Customer Reconciliation Act (report 14910)

## Customer General Ledger Turnover Report (Report 12450)

The **Customer General Ledger Turnover** report is used to analyze the turnover and to analyze customer account balances. It is usually printed monthly, but it can be printed for any given period.

The **Options** FastTab contains the fields listed in the following table.

| Field                             | Description                                                  |
| --------------------------------- | ------------------------------------------------------------ |
| **Rounding Precision**            | Select this field to choose the required rounding precision: 0.001, 0.01, 1, or 1000. |
| **Replace zero values by blanks** | Select this field to replace zero values with blanks during printing. |
| **Skip zero lines**               | Select this field to exclude lines with zero values.         |
| **Print Agreements**              | if it is selected, all amounts in reports will be calculated and shown in the section of agreements. |

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

It is printed monthly and on the date of inventory, but can be printed for any given period.

The following procedure shows how to access the **Customer Accounting Card** report.

1. Choose the **Financial Management** action, choose the **Receivables** action, and then choose the **Turnover** action.
2. Choose the **Customer G/L Turnover** action, choose the **Print** action, and then choose the **Customer Accounting Card** action.

The **Customer** FastTab of the request page contains the same fields as the **Customer** FastTab of the Customer General Ledger Turnover report. On the **Options** FastTab, you can select the **New page per Customer** field to print the information for each customer on a separate sheet.

## Customer Turnover Report (Report 12439)

The **Customer Turnover** report is used to print the data about a customer's entries for a specific period. It can also be created for customers separately for agreements. The printed data contains the following information:

- Number
- Name
- Starting balance (debit or credit at beginning of the period)
- Net change (debit or credit)
- Ending balance (debit or credit at end of the period)

To access the **Customer Turnover** report

- Choose the **Financial Management** action, choose the **Receivables** action, choose the **Reports** action, and then choose the **Customer Turnover** action.

The **Customer** FastTab of the request page contains the same fields as the **Customer** FastTab of the **Customer General Ledger Turnover** report. 

The **Options** FastTab contains the fields listed in the following table.

| Field                                      | Description                                                  |
| ------------------------------------------ | ------------------------------------------------------------ |
| **Rounding Precision**                     | Select this field to choose the required rounding precision: 0.001, 0.01, 1, or 1000. |
| **Replace zero values by blanks**          | Select this field to replace zero values with blanks during printing. |
| **Skip accounts without net changes**      | Select this field to exclude lines without net changes within the period. |
| **Skip accounts with zero ending balance** | Select this field to exclude lines with zero ending balances at the end of the period. |
| **Skip zero lines**                        | Select this field to exclude lines with zero values.         |

## Customer Posting Group Turnover Report (Report 12440)

The **Customer Posting Group Turnover** report is used to print information on the customer's entries that are accumulated in the customer posting groups. The printed data contains the following information:

- Customer posting group code
- Customer posting group name
- Starting balance (debit or credit)
- Net change (debit or credit)
- Ending balance (debit or credit)

To access the **Customer Posting Group Turnover** report

- Choose the **Financial Management** action, choose the **Receivables** action, choose the **Reports** action, and then choose the **Customer Posting Group Turnover** action.

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

To access the **Customer Entries Analysis** report

- Choose the **Financial Management** action, choose the **Receivables** action, choose the **Reports** action, and then choose the **Customer Entries Analysis** action.

On the **Customer** FastTab of the request page, define the customer number or a range of numbers, depending on whether you want to print the report for one customer or for a range of customers. On the **Customer Ledger Entry** FastTab, you can enter a filter value for one document or for a range of documents.

On the **Options** FastTab, you can specify the format options listed in the following table.

| Parameter                 | Description                                                  |
| ------------------------- | ------------------------------------------------------------ |
| **Starting Date**         | Enter the start date of the period.                          |
| **Ending of period**      | Enter the end date of the period                             |
| **Report Currency**       | Enter currency that you want to use in the report. You can choose:   -   Local currency -   Transaction currency |
| **New Page For Customer** | Select this field to print the data for each customer on a separate page. |

## Customer - Reconciliation Act (Report 14910)

The **Customer – Reconciliation Act** report shows the payments or liabilities of the customer. It is used for the reconciliation of mutual payments of contractors.

To access the **Customer – Reconciliation Act** report

- Choose the **Financial Management** action, choose the **Receivables** action, choose the **Reports** action, and then choose the **Customer - Reconciliation Act** action.

The following levels of detail are possible:

- Full
- Partial
- None

### Full Detail

If Full is selected as the detail level, the report prints the following data for each document for the current and previous periods:

- Document number and numbers of documents connected with it
- The balance on each document (debit or credit)
- Document date
- Description

The report prints the following information on the right side of the window (customer's data) in case the **Print Contactor Data** check box is selected on the **Options** FastTab of the request page:

- Document amount
- Debit
- Credit

### Partial Detail

If Partial Detail is selected as the detail level, the report shows the balance on each document for the current and previous periods, but no connections to the invoices, credit notes, and payments.

### None

If None is selected as the detail level, the report shows, for each customer, the balance at the beginning of the period, net changes for the period, and the balance at the end of the period. It also shows the amount of the customer liabilities.

On the **Options** FastTab, you can specify the format options listed in the following table.

| Parameter                     | Description                                                  |
| ----------------------------- | ------------------------------------------------------------ |
| **Starting Date**             | Enter the start date of the period.                          |
| **Ending Date of the Period** | Enter the end date of the period.                            |
| **Report Currency**           | Enter the currency that you want to use in the report. You can choose any currency from the glossary of currencies. |
| **Detailed**                  | Select one of these values:   -   **Full** -   **Partial** -   **None** |

## Related information

[Russian Payables Reports](Russian-Payables-Reports.md)  
[Set Up Customer and Vendor Agreements](How-to-Set-Up-Customer-and-Vendor-Agreements.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
