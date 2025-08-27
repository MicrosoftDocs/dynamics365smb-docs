---
title: Set Up FA Maintenance
description: Specify general maintenance information, maintenance codes for types of work, and a maintenance-expense posting account to manage fixed asset repairs and service.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: repair, service
ms.search.form: 5600, 5642
ms.date: 08/07/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up fixed asset maintenance

To manage fixed asset maintenance, you must first set up some general maintenance information, a posting account for maintenance costs, and maintenance codes for types of work, such as Routine Service or Repair.

## Set up general maintenance information

If you set up the fields for maintenance, you can post maintenance expenses from the fixed asset journal.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Fixed Assets**, and then choose the related link.
2. Select the fixed asset that you to define insurance coverage for, and then choose the **Edit** action.
3. On the **Maintenance** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## Set up maintenance codes

When you post maintenance costs from a general journal, you fill in the **Maintenance Code** field to record what kind of maintenance has been performed, such as routine service or repair.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Maintenance**, and then choose the related link.
2. On the **Maintenance** page, set up codes for different types of maintenance work.

## Set up maintenance expense accounts

To post maintenance costs, you must first enter an account number on the **FA Posting Groups** page.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **FA Posting Groups**, and then choose the related link.
2. Fill in the **Maintenance Expense Account** field for each posting group.

> [!NOTE]  
> To define that maintenance costs are allocated to departments or projects, set up an allocation keys. Learn more in [Set Up General Fixed Assets Features](fa-how-setup-general.md).

## Related information

- [Setting Up Fixed Assets](fa-setup.md)  
- [Fixed Assets](fa-manage.md)  
- [Finance](finance.md)  
- [Getting Ready for Doing Business](ui-get-ready-business.md)  
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
