---
title: Transfer bank funds
description: You can transfer amounts from one bank account to another, including different currencies, by posting the transaction in the general journal.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: bank account transfer, multiple currencies
ms.search.form: 39
ms.date: 07/25/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Transfer bank funds

You might sometimes need to transfer an amount from one bank account in [!INCLUDE[prod_short](includes/prod_short.md)] to another. To do this, you must post the transaction on the **General Journals** page. The task varies depending on whether the bank accounts use the same currency or different currencies.

## To post a transfer between bank accounts with the same currency code

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Journals**, and then choose the related link.
2. On a journal line, fill in the **Posting Date** and **Document No.** fields.
3. In the **Account Type** field, select **Bank Account**.
4. In the **Account No.** field, select the bank from which you want to transfer the funds.
5. In the **Amount** field, enter the amount to be transferred.

    Next, you must specify the balancing account. If you can't see the relevant fields, then choose the **Show More Columns** action to view all available fields.
6. In the **Bal. Account Type** field, select **Bank Account**.
7. In the **Bal. Account No.** field, select the bank account to which you want to transfer the funds.
8. Post the journal.

## To post a transfer between bank accounts with different currency codes

To transfer funds between bank accounts that use different currencies, you must post two general journal lines.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Journals**, and then choose the related link.
2. Create two journal lines, and fill in the **Posting Date** and **Document No.** fields.
3. On the first journal line, in the **Type** field, select **Bank Account**.
4. In the **Account No.** field, select the bank account from which you want to transfer the funds.
5. In the **Amount** field, enter the amount in the currency of the bank account with or without a minus sign.

    > [!TIP]
    > An amount without a sign is a debit, and an amount with a minus sign is a credit.

    > [!NOTE]
    > Some companies prefer to transfer between accounts on separate journal lines. Other companies prefer to post everything on one journal line by using a balancing account. Check with your local expert if you're not sure what to do.
    >
    > If your company prefers to use a balancing account, then set the **Bal. Account Type** field to **Bank Account**, and set the **Bal. Account No.** field to the bank account to which you want to transfer the funds. Then proceed to step 9 or 10.
    >
    > If your company prefers to use a separate journal line, then move on to the next step.
6. On the second journal line, in the **Type** field, select **Bank Account**.
7. In the **Account No.** field, select the bank account to which you want to transfer the funds.
8. In the **Amount** field, enter the amount in the currency of the bank account with or without a minus sign.

    > [!TIP]
    > An amount without a sign is a debit, and an amount with a minus sign is a credit.
9. If the exchange rates used in the journal are different than the exchange rates on the **Currency Exchange Rates** page, enter a new journal line for the exchange rate gain or loss.  

    1. Enter **G/L Account** in the **Account Type** field.  

    2. Enter the G/L account number for exchange rate gain or loss in the **Account No.** field.  

    3. Enter the exchange rate gain or loss in the **Amount** field with or without a minus sign.

    > [!TIP]
    > An amount without a sign is a debit, and an amount with a minus sign is a credit.
10. Post the journal.

## Related information

[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Setting Up Banking](bank-setup-banking.md)  
[Work with General Journals](ui-work-general-journals.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
