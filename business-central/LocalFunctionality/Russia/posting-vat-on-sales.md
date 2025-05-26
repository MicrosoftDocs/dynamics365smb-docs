---
title: Posting VAT on sales in Russia
description: Russian enhancements include VAT on sales documents.
author: DianaMalina


ms.topic: how-to
ms.search.keywords:
ms.date: 04/01/2021
ms.reviewer: bholtorf
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Posting VAT on Sales

The following fields have been added to the **VAT Posting Setup** window (ID 472):

| Field                       | Description                                                  |
| :-------------------------- | :----------------------------------------------------------- |
| **Trans. VAT Type**         | Used to define the rule for extracting VAT.                  |
| **Trans. VAT Account**      | Used to specify an account to register the VAT amount from the gain and from the customer's prepayments to be paid to the federal budget. |
| **Tax Invoice Amount Type** | Used to select the value of VAT. Depending on the value in this field, VAT entry amounts are used in different columns of the VAT purchase or sales ledgers. |

The above actions are taken for each combination of the Sales VAT Product posting group and Sales VAT posting group. 

In the **Trans. VAT Type** field, the following options are available:

- **Amount + Tax**
- **Amount & Tax**

To account for VAT, choose the **Amount + Tax** action.

The following procedure shows how the accounting entries are created.

1. In the **Trans. VAT Account No.** field, enter Subaccount 90-3, Gain VAT.
2. In the **Sales VAT Account** field, enter Subaccount 68, VAT to Federal Budget.

The following accounting entries create the different settings.

 

| Accounting Entries | Settings                                                     |
| :----------------- | :----------------------------------------------------------- |
| **Amount + Tax**   | Debit 62 Payables and Receivables - Credit 90-1 Gain and Sales Amount Including VAT   Debit 90-3 Gain VAT   Credit 68 VAT to Federal Budget   Sales VAT Amount |
| **Amount & Tax**   | Debit 62 Payables and Receivables   Credit 90-1 Gain   Amount Excluding VAT   Debit 62 Payables and Receivables   Credit 90-3 Gain VAT   Sales VAT Amount   Debit 90-3 Gain VAT   Credit 68 VAT to Budget   Sales VAT amount |
|                    | Debit 62 Payables and Receivables   Credit 90-1 Gain   Amount Excluding VAT   Debit 62 Payables and Receivables   Credit 68 VAT to Budget   Sales VAT Amount |

## Trans. VAT Account Field

In the **Trans. VAT Account** field, enter Subaccount 90-3 Gain VAT or Subaccount 62 Prepayment VAT. If this field is blank, the postings use the account from the Customer posting groups from the **Receivables Account** field.

## Related information

[VAT Ledgers](VAT-Ledgers.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
