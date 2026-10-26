---
title: Use One VAT Code in Journals in Norwegian Version [NO]
description: Use VAT Number and Bal. VAT Number in Norwegian Business Central journals to fill in VAT posting groups from a unique VAT posting setup combination.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: one VAT code, VAT code, VAT posting, VAT posting setup, Norwegian version
ms.search.form: 10602, 10697, 10698, 10604
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Use one VAT code in journals in Norwegian version

In Norway, you can use one VAT code in a journal to fill in the commonly used VAT fields. In Business Central 29, select the code in **VAT Number**. This field replaces the former **VAT Code** field and uses codes from **VAT Reporting Codes**.

To set up the VAT code for purchase orders and sales orders, the corresponding VAT business posting groups and the VAT product posting groups have to be defined.  

The VAT rate is calculated from the combination of VAT business posting groups, buyer information, and VAT product posting groups.  

## Create a VAT code  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Reporting Codes**, and then choose the related link.
1. Choose the **New** action.  
1. Enter information in the **Code**, **Gen. Posting Type**, and **Description** fields for each VAT code.
1. Close the **VAT Reporting Codes** page.

## Set up VAT posting

The following procedure explains the VAT posting setup.  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **VAT Posting Setup**, and then choose the related link.  
1. Choose the **New** action.  
1. In the **VAT Posting Setup** card, fill in the following fields:  

   - **VAT Business Posting Group**
   - **VAT Product Posting Group**
   - **VAT Identifier**
   - **VAT %**
   - **Sales VAT Account**
   - **Purchase VAT Account**

1. In the **VAT Number** field, select a code from the list. If the field isn't shown, add it through personalization. Each nonblank VAT number must identify a unique VAT posting setup combination.

Now, when you select **VAT Number** on a general journal line, the VAT business and product posting groups and the general posting type are filled in from the setup.

For example, the VAT rate posted in the journal is defined by the setup that you specified on the **VAT Posting Setup** page.  

> [!NOTE]  
> Use **VAT Number** for the account and **Bal. VAT Number** for the balancing account on the journal line.
>
> No changes are made to the posting.  

## Related information

[Norwegian VAT Codes](norwegian-vat-codes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
