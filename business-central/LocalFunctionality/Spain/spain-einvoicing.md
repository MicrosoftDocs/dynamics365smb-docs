---
title: Electronic invoicing in Spain
description: Learn how to set up and work with the Spanish localization of the E-Document framework.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: Spanish localization, Spanish local functionality, e-documents framework, e-documents, framework setup, local formats setup, e-invoices, credit memos corrections, Spanish version
ms.search.form: 
ms.date: 05/29/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Electronic invoicing in Spain

This article provides information about how to set up and work with the Spanish localization of the E-Document framework.

## E-Documents framework setup

Learn more in [Set up e-documents](../../finance-how-setup-edocuments.md) for information about how to set up the E-Documents framework.

## Set up local formats  

To set up the format for the E-Document service, follow these steps:  

1. Select the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.
1. Select **New**, and on the **E-Document Services** page, on the **General** FastTab, in the **Document Format** field, choose **Factura-E 3.2.2**.  
1. Configure the fields as described in [Set up e-documents](../../finance-how-setup-edocuments.md).
1. Close the page.

For use in sales, set up the workflow as described in [Set up the workflow](../../finance-how-setup-edocuments.md#set-up-the-workflow). Then, on the **Document Sending Profile** page, add the workflow for the customers you send e-invoices to.  

## Work with e-invoices

Use the E-Documents framework in purchases as described in [Use e-documents in the purchases process](../../finance-how-use-edocuments-purchase.md). Learn more in [Use e-documents in the sales process](../../finance-how-use-edocuments.md) for information about the sales process.  

> [!NOTE]
> The following nodes are determined using the following methods:
>
> - **InvoiceIssueData**/**ExchangeRateDetails**/**ExchangeRateDate** is taken as the **Posting Date** of the document.
> - **InvoiceHeader**/**InvoiceClass** is taken from the **SII Sales Invoice Type**. Currently, we support the following types: **OO = Original Invoice**, **OR = Corrective**, and **OC = Summary**.
> - **InvoiceLine**/**UnitOfMeasure** tries to convert existing units of measure to the supported units of measures. If it can't, it skips the node because it isn't mandatory.

### Corrections with credit memos

When you work with credit memos, before you post, on the **Credit Memo Details** FastTab add a reason code in the **Factura-E Reason Code** field.  

> [!NOTE]
> The **Corrective**/**TaxPeriod**/**StartDate**-**EndDate** nodes are determined using the following method:
>
> 1. Extract the posting date from the original document.
> 1. Match the posting date with the **VAT Return Period**.
> 1. If no match is found, match the posting date with the **Accounting Period**.
> 1. If a match still isn't found, use the current year.

## Related information

- [Set up e-documents](../../finance-how-setup-edocuments.md)  
- [How to use e-documents in sales](../../finance-how-use-edocuments.md)  
- [How to use e-documents in purchase](../../finance-how-use-edocuments-purchase.md)  
- [Spanish Local Functionality](spain-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
