---
title: Electronic Invoicing in New Zealand
description: Learn how to set up PINT A-NZ e-document formats, identifiers, and tax categories to send and receive electronic invoices in New Zealand.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: E-Documents, E-Document framework, e-invoice, electronic invoice, Peppol, PINT A-NZ
ms.search.form: 
ms.date: 10/23/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Electronic invoicing in New Zealand

Use the E-Documents framework to send and receive electronic invoices and credit memos in the Peppol PINT A-NZ format.

## E-Documents framework setup

For the general service, workflow, and document sending profile setup, see [Set up e-documents](../../finance-how-setup-edocuments.md).

### Prepare company, customer, and tax information

Before you export PINT A-NZ documents, check the following setup:

- For a company in New Zealand, enter a 13-character **GLN** on the **Company Information** page.
- For a bill-to customer in New Zealand, enter a 13-character **GLN** on the **Customer Card** page.
- Set the **Country/Region Code** for the company and customer correctly. The format uses the country/region's **ISO Code** to identify New Zealand and Australia.
- On the **VAT Posting Setup** page, set **Tax Category** for each posting group combination used on the document to `E`, `S`, `Z`, `G`, or `O`. For categories `E` and `Z`, **VAT %** must be zero.

An invalid identifier length, tax category, or tax rate for categories `E` and `Z` blocks export.

### Set up local formats  

The **E-Document Format for PINT A-NZ** app adds **PINT A-NZ** to the available document formats.

To set up the format for the E-Document service, follow these steps:  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **E-Document Services**, and then select the related link. The **E-Document Services** page displays.
1. Select **New**. On the **General** FastTab, enter a **Code** and **Description**, and set **Document Format** to **PINT A-NZ**.
1. In the **Service Integration** field, select an installed integration for your service provider. You must have an agreement with the provider and configure the integration's connection settings.
1. If you use the version 2.0 import process, select **PINT A-NZ** in the **Draft Format** field on the **Importing** FastTab. This format can read incoming invoices and credit notes into purchase drafts.
1. Configure the remaining fields as described in [Set up e-documents](../../finance-how-setup-edocuments.md).
1. Close the page.  

## Work with electronic invoices

To learn more about using the E-Documents framework in your purchasing and sales workflows, see these articles:

- [Use E-Documents in the sales process](../../finance-how-use-edocuments.md)
- [Use E-Documents in the purchasing process](../../finance-how-use-edocuments-purchase.md)

## Related information

- [Set up E-Documents](../../finance-how-setup-edocuments.md)  
- [How to use E-Documents in sales](../../finance-how-use-edocuments.md)  
- [How to use E-Documents in purchase](../../finance-how-use-edocuments-purchase.md)  
- [New Zealand local functionality](new-zealand-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
