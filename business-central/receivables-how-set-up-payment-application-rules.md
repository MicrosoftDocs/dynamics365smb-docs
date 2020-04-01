---
title: Use Automatic Application to Reconcile Payments | Microsoft Docs
description: On the Payment Application Rules page, you set up rules to govern how payments/bank transactions should be automatically applied to their related open ledger entries when you use the Apply Automatically function on the Payment Reconciliation Journal page.

author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.date: 04/01/2020
ms.author: sgroespe

---
# Set Up Rules for Automatic Application of Payments
On the **Payment Application Rules** page, you set up rules to govern how payment text (on a bank transaction) is automatically matched with text on open entries in the following two processes:
- Automatically apply payments to their related open (unpaid) invoices, credit memos, or other entries when you use the **Apply Automatically** function on the **Payment Reconciliation Journal** page. For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).

- Automatically match bank transactions with their related, internal bank account ledger entries when you choose the **Match Automatically** action on the **Bank Acc. Reconciliation** page. For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md).

You set up new payment application rules by choosing which types of data on a payment reconciliation journal line must match with data on one or more open entries before the related payment is automatically applied to the open entries. The quality of each automatic application is shown as a value of **Low** to **High** in the **Match Confidence** field on the **Payment Reconciliation Journal** page according to the payment application rule that was used.

Each row on the **Payment Application Rules** page represents a payment application rule. Rules are applied in the order specified by the **Sorting Order** field. If multiple rules are used simultaneously, then the match confidence of the highest sorted rule is used.

The automatic application function is based on prioritized matching criteria. First the function tries, in prioritized order, to match text in the five **Related-Party** fields on a journal line with text in the bank account, name, or address of customers or vendors with unpaid documents representing open entries. Then, the function tries to match text in the **Transaction Text** and **Additional Transaction Info** fields on a journal line with text in the **External Document No.** and **Document No.** fields on open entries. Last, the function tries to match the amount in the **Statement Amount** field on a journal line with the amount on open entries.

> [!NOTE]
> Text matching is only possible for text longer than four characters.

In addition to the matching criteria, the following applies concerning the sign of the payment amount:

- For negative amounts, a match is made first against open entries representing customer invoices and then against vendor credit memos.
- For positive amounts, a match is made first against open entries representing vendor invoices and then against customer credit memos.

## To set up a payment application rule
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Application Rules**, and then choose the related link.
2. Define a new or edited payment application rule by filling the fields on a line as described in the following table.

|Field|Description|
|-|-|
|**Match Confidence**|Specifies your confidence in the application rule that you define on the line. <br /></br>A value that you specify in this field is shown in the **Match Confidence** field on the **Payment Reconciliation Journal** page according to the quality of the automatic payment application on the journal line.|
|**Priority**|Specifies the priority of the application rule relative to other application rules that are defined as lines on the **Payment Application Rules** page. 1 represents the highest priority.|
|**Related Party Matched**|Specifies how much information about the customer or vendor, such as address, city name, and bank account number, on the payment reconciliation journal line must match with information about the open entry before the application rule will be used to automatically apply the payment to the open entry.|
|**Doc. No./Ext. Doc. No. Matched**|Specifies if text on the payment reconciliation journal line must match with the value in the **Document No.** field or the **External Document No.** field on the open entry before the application rule will be used to automatically apply the payment to the open entry.|
|**Amount Incl. Tolerance Matched**|Specifies how many entries for a customer or vendor must match the amount including payment tolerance before the application rule will be used to automatically apply a payment to the open entry.|

The following table shows which payment application rules are set up in the generic version of [!INCLUDE[d365fin](includes/d365fin_md.md)].

> [!Important]
> The payment application rules may be different in your implementation of [!INCLUDE[d365fin](includes/d365fin_md.md)].

| Match Confidence | Priority | Related Party Matched | Doc. No./Ext. Doc. No. Matched | Amount Incl. Tolerance Matched |
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

## See Related Training at [Microsoft Learn](/learn/modules/reconciliation-journals-dynamics-365-business-central/index)

## See Also
[Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md)  
[Managing Receivables](receivables-manage-receivables.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
