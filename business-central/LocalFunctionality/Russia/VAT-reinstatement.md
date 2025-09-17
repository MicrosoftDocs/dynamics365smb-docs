---
title: VAT reinstatement in Russia
description: Learn how to manage VAT reinstatement in Business Central for Russian localizations, including setup and processing steps.
author: DianaMalina
ms.topic: article
ms.search.keywords: VAT reinstatement, Russia VAT, VAT journal, VAT posting setup, Russia
ms.date: 07/22/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# VAT reinstatement

In certain cases, VAT payers are required to reinstate VAT.

It's known that the organizations acquiring fixed assets, goods, works, services (further – goods), have the right to accept to deduction of the input VAT on them at accomplishment of all conditions for deduction. But if later circumstances change and it becomes clear that there's no right to deduct VAT, the tax has to be reinstated. In other words, the reinstatement VAT is previously deducted VAT, which in a certain amount must be returned back to the budget.

## VAT accounting group settings  

VAT reinstatement is possible in case of using transit VAT with manual post through the VAT journal.  

In **VAT posting setup**, settings must be made:  

- VAT calculation type – NORMAL VAT.
- The unrealized VAT type is NOT EMPTY (for example Percentage).  
- Trans. VAT account – must not be filled.
- Transit VAT Type – shouldn't be filled.  
- Manual VAT Settlement checked.  
- The template and batch VAT settlement is specified.  
- VAT reinstatement template and VAT reinstatement batch – set.

## Reinstate VAT

To reinstate previously accepted for deduction of VAT used **VAT Reinstatement Worksheet**.

1. In the **VAT Reinstatement Worksheet** page, you must run the task **Suggest Documents**.  
1. You must set a filter by date (usually at the end of the month, as the documents were read).  

    And you can specify a filter on VAT Business and VAT product posting groups.  

    As a result of the work of the task in the journal, the VAT lines of operations to be restored (a list of purchase documents in which there are VAT operations previously accepted for post).

    The field **Realized VAT Amount** reflects the amount of VAT on the document, which was deducted and which can be reinstate.

1. In this worksheet, select the lines that you want to reinstate and select the "Copy lines to Journal" button. Before that, you need to set a filter by date by right-clicking on the name of any column. Add filter "Filter totals by".
1. You can reinstate the entire transaction (for the entire amount of VAT sold), you can set a factor (for example, 0.5) to reinstate part of the amount.
1. The selected line is transferred to the VAT Reinstatement journal for posting.

## Related information

[Russia Local Functionality](russia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
