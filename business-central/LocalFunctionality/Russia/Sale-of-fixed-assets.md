---
title: Selling fixed assets in Russia
description: Learn how to manage the sale or transfer of fixed assets in Russia, including local regulatory enhancements.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: selling fixed assets, fixed assets, Russia, sale of fixed assets, Russia
ms.date: 07/21/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Selling fixed assets

A sale or transfer of a fixed asset consists of two stages.

## Stage 1: Depreciation of fixed assets

1. Go to **Departments** > **Financial management** > **Fixed Assets** > **FA G/L Journals**.
1. Fill the journal lines:

   | Field | Description |
   |--|--|
   | Posting Date | Specifies the same date as the FA Posting Date field when the line is posted. |
   | Account Type | Fixed Asset |
   | Account No. | Fixed asset code to be depreciate |
   | Depreciation Book Code | Specifies the code for the depreciation book to which the line is posted |
   | FA Posting Type | Depriciation |
   | Amount | not fill |
   | Bal. Account Type | G/L Account |
   | Bal.Account No. | G/L Account for expenses related to the sale of fixed assets |
   | Depr. until FA Posting Date | Selected |

## Stage 2: Sale of fixed assets by the sales accounts

1. Go to **Financial management** > **Receivables** > **Invoices**
1. The fields in the document header are filled in the same way as the sales order fields.
1. Fill the lines:

   | Field | Description |
   |--|--|
   | Type | Fixed Asset |
   | No. | Fixed Asset Code |
   | Quantity | 1 |
   | Unit Price | Price of Fixed Asset |

1. Post the invoice.

## Related information

[Fixed Assets](fixed-assets.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
