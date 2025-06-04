---
title: Payroll Data Definitions [NO]
description: Learn how the Payroll Data Definitions extension simplifies data exchange with payroll service providers in Norway.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: payroll data definitions, data exchange definitions, payroll transactions, import payment file, Norwegian version
ms.date: 05/16/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Payroll data definitions extension in the Norwegian version

If your business uses the Huldt & Lillevik Lønn - Visma payroll service provider in Norway, the **Payroll Data Definitions (NO)** extension can help you quickly and accurately register payroll transactions from these providers. The extension contains data exchange definitions that enable you to import payroll transactions in files that the providers send to you. Learn more in [Set Up Data Exchange Definitions](../../across-how-to-set-up-data-exchange-definitions.md).

## Getting started

The first step is to map the types of payroll transactions to the general ledger accounts that you want to post them to in [!INCLUDE[prod_short](../../includes/prod_short.md)]. For example, you might want to post retirement plan contributions to an account named Pension, and the taxes paid on the contributions to an account named Pension Tax. This happens outside of [!INCLUDE[prod_short](../../includes/prod_short.md)], for example, you might use an Excel worksheet to visualize the mapping. Work with the payroll service provider to ensure that the file they export contains the mapping. Typically, you can find information about how to configure export files on the provider's website.  

After you install the extension, the next step is to specify the format for the payroll data file from the payroll service provider. To do that, go to the **General Ledger Setup** page and choose the provider in the **Payroll Trans. Import Format** field.  

## Import a payroll file

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link.
1. Choose the journal to use, and then use the **Import Payroll File** action to import the data file from the payroll service provider.  

## Related information

[Norway Local Functionality](norway-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
