---
title: Set Up Fixed Assets| Microsoft Docs
description: Learn about the sequence of tasks you must do to set up fixed assets, such as machinery or buildings.
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: machinery, buildings
ms.date: 04/01/2020
ms.author: sgroespe

---
# Setting Up Fixed Assets
Before you can work with Fixed Assets, you need to define a few things:  

* How you insure, maintain, and depreciate fixed assets.  
* How you record costs and other values in the general ledger.  

The table below has links to more information. After you set those things up, you can start various activities. For more information, see [Fixed Assets](fa-manage.md).  

> [!NOTE]  
>   You can record fixed asset transactions in the **Fixed Asset G/L Journal** or **Fixed Asset Journal** pages, depending on whether the transactions are for financial reporting or for internal management. Help for Fixed Assets only describes how to use the **Fixed Asset G/L Journal** page.  

When you enable a fixed asset activity in the **G/L Integration** section on the **Depreciation Book Card** page, the **Fixed Asset G/L Journal** page is used to post transactions for the activity.

The following table describes a sequence of tasks, with links to the topics that describe them.  

| To | See |
| --- | --- |
| Set up default G/L accounts, allocation keys, journal templates and batches for fixed asset posting, and set up fixed asset classes and subclasses, such as Tangible and Intangible. |[Set Up General Fixed Assets Information](fa-how-setup-general.md) |
| Create depreciation books, define various depreciation methods, integrate with the general ledger, and enable duplication of entries in several depreciation books. |[Set Up Fixed Asset Depreciation](fa-how-setup-depreciation.md) |
| Enable insurance of fixed assets, set up general insurance information, an insurance card per policy, and prepare journals to post insurance costs. |[Set Up Fixed Asset Insurance](fa-how-setup-insurance.md) |
| Enable maintenance of fixed assets, set up general maintenance information, set up maintenance posting accounts, and define types of maintenance work. |[Set Up Fixed Asset Maintenance](fa-how-setup-maintenance.md) |
| Learn about different fixed asset depreciation methods. |[Depreciation Methods](fa-depreciation-methods.md) |

## See Also
[Fixed Assets](fa-manage.md)  
[Finance](finance.md)  
[Getting Started](product-get-started.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
