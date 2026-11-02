---
title: Finance Charge Terms Setup in Business Central
description: Set up finance charge terms in Business Central, assign them to customers, and configure interest, currency-specific fees, and memo text.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: payment due, debt, overdue, fee, charge
ms.search.form: 6, 494, 477, 445, 572
ms.date: 10/14/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Set up finance charge terms and memo text

Use finance charge terms to define how [!INCLUDE[prod_short](includes/prod_short.md)] calculates interest and extra fees for late customer payments. Assign the terms to customers, and then use them when you create finance charge memos.

Creating a memo calculates the charges. The **Post Interest** and **Post Additional Fee** settings determine whether the charges are posted to customer and general ledger accounts when you issue the memo. Learn more about creating and issuing memos in [Collect outstanding balances](receivables-collect-outstanding-balances.md#finance-charges).

## Set up finance charge terms

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Finance Charge Terms**, and select the related link.
2. Select **New**, and then enter a **Code** and **Description** for the terms.
3. In **Interest Calculation Method**, select **Average Daily Balance** or **Balance Due**. The next section describes these methods.
4. In **Interest Calculation**, select **Open Entries**, **Closed Entries**, or **All Entries** to specify which customer ledger entries to consider.
5. Enter **Interest Rate**. For **Average Daily Balance**, also enter a nonzero **Interest Period (Days)**.
6. Set **Grace Period** to determine when overdue entries qualify for charges. Set **Due Date Calculation** to calculate the memo's due date from its document date.
7. Set **Minimum Amount (LCY)** and **Additional Fee (LCY)** as needed.
8. Turn on **Post Interest** or **Post Additional Fee** if the corresponding charges should be posted when you issue the memo.
9. Close the card to return to the **Finance Charge Terms** list.

Create a separate code for each combination of conditions that you need. The minimum amount is an interest threshold in local currency (LCY), not an extra fee.

You also need the appropriate interest and additional-fee accounts in the customer's posting group. Learn more about posting accounts in [Set up posting groups](finance-posting-groups.md).

### Interest calculation methods

* **Average Daily Balance** accounts for how long amounts are overdue and for changes in the balance during the calculation period.
* **Balance Due** applies the interest percentage to the remaining overdue amount without prorating it by the number of overdue days.

For an unchanged overdue balance and a single interest rate, the basic calculations are:

| Method | Calculation |
|---|---|
| **Average Daily Balance** | Finance charge = overdue amount x overdue days / interest period in days x interest rate / 100. |
| **Balance Due** | Finance charge = overdue amount x interest rate / 100. |

Payments, previous interest calculations, and date-specific interest rates can affect the calculation. The grace period controls eligibility for charges. It doesn't mean that interest is calculated only from the end of the grace period.

To use rates that change over time, select the terms in the **Finance Charge Terms** list and use **Interest Rates**. The rate on the terms is used when no applicable date-specific rate is found. Learn more about rate schedules in [Set up multiple interest rates for delayed payment](finance-how-to-set-up-multiple-interest-rates.md).

## Assign terms to a customer

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers**, and select the related link.
2. Open the customer card.
3. On the **Payments** FastTab, select the terms in **Fin. Charge Terms Code**. If the field isn't visible, select **Show more**.

## Set extra fees in foreign currencies

Set **Additional Fee (LCY)** on the terms to a nonzero amount to add a fee, including fees defined in foreign currencies.

1. In the **Finance Charge Terms** list, select the terms and select **Currencies**.
2. On **Currencies for Fin. Chrg Terms**, enter **Currency Code** and **Additional Fee** for each currency that needs its own fee.
3. Close the page.

If you define a fee for the memo's currency, [!INCLUDE[prod_short](includes/prod_short.md)] uses that fee. Otherwise, [!INCLUDE[prod_short](includes/prod_short.md)] converts **Additional Fee (LCY)** to the memo's currency by using the exchange rate for the memo's **Posting Date**. The currency-specific setup changes the extra fee, not the interest rate or calculation method.

## Add beginning and ending text

You can add text before and after the charge lines on finance charge memos.

1. In the **Finance Charge Terms** list, select the terms and select **Beginning Text**.
2. On **Finance Charge Text**, enter one or more lines in **Text**.
3. Close the page and repeat with **Ending Text** if needed.

Use the following placeholders in **Text** to insert values from the memo or its terms.

| Placeholder | Value |
|---|---|
| `%1` | The memo's **Document Date**. |
| `%2` | The memo's **Due Date**. |
| `%3` | **Interest Rate** on the finance charge terms. |
| `%4` | The memo's **Remaining Amount**. |
| `%5` | The memo's **Interest Amount**. |
| `%6` | The memo's **Additional Fee**. |
| `%7` | The memo total: remaining amount, interest, additional fee, and VAT. |
| `%8` | The memo's **Currency Code**. |
| `%9` | The memo's **Posting Date**. |

If you change the text or memo lines after creating a memo, use **Update Finance Charge Text** on the unissued memo to refresh the text and substituted values.

## Related information

[Set up reminder terms and levels](finance-setup-reminders.md)  
[Set up finance](finance-setup-finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
