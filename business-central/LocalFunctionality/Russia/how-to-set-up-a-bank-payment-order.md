---
title: Setting up a bank payment order in Russia
description: Learn how to set up bank payment orders in Russia using enhanced features for compliance with local banking requirements.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: bank payment order, bank payment, Russia
ms.date: 07/16/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Set up a bank payment order

Bank payment orders must be used if a bank payment is for the official state budget. To use a bank payment order, a general journal template must be created as described in the following procedure.

## Steps to set up a bank payment order

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journal Templates**, and then choose the related link.
1. Create a general journal batch for every bank operation.
1. In the **Bal. Account Type** field, select the bank account type.
1. In the **Bal. Account No.** field, enter the bank account.
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Source Codes**, and then choose the related link.
1. Create a source code record.
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Source Code Setup**, and then choose the related link.
1. On the **General** FastTab, in the **Bank Payments** field, select the source code that you entered in the **Source Codes** window.

## Related information

[Bank Management](Bank-Management.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
