---
title: Use One VAT Code in Journals [NO]
description: Learn how to use one VAT code in journals within the Norwegian version of Business Central to simplify VAT posting.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: one VAT code, VAT code, VAT posting, VAT posting setup, Norwegian version
ms.search.form: 10602, 10697, 10698, 10604
ms.date: 05/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Use one VAT code in journals in Norwegian version

In Norway, you can use the feature one VAT code in a journal, so that you can post VAT by using a single field, **VAT Code**. After it's set up, the one VAT code is a quick way to fill in the commonly used VAT fields.  

To set up the VAT code for purchase orders and sales orders, the corresponding VAT business posting groups and the VAT product posting groups have to be defined.  

The VAT rate is calculated from the combination of VAT business posting groups, buyer information, and VAT product posting groups.  

## Create a VAT code  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Codes**, and then choose the related link.  
1. Choose the **New** action.  
1. Enter information in the **Code**, **General Posting Type**, and **Description** fields for each VAT code.  
1. Choose the **OK** button to close the **VAT Codes** page.  

## Set up VAT posting

The following procedure explains the VAT posting setup.  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **VAT Posting Setup**, and then choose the related link.  
1. Choose the **New** action.  
1. In the **VAT Posting Setup** card, fill in the following fields:  

- **VAT Business Posting Group**  
- **VAT Product Posting Group**  
- **VAT Identifier**  
- **VAT Percentage**  
- **Sales VAT Account**  
- **Purchase VAT Account**  

1. In the **VAT Code** field, select a code from the list.  

Now, when you post a document in the general journal and close it, the information specified in the **VAT Posting Setup** card is applied.  

For example, the VAT rate posted in the journal is defined by the setup that you specified on the **VAT Posting Setup** page.  

> [!NOTE]  
> The **VAT Code** and the **Bal. VAT Code**  fields are added to the journal. The **Bal. VAT Code** is the VAT code that is used to calculate the balancing account.  
>
> No changes are made to the posting.  

## Related information

[Norwegian VAT Codes](norwegian-vat-codes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
