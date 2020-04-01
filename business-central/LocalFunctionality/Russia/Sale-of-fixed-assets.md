---
title: Selling fixed assets in Russia
description: Russian enhancements include managing sales or transfers of fixed assets.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Selling Fixed Assets

A sale or transfer of a fixed asset consists of two stages.

## Stage 1: Depreciation of fixed assets

1. Go to **Departments > Financial management > Fixed Assets > FA G/L Journals**.
2. Fill the journal lines:

| Field                       | Description                                                  |
| --------------------------- | ------------------------------------------------------------ |
| Posting Date                | Specifies the same date as the FA Posting Date field when the line is posted. |
| Account Type                | Fixed Asset                                                  |
| Account No.                 | Fixed asset code to be depreciate                            |
| Depreciation Book Code      | Specifies the code for the depreciation book to which the line will be posted |
| FA Posting Type             | Depriciation                                                 |
| Amount                      | not fill                                                     |
| Bal. Account Type           | G/L Account                                                  |
| Bal.Account No.             | G/L Account for expenses related to the sale of fixed assets |
| Depr. until FA Posting Date | Selected                                                     |

## Stage 2: Sale of fixed assets by the sales account

1. Go to **Financial management > Receivables > Invoices**
2. The fields in the document header are filled in the same way as the sales order fields.
3. Fill the lines:

| Field      | Description          |
| ---------- | -------------------- |
| Type       | Fixed Asset          |
| No.        | Fixed Asset Code     |
| Quantity   | 1                    |
| Unit Price | Price of Fixed Asset |

4. Post the invoice.

## See Also

[Fixed Assets](fixed-assets.md)  
