---
title: Electronic invoicing in Spain
description: The following article provides information about how to work with the Spanish localization of the E-Document framework.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords:
ms.search.form: 
ms.date: 01/10/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# Electronic invoicing in Spain

The following article provides information about how to setup and work with the Spanish localization of the E-Document framework.

## E-Documents framework setup

Read detailed information how to set up the E-Documents framework [here](../../finance-how-setup-edocuments.md).  

## Set up local formats  

To set up the format for the E-Document service, follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **E-Document Services**, and then select the related link.
2. Select **New**, and on the **E-Document Services** page, on the **General** FastTab, in the **Document Format** field, choose **Factura-E 3.2.2**.  
3. Configure the fields as described in [Set up e-documents](../../finance-how-setup-edocuments.md).
4. Close the page.

For using in the sales, you need to set up the workflow as described in [Set up e-documents](../../finance-how-setup-edocuments.md) and add this workflow for all customer you want to send e-invoice on the **Document Sending Profile** page.  

## Working with E-invoices

Read detailed information about how to use the E-Documents framework in purchase [Use e-documents in the purchases process](../../finance-how-use-edocuments-purchase.md) and in the sales [Use e-documents in the sales process](../../finance-how-use-edocuments.md).  

> [!NOTE]
> The following nodes are determined using the following methods:
>
> - **InvoiceIssueData**/**ExchangeRateDetails**/**ExchangeRateDate** will be taken as **Posting Date** of the document.
> - **InvoiceHeader**/**InvoiceClass** will be taken from the **SII Sales Invoice Type**: currently we support only the following types OO = Original Invoice, OR = Corrective, OC = Summary.
> - **InvoiceLine**/**UnitOfMeasure** will try best to convert from existing units of measure to the supported units of measures. If not possible, the node will be skipped as it’s not mandatory.


### Corrections with the Credit Memo

When you work with credit memos use everything as mentioned but before posting open the **Credit Memo Details** FastTab where you must add the reason code in the **Factura-E Reason Code** field.  

> [!NOTE]
> The **Corrective**/**TaxPeriod**/**StartDate**-**EndDate** nodes are determined using the following method:
>
> 1. Extract the posting date from the original document.
> 2. Match the posting date with the **VAT Return Period**.
> 3. If no match is found, match the posting date with the **Accounting Period**.
> 4. If still no match is found, use the current year.


## Related information

[Set up e-documents](../../finance-how-setup-edocuments.md)  
[How to use e-documents in sales](../../finance-how-use-edocuments.md)  
[How to use e-documents in purchase](../../finance-how-use-edocuments-purchase.md)  
[Spanish Local Functionality](spain-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
