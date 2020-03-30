---
title: Prepayments for vendors and customers in Russia
description: Russian enhancements include managing prepayments to vendors and from customers.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Posting Vendor and Customer Prepayments

In the Russian version, prepayments work in a different way compared to the standard version of [!INCLUDE[prodshort](../../includes/prodshort.md)]. When we receive a prepayment, it is necessary by accounting rules to post the prepayment on a separate account. Therefore, the vendor and customer posting groups have the **Prepayment Account** field.

[!INCLUDE[prodshort](../../includes/prodshort.md)] uses this accounts for prepayment entries- Payment with Prepayment check mark.

## To post a prepayment

1. On the **General Journal** page, select the **Document Type - Payment and Prepayment** check box.
2. Specify the account type and account number, the balance account type, and the balance account number.
3. Post the general journal.

## To apply prepayments

1. Go to the **Vendor Ledger Entries** or **Customer Ledger Entries** page.
2. Select a line with a posted prepayment, and then choose the **Apply** action.
4. Select the line with the invoice to which you want to apply the prepayment, and then choose the **Set applies-to ID** action.
6. Choose the **Post Application** action.

## See Also

[Russia Local Functionality](russia-local-functionality.md)  
