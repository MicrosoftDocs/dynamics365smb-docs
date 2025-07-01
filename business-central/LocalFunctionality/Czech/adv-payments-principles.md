---
title: Understanding Advance Payment Principles and Lifecycle  
description: This section explains the core principles and lifecycle of advance payments in the Czech localization extension.  
author: v-pejano

ms.service: dynamics365-business-central  
ms.topic: article  
ms.search.keywords: Czech, Advance Payments, Localization  
ms.date: 10/01/2021  
ms.reviewer: v-pejano  
ms.author: v-pejano  
---

# Understanding the Core Principles of Advance Payments and Their Lifecycle

## Core Principles of the Advance Payment Functionality

- Document matching is performed at the **header level** – invoice headers are matched to advance payment headers.  
- Advance payment settlements are posted using the **Advance Letter G/L Account** defined in the **Advance Letter Templates**.  
- Most actions related to advances are initiated directly from the corresponding **Adv. Letter Entries**. For example:
  - From a **Payment** type entry, you can post an **Payment VAT** or execute the **Unlink Advance Payment** function.
  - From a **VAT Payment** type entry, you can post a **Credit Memo VAT** (for reversal) or print the **Advance VAT Document**.  
- Posting an advance VAT document or credit memo does not generate a separate document header – only entries in the **Advance Letter Entries**, from which the relevant VAT documents can be printed.  
- In the **General Journal** (or **Cash Receipt Journal**), only the **Document Type** = *Payment* must be specified for settling an advance, and the payment must be linked to the advance using the **Advance Letter No.** field.  
- New fields such as **Advance Letter No.** and **Adv. Letter Template Code** are available on **Customer/Vendor Ledger Entries**, and **Advance Letter No.** is also present on **VAT Entries**.  
- In **VAT Entries**, advances are posted with **VAT Calculation Type** = *Normal VAT*, using the standard **Base** field for the VAT base amount.

## Advance Payment Lifecycle

The entire lifecycle of an advance is available from a single location – the **Sales (or Purchase) Advance Letter** card. Here, you can see all historical advance entries and access all related functions, including posting VAT documents, credit memos, closing the advance, running reports, and more.

The current stage of the advance – whether it is issued, paid, or applied – is reflected in the **Status** field.

![Advance Payment Principles](Media/adv-payments-principes.png)

1. When the advance is created, its **Status** is set to *New*.  
2. When the advance is issued, its **Status** changes to *To Pay*. An initial **Initial Entry** is created, and the advance is ready for settlement.  
3. When the advance is paid via cash or general journal, its **Status** becomes *To Use*. The advance is ready to be applied to a final document. **Payment** and/or **VAT Payment** entries are generated.  
4. When the advance is applied to an invoice, the **Status** is set to *Closed* (if fully applied).
5. If the advance is not (or not fully) applied, it can be manually closed. Doing so changes the **Status** to *Closed*, and the system generates **Close**, **VAT Close**, and reversing **Initial Entry** entries.

## See Also

[Advance Payments for Czech Republic (Extension)](ui-extensions-advance-payments-localization-cz.md)  
[Czech Local Functionality](czech-local-functionality.md)  
[Finance](../../finance.md)
