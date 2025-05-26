---
title: Setting up a bank payment order in Russia
description: Russian enhancements include bank payment orders.
author: DianaMalina


ms.topic: how-to
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Set Up a Bank Payment Order

Bank payment orders must be used if a bank payment is for the official state budget. To use a bank payment order, a general journal template must be created as described in the following procedure.

## To set up a bank payment order

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journal Templates**, and then choose the related link.
2. Create a general journal batch for every bank operation.
3. In the **Bal. Account Type** field, select the bank account type.
4. In the **Bal. Account No.** field, enter the bank account.
5. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Source Codes**, and then choose the related link.
6. Create a source code record.
7. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Source Code Setup**, and then choose the related link.
8. On the **General** FastTab, in the **Bank Payments** field, select the source code that you entered in the **Source Codes** window.

## Related information

 [Bank Management](Bank-Management.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
