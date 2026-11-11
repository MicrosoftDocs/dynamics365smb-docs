---
title: Use EU Third-Party Purchase Transactions
description: Enable EU third-party purchase transactions in Business Central, mark purchase documents, and include or exclude the transactions in VAT statements.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.form: 50, 51, 52, 187, 317
ms.search.keywords: EU3P, EU 3-P, EU 3-Party
ms.date: 11/11/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Use EU third-party purchase transactions

European Union (EU) third-party trade occurs when you receive a purchase invoice from a vendor in one EU country/region, and the products are sent directly to another country/region without entering your country/region. The transaction amount can be identified and reported separately to comply with some EU countries/regions value-added tax (VAT) reporting and VAT Information Exchange System (VIES) requirements. Microsoft Dynamics 365 Business Central enables purchase transactions to be set up as EU third-party trade. Posted EU third-party transactions can be filtered in VAT statements and excluded from the amount in the **Sales to Customer** column of the **VAT-VIES Declaration Tax Auth** report.

## Prerequisites

- The **EU 3-Party Trade Purchase** extension must be installed. Even if the extension is preinstalled, the functionality isn't enabled by default. On the **VAT Setup** page, select **Enable EU 3-Party Purchase** as described below.

- The EU third-party trade feature is unavailable in the German (DE) or Italian (IT) localized versions, because it's not compatible with the local VAT reporting and declaration features specific to these countries/regions.

## Enable EU third-party trade functionality for a purchase

1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Setup**, and then select the related link.
1. On the **VAT Setup** page, select the **Enable EU 3-Party Purchase** checkbox.

## Use EU third-party trade functionality

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Invoices** (or another purchase document), and then select the related link.
1. Select an existing purchase invoice, or select **New** to create a new one.
1. On the **Invoice Details** FastTab, select the **EU 3-Party Trade** checkbox.
1. Close the page.

## Include or exclude EU third-party trade records on the VAT statement

1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Statements**, and then select the related link.
1. On the **VAT Statements** page, set **EU 3-Party Trade Filter** on each **VAT Entry Totaling** row that you want to filter.

    | Option | Description |
    |--------|-------------|
    | All | Show all records, regardless of whether the **EU 3-Party Trade** field in documents was marked. |
    | EU3 | Show only records where the **EU 3-Party Trade** field in documents was marked. |
    | non-EU3 | Show only records where the **EU 3-Party Trade** field in documents wasn't marked. |

## Related information

[Financial Management](finance.md)  
[Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
