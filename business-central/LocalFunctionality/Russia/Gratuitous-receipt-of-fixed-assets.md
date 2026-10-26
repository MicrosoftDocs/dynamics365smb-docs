---
title: Gratuitous receipts in Russia
description: Russian localization features support the processing of gratuitous receipt of fixed assets.
author: DianaMalina
ms.topic: article
ms.search.keywords: gratuitous receipt, fixed assets, Russia
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Gratuitous receipt of fixed assets

Posting gratuitous receipt of fixed assets operation is registered in one of the sections of the Ledger journal for fixed assets:

1. Search for **Fixed Asset G/L Journals**, and open the page.
1. Fill the journal lines:

   | Field | Description |
   |--|--|
   | Posting Date | Enter the transaction date. Financial transactions and operations with fixed assets are generated on the same date. |
   | Document No. | Depending on the settings of the journal section, the document number is entered manually or filled in automatically. |
   | Document Type | Not fill |
   | Account Type | Fixed Asset |
   | Account No. | Code of Fixed Asset |
   | Depreciation Book Code | Specify the code of the depreciation book in which the Acquisition of fixed assets is posted. |
   | FA Posting Type | Acquisition Cost |
   | Description | You must enter a brief description of the business transaction. This description is reflected in all transaction books and statements of transactions. |
   | Amount | Enter the amount of the transaction with the "+ " sign. |
   | Bal. Account Type | G/L Account |
   | Bal. Account No. | G/L Account for accounting of deferred income. |
   | TAX Difference Code | Tax difference code for the acquisition of fixed assets. |

1. Post the line.

   > [!NOTE]
   > Confirm whether the gratuitous receipt is eligible for a depreciation bonus under the rules that apply to your organization. If it isn't eligible, exclude the acquisition entry from the depreciation bonus base.

1. If the option **Create Acquis. FA Tax Ledger** turned off in **TAX Register Setup**, then the value of the fixed asset issued in this way isn't reflected in the depreciation book for tax accounting. Therefore, it's necessary to form an additional operation in **FA Journals**.
1. Fill the line **FA Journals**.

   | Field | Description |
   |--|--|
   | Posting Date | Enter the transaction date. Financial transactions and operations with fixed assets will be generated on the same date. |
   | Document No. | Depending on the settings of the journal section, the document number is entered manually or filled in automatically. |
   | Document Type | Not fill |
   | Account Type | Fixed Asset |
   | FA No. | Code of Fixes Asset |
   | Depreciation Book Code | Specify the code of the depreciation book in which the Acquisition of fixed assets is posted. |
   | FA Posting Type | Acquisition Cost |
   | Description | You must enter a brief description of the business transaction. This description is reflected in all transaction books and statements of transactions. |
   | Amount | Enter the amount of the transaction with the "+" sign. |

1. As a result of posting **FA Journals**, an acquisition entry is generated in the fixed asset Ledger for the depreciation book for tax accounting.

## Related information

[Fixed Assets](fixed-assets.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
