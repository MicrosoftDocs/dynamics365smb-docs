---
title: Electronic Invoicing with Factura-E in Spain
description: Learn how to configure Factura-E 3.2.2 in the Business Central E-Documents framework for Spain and export invoices and corrective credit memos.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Spanish localization, Spanish local functionality, e-documents framework, e-documents, framework setup, local formats setup, e-invoices, credit memos corrections, Spanish version
ms.date: 10/20/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Electronic invoicing in Spain

This article provides information about how to set up and work with the Spanish localization of the E-Document framework.

## E-documents framework setup

Learn more in [Set up e-documents](../../finance-how-setup-edocuments.md) for information about how to set up the E-Documents framework.

## Set up local formats  

To set up the format for the E-Document service, follow these steps:  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **E-Document Services**, and then select the related link.
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
> - **InvoiceHeader**/**InvoiceClass** comes from the document's **Invoice Type**, which uses the SII sales invoice types. F1, F2, and F3 produce `OO` for an original invoice. F4 produces `OC` for a summary. Other types produce `OR` for a corrective invoice.
> - **InvoiceLine**/**UnitOfMeasure** is included when the unit of measure's **International Standard Code** matches a supported Factura-E unit. If there's no match, the optional node is omitted.

### Corrections with credit memos

When you work with credit memos, before you post, on the **Credit Memo Details** FastTab add a reason code in the **Factura-E Reason Code** field. Factura-E validation requires this code when you export a sales credit memo.

> [!NOTE]
> The **Corrective**/**TaxPeriod**/**StartDate**-**EndDate** nodes are determined using the following method:
>
> 1. Use the posted credit memo's **Posting Date**, not the original invoice's date.
> 1. If a **VAT Return Period** contains that date, use its start and end dates.
> 1. Otherwise, use the latest **Accounting Period** start on or before that date and the end of its fiscal year.
> 1. If no accounting period is found, use the calendar year that contains the credit memo's posting date.

## Related information

- [Set up e-documents](../../finance-how-setup-edocuments.md)  
- [How to use e-documents in sales](../../finance-how-use-edocuments.md)  
- [How to use e-documents in purchase](../../finance-how-use-edocuments-purchase.md)  
- [Spanish Local Functionality](spain-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
