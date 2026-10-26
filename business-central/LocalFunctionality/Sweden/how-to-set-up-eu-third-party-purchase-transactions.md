---
title: Set Up EU Third-Party Purchase Transactions in Sweden
description: Set up EU third-party purchase transactions in the Swedish version of Business Central, enable VAT tracking, and mark qualifying purchase invoices.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: EU, third party, purchase transactions
ms.search.form: 51, 472
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---
# Set up EU third-party purchase transactions in the Swedish version

European Union (EU) third-party trade occurs when you receive a purchase invoice from a vendor in one EU country/region and the products are sent to a different EU country/region without entering Sweden. The transaction amount must be identified and reported separately to comply with Swedish VAT reporting and VAT Information Exchange System (VIES) requirements. [!INCLUDE[prod_short](../../includes/prod_short.md)] lets you mark purchase transactions as EU third-party trade. Posted EU third-party transactions can then be filtered in VAT statements and excluded from the amount in the **Sales to Customer** column in the **VAT- VIES Declaration Tax Auth** report.

> [!NOTE]
> EU third-party purchase functionality is provided by the global EU 3-Party Trade Purchase extension. The earlier Swedish implementation was replaced in version 25.0. In the current implementation, enable the functionality on **VAT Setup**, rather than through **Feature Management**. Learn more in [EU third-party purchase transactions](../../finance-how-to-eu3party-trade-purchase.md).

## Enable EU third-party purchase transactions

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Setup**, and then choose the related link.
1. Turn on **Enable EU 3-Party Purchase**.

## Set up EU third-party purchase transactions  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Purchase Invoices**, and then choose the related link.  
1. Select an existing purchase invoice, or choose the **New** action to create a new one.  
1. Open the purchase invoice. On the **Invoice Details** FastTab, select **EU 3-Party Trade**.
1. Complete the purchase invoice and post it as usual.

## Related information

- [Report VAT to Tax Authorities](../../finance-how-report-vat.md)   
- [Sweden Local Functionality](sweden-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
