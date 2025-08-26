---
title: Set Up FA Insurance
description: Configure insurance cards and policy details to manage fixed-asset insurance coverage.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: policy, coverage
ms.search.form: 5607, 5648, 5644, 5651
ms.date: 08/07/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up fixed asset insurance

To manage fixed asset insurance coverage, you must first set up some general insurance information and an insurance card per policy.

## Set up general insurance information

To use the insurance features in [!INCLUDE[prod_short](includes/prod_short.md)], you must set up some general insurance information.  

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Setups**, and then choose the related link.  
1. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## Set up insurance types

You can group your insurance policies into categories, such as insurance against theft or fire insurance. The insurance types are used on the insurance card.

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Insurance Types**, and then choose the related link.  
1. Fill in the fields as necessary.

## Set up insurance cards

You may accumulate information about each insurance policy on the insurance card.  

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Insurance**, and then choose the related link.  
1. On the **Insurance** page, choose the **New** action to create a  new insurance card.  
1. Fill in the fields as necessary.

## Set up insurance journal templates

[!INCLUDE[prod_short](includes/prod_short.md)] automatically creates an insurance journal template the first time that you open the **Insurance Journal** page, but you can set up additional journal templates. Learn more in [Work with General Journals](ui-work-general-journals.md).  

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Insurance Journal Templates**, and then choose the related link.  
1. Fill in the fields as necessary.

## Set up insurance journal batches

You can set up batches in an insurance journal template. The values in the journal batch are used as default values if the fields aren't filled in on the journal lines. Learn more in [Work with General Journals](ui-work-general-journals.md)  

1. Choose the ![Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Insurance Journal Templates**, and then choose the related link.  
1. Select an insurance journal template, and then choose the **Batches** action.
1. On the **Insurance Journal Batches** page, fill in the fields as necessary.

> [!NOTE]  
> Numbers have a special function in journal names. If a journal template name or journal batch name contains a number, the number automatically advances by one every time that the journal is posted. For example, if HH1 is entered in the **Name** field, the journal name will change to HH2 after the journal named HH1 has been posted.

## Related information

- [Setting Up Fixed Assets](fa-setup.md)  
- [Fixed Assets](fa-manage.md)  
- [Finance](finance.md)  
- [Getting Ready for Doing Business](ui-get-ready-business.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
