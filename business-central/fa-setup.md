---
title: Set Up Fixed Assets (FA)
description: Learn about the sequence of tasks you must do to set up fixed assets, such as machinery or buildings.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: machinery, buildings
ms.search.form: 5607
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Setting Up Fixed Assets

Before you can work with Fixed Assets, you need to define a few things:  

* How you depreciate fixed assets.  
* How you record acquisition costs, depreciations, and other values in the general ledger.  
* Optionally, how to record insurance and maintenance on fixed assets.

The sections below have links to more information on how to setup Fixed Assets. After you finish the setup, you can start working with Fixed Assets features. For more information, see [Using Fixed Assets](fa-manage.md).  

> [!NOTE]  
> You can record fixed asset transactions in the **Fixed Asset G/L Journal** or **Fixed Asset Journal** pages, depending on whether the transactions are for financial reporting or for internal management. The help articles for Fixed Assets only describes how to use the **Fixed Asset G/L Journal** page.  

When you enable a fixed asset activity in the **G/L Integration** section on the **Depreciation Book Card** page, the **Fixed Asset G/L Journal** page is used to post transactions for the activity.


## Required setup tasks

The following table describes a sequence of tasks needed for setting up Fixed Assets, with links to the topics that describe them. 

| To | See |
| -- | --- |
| Set up default G/L accounts, allocation keys, journal templates and batches for fixed asset posting, and set up fixed asset classes and subclasses, such as Tangible and Intangible. |[Set Up General Fixed Assets Information](fa-how-setup-general.md) |
| Create depreciation books, define various depreciation methods, integrate with the general ledger, and enable duplication of entries in several depreciation books. |[Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md) |


## Optional setup tasks (insurance, maintenance, and user-defined depreciation methods)

The following table describes a sequence of optional tasks needed for setting up Fixed Assets features such as insurance, maintenance, and user-defined depreciation methods, with links to the topics that describe them. 

| To | See |
| -- | --- |
| Enable insurance of fixed assets, set up general insurance information, an insurance card per policy, and prepare journals to post insurance costs. |[Set Up Fixed Asset Insurance](fa-how-setup-insurance.md) |
| Enable maintenance of fixed assets, set up general maintenance information, set up maintenance posting accounts, and define types of maintenance work. |[Set Up Fixed Asset Maintenance](fa-how-setup-maintenance.md) |
| Learn about how to apply user-defined depreciation methods. |[Set Up User-Defined Depreciation Methods](fa-how-setup-user-defined-depreciation-method.md) |


## See also

[Fixed Assets overview](fa-manage.md)  
[Finance](finance.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
