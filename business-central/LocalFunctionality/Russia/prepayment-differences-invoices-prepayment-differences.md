---
title: Prepayment differences in Russia
description: Russian enhancements include managing prepayment differences.
author: DianaMalina


ms.topic: article
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Prepayment Differences

When you apply a prepayment to an invoice in a foreign currency, [!INCLUDE[prod_short](../../includes/prod_short.md)] calculates the difference in the amounts based on currency exchange rates between the invoice and the prepayment and create a prepayment difference entry for the invoice.  

### Setup for Purchases

On the **Purchases & Payables Setup** page, fill in the fields:

| Field                      | Description                                                  |
| -------------------------- | ------------------------------------------------------------ |
| **Use Prepayment Account** | Specifies if you want to post prepayments using the general ledger account. |
| **Posted PD Doc. Nos.**    | Specifies the number series from which numbers are assigned to new records. |
| **PD Doc. Nos. Type**      | Specifies if you want to use a number series or symbol to identify prepayment transaction entries. |
| **Symbol for PD Doc**      | Specifies the symbol that identifies prepayment related entries. |

### Setup for Sales

On the **Sales & Receivables Setup** page, fill in the fields:

| Field                     | Description                                                  |
| ------------------------- | ------------------------------------------------------------ |
| **Use Prepayment Account**    | Specifies if you want to post prepayments using the general ledger account. |
| **Create Prepayment Invoice** | Specifies if you want to create an invoice for the prepayment. |
| **Posted Prepayment Nos.**    | Specifies the number series from which numbers are assigned to new records. |
| **Posted PD Doc. Nos.**       | Specifies the number series from which numbers are assigned to new records. |
| **PD Doc. Nos. Type**         | Specifies if you want to use a number series or symbol to identify prepayment transaction entries. |
| **Symbol for PD Doc.**        | Specifies a symbol that identifies prepayment related entries. |

## Related information

[Russia Local Functionality](russia-local-functionality.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
