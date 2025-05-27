---
title: Make Journal Templates Mandatory [BE]
description: Learn how to make the use of journal templates required in the Belgian version.
author: altotovi
ms.topic: how-to
ms.search.keywords: journal templates, Belgian version
# ms.search.form: 118
ms.date: 04/04/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Make journal templates mandatory in the Belgian version

You can use journals to post purchase and sales documents and make other general ledger entries. Journal templates can then help you structure different types of entries. In the Belgian version of [!INCLUDE [prod_short](../../includes/prod_short.md)], you must specify if journal templates are required in the current company.  

## Make journal templates required in a company

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
1. On the **General** FastTab, select the **Journal Template Name Mandatory** field. This field specifies if users must specify a journal template when they post general ledger transactions.  

> [!NOTE]  
> If the **Journal Template Name Mandatory** field isn't selected, [!INCLUDE [prod_short](../../includes/prod_short.md)] doesn't use template names in the posted documents and entries.

## Use journal templates in sales and purchase documents

If your organization decides to switch on the **Journal Template Name Mandatory** field, you must configure which journal templates must be used as default in sales and purchase documents.

> [!TIP]  
> Before you post a transaction, you can change the suggested template name in the **Journal Template Name** field. This way, the transactions are assigned another document number, as defined by the template.

### Use journal templates in sales documents

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
1. On the **Journal Templates** FastTab, choose the journal templates you want to use as default for all sales documents.  

### Use journal templates in purchase documents

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.  
1. On the **Journal Templates** FastTab, choose the journal templates you want to use as default for all purchase documents.  

## Related information

- [Create Financial Journals in the Belgian Version](how-to-create-financial-journals.md)  
- [Belgium Local Functionality](belgium-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
