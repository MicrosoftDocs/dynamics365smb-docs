---
title: Understand the principles and lifecycle for Advance Payments  
description: This article explains the core principles and lifecycle of advance payments in the Czech version.  
author: v-pejano
ms.reviewer: v-pejano  
ms.author: v-pejano 
ms.service: dynamics-365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 09/17/2025  
ms.custom: bap-template 
---

# Understand the core principles and lifecycle of Advance Payments

This article explains the core principles and lifecycle of advance payments in the Czech version.

## Core principles

- Document matching happens at the **header level**. Invoice headers are matched to advance payment headers.  
- Advance payment settlements are posted using the **Advance Letter G/L Account** defined in the **Advance Letter Templates**.  
- Most actions related to advances are initiated directly from the corresponding **Adv. Letter Entries**. For example:
  - From a **Payment** type entry, you can post an **Payment VAT** or execute the **Unlink Advance Payment** function.
  - From a **VAT Payment** type entry, you can post a **Credit Memo VAT** (for reversal) or print the **Advance VAT Document**.  
- Posting an advance VAT document or credit memo doesn't generate a separate document header. Only entries in the **Advance Letter Entries**, from which the relevant VAT documents can be printed.  
- In the **General Journal** (or **Cash Receipt Journal**), the **Document Type** field must contain **Payment** for settling an advance. Also, the payment must be linked to the advance using the **Advance Letter No.** field.  
- Fields such as **Advance Letter No.** and **Adv. Letter Template Code** are available on customer and vendor ledger entries**, and the **Advance Letter No.** field is also present on **VAT Entries**.  
- In **VAT Entries**, advances post with the **VAT Calculation Type** field set to **Normal VAT**, and use the standard **Base** field for the VAT base amount.

## Advance payment lifecycle

The entire lifecycle of an advance is available from the **Sales (or Purchase) Advance Letter** page. The page lists all historical advance entries and you can access all related functions. For example, you can post VAT documents and credit memos, close an advance, run reports, and so on.

The **Status** field shows the current stage of the advance. For example, whether the advance is issued, paid, or applied.

![Advance Payment Principles](Media/adv-payments-principes.png)

1. When the advance is created, its **Status** is set to **New**.  
2. When the advance is issued, its **Status** changes to **To Pay**. An **Initial Entry** is created, and the advance is ready for settlement.  
3. When the advance is paid via cash or a general journal, its **Status** becomes **To Use**. The advance is ready to be applied to a final document. Payment and/or VAT payment entries are generated.  
4. When the advance is fully applied to an invoice, the **Status** is set to **Closed**.
5. If the advance isn't fully applied, you can close it manually. Doing so changes the **Status** to **Closed**, and the system generates **Close**, **VAT Close**, and reversing **Initial Entry** entries.

## Related information

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
