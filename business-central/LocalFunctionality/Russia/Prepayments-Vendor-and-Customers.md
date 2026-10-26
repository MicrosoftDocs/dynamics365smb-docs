---
title: Prepayments for vendors and customers in Russia
description: Learn how to manage vendor and customer prepayments in the Russian version of Business Central.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: posting vendor prepayments, posting customer prepayments, vendor prepayments, customer prepayments, prepayments, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Posting vendor and customer prepayments

In the Russian version of [!INCLUDE[prod_short](../../includes/prod_short.md)], you can post customer and vendor prepayments to separate accounts. Specify these accounts in the **Prepayment Account** field on the customer and vendor posting groups, and enable **Use Prepayment Account** in the corresponding sales or purchases setup.

[!INCLUDE[prod_short](../../includes/prod_short.md)] uses these accounts for payment entries marked as prepayments.

## Post a prepayment

1. On the **General Journal** page, set **Document Type** to **Payment** and select the **Prepayment** check box.
1. Specify the account type and account number, the balance account type, and the balance account number.
1. Post the general journal.

## Apply prepayments

1. Go to the **Vendor Ledger Entries** or **Customer Ledger Entries** page.
1. Select a line with a posted prepayment, and then choose **Apply Entries**.
1. Select the line with the invoice to which you want to apply the prepayment, and then choose the **Set applies-to ID** action.
1. Choose the **Post Application** action.

## Related information

[Russia Local Functionality](russia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
