---
title: How to Set Up VAT Reports [DE]
description: Learn how to set up VAT statements, company information, and tax office data before you declare VAT-VIES tax or sales VAT advance notifications in the German version.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: VAT report setup, tax office setup, VAT statement setup, German version
ms.date: 10/09/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Set up VAT reports in the German version

> [!NOTE]
> This article previously described a dedicated **VAT Report** page with fields such as **Trade Type**, **EU Goods/Services**, and a **ZIVIT** FastTab. That page doesn't exist for the German version. For Germany, VAT reporting setup is split between the **VAT Statement Names** page, the **Company Information** page, and the ELSTER-specific setup pages, as described in this article.

Before you can declare VAT-VIES tax or create and export sales VAT advance notifications in [!INCLUDE[prod_short](../../includes/prod_short.md)], you must set up company and tax office information, and link a VAT statement to the declaration.

## Set up company and tax office information

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
1. Fill in the tax office fields, including **Tax Office Name**, **Tax Office Address**, **Tax Office City**, **Tax Office Post Code**, and **Tax Office Number**.  
1. In the **VAT Representative** field, enter the contact person for VAT-related information.  
1. Choose the **OK** button.

## Link a VAT statement to the declaration

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Statement**, and then choose the related link.  
1. On the **VAT Statements** page, in the **Name** field, choose the dropdown arrow.  
1. On the **VAT Statement Names** page, in the line for the appropriate VAT statement name, select the **Sales VAT Adv. Notification** field to use that statement for sales VAT advance notifications.  

For the complete setup of sales VAT advance notifications, including the **Electronic VAT Decl. Setup** page, see [Set up and export sales VAT advance notifications](how-to-set-up-and-export-sales-vat-advance-notifications.md).

## Related information

- [VAT Reporting](vat-reporting.md)
- [Set up and export sales VAT advance notifications](how-to-set-up-and-export-sales-vat-advance-notifications.md)
- [Declare VAT-VIES tax](how-to-declare-vat-vies-tax.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
