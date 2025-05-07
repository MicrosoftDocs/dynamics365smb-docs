---
title: Rules for automatic application of payments
description: Read about how to set Up Rules for the Automatic Application of Payments on the Payment Application Rules page.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.search.form: 1290, 1294, 1287
ms.date: 06/03/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Set up rules for automatic application of payments

On the **Payment Application Rules** page, you set up rules to govern how payment text (on a bank transaction) is automatically matched with text on related open (unpaid) invoices, credit memos, or other entries when you use the **Apply Automatically** function on the **Payment Reconciliation Journal** page. For more information, see [Reconcile payments using automatic application](receivables-how-reconcile-payments-auto-application.md).

You set up new payment application rules by choosing which types of data on a payment reconciliation journal line must match with data on one or more open entries before the related payment is automatically applied to the open entries. The quality of each automatic application is shown as a value of **Low** to **High** in the **Match Confidence** field on the **Payment Reconciliation Journal** page according to the payment application rule that was used.

Each row on the **Payment Application Rules** page represents a payment application rule. Rules are applied in the order specified by the **Sorting Order** field. If multiple rules are used simultaneously, then the match confidence of the highest sorted rule is used.

The automatic application function is based on prioritized matching criteria. First the function tries, in prioritized order, to match text in the five **Related-Party** fields on a journal line with text in the bank account, name, or address of customers or vendors with unpaid documents representing open entries. Then, the function tries to match text in the **Transaction Text** and **Additional Transaction Info** fields on a journal line with text in the **External Document No.** and **Document No.** fields on open entries. Last, the function tries to match the amount in the **Statement Amount** field on a journal line with the amount on open entries.

> [!NOTE]
> Text matching is only possible for text longer than four characters.

In addition to the matching criteria, the following applies concerning the sign of the payment amount:

- For negative amounts, a match is made first against open entries representing customer invoices and then against vendor credit memos.
- For positive amounts, a match is made first against open entries representing vendor invoices and then against customer credit memos.

## To set up a payment application rule
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Application Rules**, and then choose the related link.
2. Define a new or edited payment application rule by filling the fields on a line as described in the following table.

|Field|Description|
|-|-|
|**Match Confidence**|Specifies your confidence in the application rule that you define on the line. <br /></br>A value that you specify in this field is shown in the **Match Confidence** field on the **Payment Reconciliation Journal** page according to the quality of the automatic payment application on the journal line.|
|**Priority**|Specifies the priority of the application rule relative to other application rules that are defined as lines on the **Payment Application Rules** page. 1 represents the highest priority.|
|**Related Party Matched**|Specifies how much information about the customer or vendor, such as address, city name, and bank account number, on the payment reconciliation journal line must match with information about the open entry before the application rule will be used to automatically apply the payment to the open entry.|
|**Document No./Ext. Document No. Matched**|Specifies whether text on the payment reconciliation journal line must match with the value in the **Document No.** field or the **External Document No.** field on the open entry before the application rule will be used to automatically apply the payment to the open entry.|
|**Number of Entries Within Amount Tolerance Found**|Specifies how many entries for a customer or vendor must match the amount including payment tolerance before the application rule will be used to automatically apply a payment to the open entry.|
|**Review Required**|Specifies whether the automatic payment application is recommended for manual review by the user before posting. Choosing the **Lines to Review** field on the **Payment Application Journal** page starts a guided experience where you can easily review multiple applications in a sequence on the **Payment Application Review** page.|

The following table describes the standard payment application rules in [!INCLUDE[prod_short](includes/prod_short.md)].

> [!Important]
> The payment application rules may be different in your implementation of [!INCLUDE[prod_short](includes/prod_short.md)].

| Match Confidence | Priority | Related Party Matched | Document No./Ext. Document No. Matched | Number of Entries Within Amount Tolerance Found |
|------------------|----------|-----------------------|--------------------------------|--------------------------------|
| High             | 1        | Fully                 | Yes - Multiple                 | One Match                      |
| High             | 2        | Fully                 | Yes - Multiple                 | Multiple Matches               |
| High             | 3        | Fully                 | Yes                            | One Match                      |
| High             | 4        | Fully                 | Yes                            | Multiple Matches               |
| High             | 5        | Partially             | Yes - Multiple                 | One Match                      |
| High             | 6        | Partially             | Yes - Multiple                 | Multiple Matches               |
| High             | 7        | Partially             | Yes                            | One Match                      |
| High             | 8        | Fully                 | No                             | One Match                      |
| High             | 9        | No                    | Yes - Multiple                 | One Match                      |
| High             | 10       | No                    | Yes - Multiple                 | Multiple Matches               |
| Medium           | 1        | Fully                 | Yes - Multiple                 | Not Considered                 |
| Medium           | 2        | Fully                 | Yes                            | Not Considered                 |
| Medium           | 3        | Fully                 | No                             | Multiple Matches               |
| Medium           | 4        | Partially             | Yes - Multiple                 | Not Considered                 |
| Medium           | 5        | Partially             | Yes                            | Not Considered                 |
| Medium           | 6        | No                    | Yes                            | One Match                      |
| Medium           | 7        | No                    | Yes-Multiple                   | Not Considered                 |
| Medium           | 8        | Partially             | No                             | One Match                      |
| Medium           | 9        | No                    | Yes                            | Not Considered                 |
| Low              | 1        | Fully                 | No                             | No Matches                     |
| Low              | 2        | Partially             | No                             | Multiple Matches               |
| Low              | 3        | Partially             | No                             | No Matches                     |
| Low              | 4        | No                    | No                             | One Match                      |
| Low              | 5        | No                    | No                             | Multiple Matches               |

## Related information
[Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
