---
title: Payment Times Reporting in the Australian version
description: Payment Times Reporting isn't directly available in the Australian version of Business Central, but this article guides you to the necessary data.
author: sorenfriisalexandersen
ms.topic: article
ms.search.keywords: payment times reporting, vendor ledger entries, Australian version
ms.date: 10/08/2026
ms.author: soalex
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
ai-usage: ai-assisted
---

# Payment Times Reporting in the Australian version

Businesses in Australia that are a constitutionally covered entity with an annual consolidated revenue of AUD 100,000,000 or more must report to the authorities how they pay their small business vendors. This revenue threshold is assessed at the consolidated group level. An entity that's controlled by a reporting entity doesn't report separately; instead, the controlling (head) entity submits a single consolidated report that covers all its controlled entities. Small businesses can register with the authorities so that reporting entities can look up their vendors to check if a given vendor qualifies as a small business vendor and report the relevant amounts. Learn more on the [Payment Times Reporting Scheme website](https://paymenttimes.gov.au/), which provides information about the reporting rules and registration. Use the lookup field to look for this information.

## Support for Payment Times Reporting

Business Central supports Australian businesses in running their financial reporting. While Business Central doesn't have a dedicated report for reporting according to the Payment Times Reporting Scheme, the data that you need for the report is present. However, for more automated reporting, you must find and install an add-in that is built by a Business Central partner.  

## Reporting the Payment Times

As a reporting entity, you must provide the authorities with two files:

- A declaration document that states that the reported numbers are true, signed by a responsible member of the reporting entity or its controlling (head) entity.
- A delimited text file that contains a line with the reported information in various fields.

Examples and descriptions of these files can be found on the Australian authorities' website: [https://paymenttimes.gov.au/](https://paymenttimes.gov.au/).

The information in the following sections relates only to the delimited text file. The content is intended as model for getting some of the relevant information from Business Central in a manual fashion. Partner-provided capabilities may exist that provide functionality to automate this.

### Marking a vendor as a small business vendor

Consider creating a new **Vendor Posting Group** to be set on vendors that are confirmed to be small business vendors in the **Small Business Identification (SBI) Tool**. You must look up a vendor in this tool to get this confirmation. After a vendor is set to this vendor posting group, the posting group is propagated to the vendor ledger entries, which is key for you to be able to find relevant entries for the report.

### Reporting data

As you'll see from the example template of the delimited text file, much of the information needed for reporting is textual and has to do with trade agreements and explanations for various business decisions. However, there are also numbers that must be reported.  

From a reporting perspective, the interesting thing is how the reporting entity pays its small business vendors. The authorities have defined buckets into which these payments fall and must be reported.

Under the reporting rules that apply to reporting periods starting on or after July 1, 2024, these buckets are:

- Invoices paid within 30 days after the day of receipt
- Invoices paid between 31 days and 60 days after the day of receipt
- Invoices paid more than 60 days after the day of receipt

As a scenario, you must report how many invoices from small business vendors have been paid between 31 and 60 days after the day of receipt of the invoice. You must also report the proportional invoice amount of those invoices compared to the total number of invoices from small business vendors.

### Finding the data for the Payment Times report

As mentioned above, many fields and much of the data needed for the report doesn't reside in Business Central. The invoice data does, and you can find this data in the vendor ledger entries. The following procedure illustrates how you can find the relevant data.

#### Find vendor ledger entries

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Ledger Entries**, and then choose the related link.  
1. Filter the view to include entries within the reporting period.
1. Use the **Filter Totals** and use the **Date Filter** to specify a range that exceeds the reporting period. You can use this to exclude invoices from the list that haven't yet been paid, by comparing the **Original Amount** and **Remaining Amount** fields.
1. Filter the list to show only invoices by setting a filter on **Document Type**.
1. Filter on the **Vendor Posting Group** to only see invoices from small business vendors.

   You can now go through invoices one by one and select the **Applied Entries** action to see information about payments that have been applied to the invoice.
1. In the **Applied Entries** page, make sure you look at records where **Document Type** is **Payment**, so you don't report on invoices that have been closed by a credit memo, for example.
1. If there's a payment for the invoice, use the **Posting Date** to determine how many days have elapsed since receipt of the invoice by comparing it to the **Posting Date** of the Invoice **Vendor Ledger Entry**.
1. Note down how this invoice affects the bucket (such as 31 to 60 days) when it comes to the number of invoices and the proportional number of small business vendor invoices.

As an alternative, consider exporting the full list of vendor ledger entries to Excel by using the action **Page** > **Open in Excel**. In Excel, you can do more advanced calculations and formulas to find the applied entries and payments for an invoice.

> [!NOTE]
> Invoices and their corresponding payments are all vendor ledger entries. Using Excel to find the relevant payments for a given invoice may be more convenient for you.

## Related information

[Australia Local Functionality](australia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
