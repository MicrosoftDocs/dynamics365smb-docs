---
title: Calculating Due Dates [ES]
description: Learn how to submit an annual report of purchases and sales for payments that were made before or after the due date.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: submit annual report, due date calculation, payment terms, overdue payments, Spanish version
ms.search.form: 7000048
ms.date: 05/26/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Calculating due dates in the Spanish version

In Spain, there's a legal limit for the number of days that a payment can be delayed. You must submit an annual report of purchases and sales for payments that were made before or after the due date. The legal requirements depend on whether the customer is a private company or a public administration. Learn more about the official declaration [BOE-A-2010-10708](https://go.microsoft.com/fwlink/?LinkId=224630) on the Boletín Oficial del Estado website.  

## Payment terms

To help you meet the legal requirements, you can set up payment terms so that the due dates are calculated correctly. This includes specifying the maximum number of calendar days that a payment can be delayed after delivery. For example, you can create separate payment terms for sales to the public sector and sales to private companies. The following table illustrates how you can set up payment terms.  

|Field|Public sector|Private company|  
|---------------------------------|-------------------|---------------------|  
|**Code**|**1M(8D) PUB**|**1M(8D) PRI**|  
|**Due Date Calculation**|**1M**|**1M**|  
|**Max. No. of Days till Due Date**|**30**|**60**|  

For each customer and vendor, you must select the appropriate payment term code. Then, when you create a document for that customer or vendor, [!INCLUDE[prod_short](../../includes/prod_short.md)] calculates a due date that doesn't exceed the limit for the relevant payment term.  

> [!IMPORTANT]  
> You can't post a document that creates a bill where one or more installments have a due date that is later than the limit that is specified in the **Max. No. of Days till Due Date** field.  

If a due date can't be calculated based on the limit, the due date is set to blank. For example, if the calculated due date falls in a non-payment period and there's no available date before that period, you must specify a due date manually. You can't post a document that has an empty due date.  

You can change the calculated due date manually, but you can't make it later than the limit that you specify for the payment term. For example, the due date can be calculated to be late because of conflicts with non-payment periods. In that case, you can decide to make the due date earlier than the non-payment period.  

## Overdue payments

You must include information about overdue payments in the annual reports for the government. [!INCLUDE[prod_short](../../includes/prod_short.md)] includes two reports to help you identify overdue payments from customers and payments that you're late in making.  

The **Customer - Overdue Payments** and **Vendor - Overdue Payments** reports include a section for each customer or vendor that lists the payments with the following information:  

- Invoice number  
- Invoice description  
- Document number  
- Posting date  
- Due date  
- Days overdue  
- Currency code  
- Amount  
- Amount in the local reporting currency (LCY)  

Each section has a summary section with the following information.  

|Information|Description|  
|-----------------|---------------------------------------|  
|Weighted average term exceeded|This formula is calculated based on the number of posted payments for the specified period, the number of days that payments were delayed, and the paid amount in (LCY). Learn about the official declaration [BOE-A-2010-10708](https://go.microsoft.com/fwlink/?LinkId=224630) on the Boletín Oficial del Estado website.|  
|Payments within the legal limit|The amounts in LCY and the percentage of the total payments that were made before the maximum allowed due date for each transaction.|  
|Payments outside the legal limit|The amounts in LCY and the percentage of the total payments that were made after the maximum allowed due date for each transaction.|  

At the end of these reports, there's a section that summarizes this information for all payments. These reports show information based on applied detailed customer ledger entries or applied detailed vendor ledger entries. The information is based on the date filters that you specify. For more information, see Customer - Overdue Payments and Vendor - Overdue Payments.  

## Related information

- [Set Limits for Due Dates](how-to-set-limits-for-due-dates.md)
- [Managing Payables](../../payables-manage-payables.md)
- [Managing Receivables](../../receivables-manage-receivables.md)
- [Defining Payment Methods](../../finance-payment-methods.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
