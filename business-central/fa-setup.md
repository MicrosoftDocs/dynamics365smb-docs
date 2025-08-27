---
title: Set up fixed assets
description: Learn about the sequence of tasks to set up fixed assets, such as machinery or buildings.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: v-soumramani
ms.topic: concept-article
ms.search.keywords: machinery, buildings, fixed assets
ms.search.form: 5607
ms.date: 08/07/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Setting up fixed assets

Before you can work with fixed assets (FA), you need to define a few things:  

* How you depreciate fixed assets.  
* How you record acquisition costs, depreciations, and other values in the general ledger.  
* Optionally, how to record insurance and maintenance on fixed assets.

The sections in this article link to more information about how to set up fixed assets. After you finish the setup, you can start working with fixed assets. Learn more in [Using Fixed Assets](fa-manage.md).  

> [!NOTE]  
> You can record fixed asset transactions in the **Fixed Asset G/L Journal** or **Fixed Asset Journal** pages, depending on whether the transactions are for financial reporting or for internal management. The help articles for fixed assets only describe how to use the **Fixed Asset G/L Journal** page.  

When you enable a fixed asset activity in the **G/L Integration** section on the **Depreciation Book Card** page, use the **Fixed Asset G/L Journal** page to post transactions for the activity.

## Required setup tasks

The following table contains a sequence of tasks to set up fixed assets, and links to related articles.

| To... | Go to... |
|--|--|
| Set up default G/L accounts, allocation keys, journal templates and batches for fixed asset posting, and set up fixed asset classes and subclasses, such as Tangible and Intangible. | [Set Up General Fixed Assets Information](fa-how-setup-general.md) |
| Create depreciation books, define various depreciation methods, integrate with the general ledger, and enable duplication of entries in several depreciation books. | [Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md) |

## Optional setup tasks (insurance, maintenance, and user-defined depreciation methods)

The following table contains a sequence of optional tasks to set up fixed assets, such as insurance, maintenance and depreciation methods, and links to related articles.

| To... | Go to... |
|--|--|
| Enable insurance of fixed assets, set up general insurance information, an insurance card per policy, and prepare journals to post insurance costs. | [Set Up Fixed Asset Insurance](fa-how-setup-insurance.md) |
| Enable maintenance of fixed assets, set up general maintenance information, set up maintenance posting accounts, and define types of maintenance work. | [Set Up Fixed Asset Maintenance](fa-how-setup-maintenance.md) |
| Learn about how to apply depreciation methods. | [Set Up User-Defined Depreciation Methods](fa-how-setup-user-defined-depreciation-method.md) |

## Related information

- [Fixed Assets overview](fa-manage.md)  
- [Fixed assets analytics overview](fa-analytics-overview.md)  
- [Finance](finance.md)  
- [Getting Ready for Doing Business](ui-get-ready-business.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
