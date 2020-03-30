---
title: Vendor tax agent scheme in Russia
description: Russian enhancements include vendor tax agent schemes.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Vendor Tax Agent Scheme

## VAT from Internal Funds

Fill in the fields on the vendor card.

1. **Agreement** FastTab:

    - Agreement posting - mandatory.

    - Agreement numbers required.

2. On the agreement card:

    - VAT Bus. Posting Group
    - VAT Agent Prod. Posting Group
    - VAT Payment Source Type - Internal Funds

## Prepayment and Payment VAT

1. Create and release an invoice

Agreement No. (with settings for Vendor with VAT Payment from internal funds) should be specified.

2. Create a line in Payment Journal:

    - Document Type - Payment
    - Prepayment - yes
    - Prepayment Document No is required.

3. Post lines of Journal

    Operations with VAT are automatically generated in rubles.

4. Create and post line in Payment Journal for Tax Authority with VAT Amount of prepayment.

5. Ship and post invoice.

6. Create a line in Payment Journal

    - Document Type - Payment
    - Initial Document No. - No. of posted invoice
    - Applies-to Doc. No. - No. of posted invoice

7. Create and post payment to the Tax Authority.
8. Go to VAT Settlement Worksheet. Post VAT (see [Settlement VAT](Settlement-VAT.md)).

## VAT from Vendor Funds

Fill the fields in Vendor Card.

1. On Agreement tab:

    - Agreement posting - mandatory.
    - Agreement Nos is required.

2. In Agreement card:

    - VAT Bus. Posting Group
    - VAT Agent Prod. Posting Group
    - VAT Payment Source Type - Vendor Funds

## Prepayment and Payment VAT

1. Create and release an invoice.

2. For the payment in the currency for the bank and in rubles for the vendor it is necessary to create two lines in the **payment journal**.

    **For vendor:**

        - Posting Date,
        - Document Type - Payment
        - Prepayment - yes
        - Account Type - Vendor
        - Account No.
        - Agreement No.
        - Bal. Account Type - G/L Account
        - Bal. Account - “ ”
        - Currency Code - “ “
        - Prepayment Document No. is required
        - Amount - in rubles

    **For Bank:**

        - Posting Date,
        - Document Type - Payment
        - Prepayment - yes
        - Account Type - Bank Account
        - Account No.
        - Agreement No.
        - Bal. Account Type -  G/L Account
        - Bal. Account - “ ”
        - Currency Code
        - Amount - in USD/EUR

3. Post the lines of Journal.
4. Ship.

    You can change the Currency Code and Amount in the Invoice.

5. Post the invoice.

6. Apply Entry.

7. Go to VAT Settlement Worksheet. Post VAT (see [Settlement VAT](Settlement-VAT.md)).

    At the end of the period will be formed entries as a result of revaluation of debt.

8. Create and post lines in Payment Journal.

    For the payment in the currency for the bank and in rubles for the vendor it is necessary to create two lines in the payment journal.

    **For vendor:**

        - Posting Date
        - Document Type - Payment
        - Account Type - Vendor
        - Account No.
        - External Document No.
        - Internal Document No.
        - Agreement No.
        - Bal. Account Type - G/L Account
        - Bal. Account - “ ”
        - Currency Code - “ “
        - Prepayment Document No. is required
        - Amount - in rubles

    **For Bank:**

        - Posting Date,
        - Document Type - Payment
        - Account Type - Bank Account
        - Account No.
        - Agreement No.
        - Bal. Account Type -  G/L Account
        - Bal. Account - “ ”
        - Currency Code
        - Amount - in USD/EUR

## See Also

[Russia Local Functionality](russia-local-functionality.md)  
