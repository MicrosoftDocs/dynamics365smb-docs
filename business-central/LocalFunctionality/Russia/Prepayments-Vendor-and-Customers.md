---
title: Prepayments for vendors and customers in Russia
description: Russian enhancements include managing prepayments to vendors and from customers.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 10/01/2019
ms.reviewer: edupont
ms.author: soalex
---

# Prepayments Vendor and Customers

In the Russian version, prepayments work in a different way compared to the standard version of [!INCLUDE[prodshort](../../includes/prodshort.md)]. When we receive a prepayment, it is necessary by accounting rules to post prepayment on separate account, that way Vendor and Customer Posting groups have field - Prepayment Account

[!INCLUDE[prodshort](../../includes/prodshort.md)] uses this accounts for prepayment entries- Payment with Prepayment check mark.

## Posting a prepayment

In the **General Journal** page, choose Document type - Payment and Prepayment - yes.

Specify the account type and account number, the balance account type, and the balance account number.

Post the general journal.

## Applying prepayments

1. Go to the **vendor ledger entries** or **customer ledger entries**.
2. Select a line with a posted prepayment.
3. On the **Home** tab, click apply operations.
4. Select the line with the invoice to which you want to apply the prepayment.
5. Press **Set applies-to ID**.
6. Press **Post Application**.

## See Also

[Russia Local Functionality](russia-local-functionality.md)  
