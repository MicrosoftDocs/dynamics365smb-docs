---
title: Prepayments for vendors and customers in Russia
description: Learn how to manage vendor and customer prepayments in the Russian version of Business Central.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: posting vendor prepayments, posting customer prepayments, vendor prepayments, customer prepayments, prepayments, Russia
ms.date: 07/18/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Posting vendor and customer prepayments

In the Russian version, prepayments work in a different way compared to the standard version of [!INCLUDE[prod_short](../../includes/prod_short.md)]. When we receive a prepayment, it's necessary by accounting rules to post the prepayment on a separate account. Therefore, the vendor and customer posting groups have the **Prepayment Account** field.

[!INCLUDE[prod_short](../../includes/prod_short.md)] uses this accounts for prepayment entries- Payment with Prepayment check mark.

## Post a prepayment

1. On the **General Journal** page, select the **Document Type - Payment and Prepayment** check box.
1. Specify the account type and account number, the balance account type, and the balance account number.
1. Post the general journal.

## Apply prepayments

1. Go to the **Vendor Ledger Entries** or **Customer Ledger Entries** page.
1. Select a line with a posted prepayment, and then choose the **Apply** action.
1. Select the line with the invoice to which you want to apply the prepayment, and then choose the **Set applies-to ID** action.
1. Choose the **Post Application** action.

## Related information

[Russia Local Functionality](russia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
