---
title: Gratuitous receipts in Russia
description: Russian enhancements include gratuitous receipt of fixed assets.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---
# Gratuitous Receipt of Fixed Assets.

Posting gratuitous receipt of fixed assets operation is registered in one of the sections of the Ledger journal for fixed assets:

1. Go to **Financial management > Fixed Assets > Journals > FA G/L Journals**

2. Fill the journal lines:

| Field                  | Description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| Posting Date           | Enter the transaction date. Financial transactions and operations with fixed assets will be generated on the same date. |
| Document No.           | Depending on the settings of the journal section, the document number is entered manually or filled in automatically. |
| Document Type          | Not fill                                                     |
| Account Type           | Fixed Asset                                                  |
| Account No.            | Code of Fixed Asset                                          |
| Depreciation Book Code | Specify the code of the depreciation book in which the Acquisition of fixed assets is posted. |
| FA Posting Type        | Acquisition Cost                                             |
| Description            | You must enter a brief description of the business transaction. This description will be reflected in all transaction books and statements of transactions. |
| Amount                 | Enter the amount of the transaction with the "+ " sign.      |
| Bal. Account Type      | G/L Account                                                  |
| Bal. Account No.       | G/L Account for accounting of deferred income.               |
| TAX Difference Code    | Tax difference code for the acquisition of fixed assets.     |

3. Post the line.

> [!NOTE]
> Since the fixed asset was not acquired by the organization, it does not have the right to apply a depreciation bonus for such an asset. Therefore, if the company enjoys the right of application of the depreciation bonus should exclude the cost of acquisition of the asset from the calculation base for the depreciation bonus.

4. If the option **Create Acquis. FA Tax Ledger** turned off in **TAX Register Setup**, then the value of the fixed asset issued in this way is not reflected in the depreciation book for tax accounting. Therefore, it is necessary to form an additional operation in **FA Journals**.
5. Fill the line **FA Journals**.

| Field                  | Description                                                  |
| ---------------------- | ------------------------------------------------------------ |
| Posting Date           | Enter the transaction date. Financial transactions and operations with fixed assets will be generated on the same date. |
| Document No.           | Depending on the settings of the journal section, the document number is entered manually or filled in automatically. |
| Document Type          | Not fill                                                     |
| Account Type           | Fixed Asset                                                  |
| FA No.                 | Code of Fixes Asset                                          |
| Depreciation Book Code | Specify the code of the depreciation book in which the Acquisition of fixed assets is posted. |
| FA Posting Type        | Acquisition Cost                                             |
| Description            | You must enter a brief description of the business transaction. This description will be reflected in all transaction books and statements of transactions. |
| Amount                 | Enter the amount of the transaction with the "+ " sign.      |

6. As a result of posting **FA Journals**, an acquisition entry is generated in the fixed asset Ledger for the depreciation book for tax accounting.

## See Also

[Fixed Assets](fixed-assets.md)
