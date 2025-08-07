---
title: Vendor tax agent scheme in Russia
description: Learn about vendor tax agent schemes in Russia, including enhancements for VAT processing and payment workflows.
author: DianaMalina
ms.topic: article
ms.search.keywords: vendor tax agent, tax agent scheme, VAT processing, payment workflow, vendor funds, VAT payment, Russia
ms.date: 07/22/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Vendor tax agent scheme

## VAT from internal funds

Fill in the fields on the vendor card.

1. **Agreement** FastTab:

    - Agreement posting - mandatory.

    - Agreement numbers required.

1. On the agreement card:

    - VAT Bus. Posting Group
    - VAT Agent Prod. Posting Group
    - VAT Payment Source Type - Internal Funds

## Prepayment and payment VAT

1. Create and release an invoice

    Agreement No. (with settings for Vendor with VAT Payment from internal funds) should be specified.

1. Create a line in Payment Journal:

    - Document Type - Payment
    - Prepayment - yes
    - Prepayment Document No is required.

1. Post lines of Journal

    Operations with VAT are automatically generated in rubles.

1. Create and post line in Payment Journal for Tax Authority with VAT Amount of prepayment.

1. Ship and post invoice.

1. Create a line in Payment Journal

    - Document Type - Payment
    - Initial Document No. - No. of posted invoice
    - Applies-to Doc. No. - No. of posted invoice

1. Create and post payment to the Tax Authority.
1. Go to VAT Settlement Worksheet. Post VAT (see [Settlement VAT](Settlement-VAT.md)).

## VAT from vendor funds

Fill the fields in Vendor Card.

1. On Agreement tab:

    - Agreement posting - mandatory.
    - Agreement Nos is required.

1. In Agreement card:

    - VAT Bus. Posting Group
    - VAT Agent Prod. Posting Group
    - VAT Payment Source Type - Vendor Funds

## Post prepayment and payment VAT

1. Create and release an invoice.

1. For the payment in the currency for the bank and in rubles for the vendor it's necessary to create two lines in the **payment journal**.

    - **For vendor:**

        - Posting Date,
        - Document Type - Payment
        - Prepayment - yes
        - Account Type - Vendor
        - Account No.
        - Agreement No.
        - Bal. Account Type - G/L Account
        - Bal. Account - " "
        - Currency Code - " "
        - Prepayment Document No. is required
        - Amount - in rubles

    - **For Bank:**

        - Posting Date,
        - Document Type - Payment
        - Prepayment - yes
        - Account Type - Bank Account
        - Account No.
        - Agreement No.
        - Bal. Account Type -  G/L Account
        - Bal. Account - " "
        - Currency Code
        - Amount - in USD/EUR

1. Post the lines of Journal.
1. Ship.

    You can change the Currency Code and Amount in the Invoice.

1. Post the invoice.

1. Apply Entry.

1. Go to VAT Settlement Worksheet. Post VAT (see [Settlement VAT](Settlement-VAT.md)).

    At the end of the period entries are formed as a result of revaluation of debt.

1. Create and post lines in Payment Journal.

    For the payment in the currency for the bank and in rubles for the vendor it's necessary to create two lines in the payment journal.

    - **For vendor:**

        - Posting Date
        - Document Type - Payment
        - Account Type - Vendor
        - Account No.
        - External Document No.
        - Internal Document No.
        - Agreement No.
        - Bal. Account Type - G/L Account
        - Bal. Account - " "
        - Currency Code - " "
        - Prepayment Document No. is required
        - Amount - in rubles

    - **For Bank:**

        - Posting Date,
        - Document Type - Payment
        - Account Type - Bank Account
        - Account No.
        - Agreement No.
        - Bal. Account Type -  G/L Account
        - Bal. Account - " "
        - Currency Code
        - Amount - in USD/EUR

## Related information

[Russia Local Functionality](russia-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
