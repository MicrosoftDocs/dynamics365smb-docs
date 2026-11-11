---
title: Set Up Unrealized VAT for Cash-Based Accounting
description: Set up unrealized VAT in Business Central for cash-based accounting, choose how payments realize VAT, and assign temporary sales and purchase VAT accounts.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: cash, VAT, unrealized, cash-based
ms.search.form: 118, 472, 473
ms.date: 11/11/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Set up unrealized VAT for cash-based accounting

If you're using cash-based accounting methods, you can set up [!INCLUDE[prod_short](includes/prod_short.md)] to handle unrealized VAT.

## To use general ledger accounts for unrealized VAT

You can choose to have VAT amounts calculated and posted to a temporary general ledger account when an invoice is posted, and then posted to the correct general ledger account and included in VAT statements when the actual payment of the invoice is posted. Before you can do this, you must complete the [VAT posting setup](finance-setup-vat.md).

To use accounts for unrealized VAT, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Ledger Setup**, and then select the related link.
1. On the **General Ledger Setup** page, select the **Unrealized VAT** checkbox.
1. [!INCLUDE[open-search](includes/open-search.md)], enter **VAT Posting Setup**, and then select the related link.
1. On the **VAT Posting Setup** page, choose the combination of VAT business and VAT product posting groups, and then choose the **Edit** action.
1. In **Unrealized VAT Type**, choose how to allocate payments between the invoice amount excluding VAT and the VAT amount, and when to transfer VAT to the realized account.

    | Option | Description |
    | --- | --- |
    | Blank | Choose this option if you don't want to use the unrealized VAT feature. |
    | Percentage | Payments cover both VAT and the invoice amount in proportion to the payment's percentage of the remaining invoice amount. The paid VAT amount is transferred from the unrealized VAT account to the realized VAT account. |
    | First | Payments cover VAT first and then invoice amounts. In this case, the amount transferred from the unrealized VAT account to the VAT account will equal the amount of the payment until the total VAT has been paid. |
    | Last | Payments cover the invoice amount first and then VAT. In this case, no amount will be transferred from the unrealized VAT account to the VAT account until the total amount of the invoice, excluding VAT, has been paid. |
    | First (Fully Paid) | Payments will cover VAT first (like the **First** option), but no amount will be transferred to the VAT account until the full amount of VAT has been paid. |
    | Last (Fully Paid) | Payments cover the invoice amount first, as with **Last**, but no amount is transferred to the VAT account until the invoice, including VAT, has been paid in full. |

1. In **Sales VAT Unreal. Account**, choose the account for unrealized sales VAT.
1. In **Purch. VAT Unreal. Account**, enter the G/L account for unrealized purchase VAT.

> [!NOTE]  
> Sales VAT stays in the unrealized sales VAT account until customer payments realize it. Purchase VAT stays in the unrealized purchase VAT account until vendor payments realize it. The selected **Unrealized VAT Type** determines when and how much VAT is transferred.

## Related information
[Set Up Calculations and Posting Methods for Value Added Tax](finance-setup-vat.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
