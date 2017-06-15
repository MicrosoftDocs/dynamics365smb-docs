---
title: Apply Entries in Different Currencies| Microsoft Docs
description: You can apply ledger entries in multiple currencies, for example, if you sell in one currency and receive payment in another.
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies, payment, reconcile
ms.date: 06/02/2017
ms.author: edupont

---
# How to: Enable Application of Ledger Entries in Different Currencies
If you purchase from a vendor in one currency and submit payment in another currency, you can apply the payment to the purchase.

Likewise, if you sell to a customer in one currency and receive payment in another currency, you can apply the payment to the sales invoice.

The following procedure describes how to set this up for vendor ledger entries in the **Purchases & Payables Setup** window. The setup is similar for customer ledger entries in the **Sales & Receivables Setup** window.

> [!NOTE]  
>   This functionality requires that your experience is set to **Suite**. For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).

## To enable application of vendor ledger entries in different currencies
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchases & Payables Setup**, and then choose the related link.
2. In the **Appln. between Currencies** field, select one of the following options.

| Option | Description |
| --- | --- |
| None |Application between currencies is not allowed. |
| EMU |Application between EMU currencies is allowed. |
| All |Application between all currencies is allowed. |

## See Also
[Managing Payables](payables-manage-payables.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Working With [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
