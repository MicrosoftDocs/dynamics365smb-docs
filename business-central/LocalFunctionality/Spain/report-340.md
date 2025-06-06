---
title: Report 340 [ES]
description: Provides an overview of Report 340, detailing how it captures information on invoices and taxes issued or received by your company within a specific period.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: report 340, reporting requirements for entrepreneurs, file format, File format restrictions, VAT percentages, EC percentages, Spanish version
ms.date: 05/29/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Report 340 in the Spanish version

The **Report 340** report contains information about invoices and taxes that were issued or received by your company in a given period, based on **VAT Date**. The report is generated in a format that is approved by the tax authorities. This report should be submitted in the company's monthly or quarterly liquidation period, depending on the size of the company. This file can be uploaded to the Spanish Tax Agency website or submitted on CD-ROM. Learn more at the [Spanish Tax Agency](https://www.agenciatributaria.es/) website. If the number of operations exceeds 1,000,000, the report can be submitted electronically.  

## Reporting requirements for entrepreneurs and small companies

The reporting requirements for entrepreneurs and small businesses are modified to support businesses that use the cash accounting criteria (CAC).  

A company can use the cash accounting method if business sales don't exceed 2,000,000 euros per year. There's one exception to this rule for a business whose receipts in cash from any single customer exceed the sum of 100,000 euros.  

In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can set up posting groups for cash-based VAT accounting for purchases and sales.  

 If you file a report under this regimen, the following label is applied to certain [!INCLUDE[prod_short](../../includes/prod_short.md)] reports: **Régimen especial del criterio de caja**. The modified reports are:  

|Report|Description|  
|------------|---------------------------------------|  
|Report 117|Reminder|  
|Report 118|Finance Charge Memo|  
|Report 205|Order Confirmation|  
|Report 206|Sales - Invoice|  
|Report 207|Sales - Credit Memo|  
|Report 405|Purchase Order|  
|Report 406|Purchase – Invoice|  
|Report 407|Purchase - Credit Memo|  
|Report 5900|Service Order|  
|Report 5911|Service - Invoice|  
|Report 5912|Service - Credit Memo|  

## File format

The file format for the **Report 340** report includes one deponent record, and at least one issued invoice or one received invoice. Deponent information comes from the **Company Information** table and the request form. Issued invoices come from the companies to which you sold goods or services. Customer information comes from the **Customer** table. Received invoices come from the companies from which you purchased goods or services. Vendor information comes from the **Vendor** table.  

> [!NOTE]  
> If there are no file format records, the file isn't created and an error message is displayed.  

## Entries included in Report 340

The entries included in **Report 340** must have been posted in the period and fiscal year entered in the request form. The entries that are included in the report of payments in cash can be posted from the previous year.  

### Businesses

**Report 340** must include the following entries:  

- Posted sales invoices and credit memos.  
- Posted purchase invoices and credit memos.  
- Posted service invoices and credit memos.  
- Auto invoices and auto credit memos.  
- Payments in cash.  

Entries in the **Sales Invoice Book** report must be included in the report as issued invoices.  

Entries in the **Purchase Invoice book** report must be included in the report as received invoices.  

### Small businesses

For small businesses and entrepreneurs operating under the Cash Accounting Criteria (CAC), Report 340 reports invoices under the CAC. The invoice is marked with a "Z" for operation type. If the invoice is under the CAC, then the following details are reported:  

- Payment/receipt method, that is, cash, check, transfer, and so forth. This field is blank in the report if no payment collection has occurred.  
- Payment/receipt amount (full, partial)  
- Payment/receipt dates  

### Invoices including different VAT percentages or EC percentages

If the invoice has more than one VAT percentage or equivalence charge (EC) percentage, the report must include all of the records with different VAT percentage and EC percentage. If the invoice includes equivalence charges (EC), the EC percentage and EC amount without VAT is displayed.  

All of these records show the same invoice ID and customer VAT number.  

## File format restrictions

Before creating the **Report 340** report, you should consider the following file format restrictions:  

- All amounts must be in euro.  
- All amounts must be positive. In the fields where negative amounts are possible, **N** is specified.  
- All text must be capitalized.  
- All alphanumeric fields must be left-aligned.  
- All numeric fields must be right-aligned.  
- Special characters are converted to standard characters.  
- If the field has no value, it's empty for alphanumeric fields and populated with zeros for numeric fields.  

## Related information

- [Create Report 340](how-to-create-report-340.md)
- [Payments in Cash](payments-in-cash.md)
- [Spain Local Functionality](spain-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
