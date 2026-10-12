---
title: Use multi-circuit accounting [CZ]
description: Learn how to use multi-circuit accounting with the G/L Account Group field to separate financial, internal, and off-balance postings in the Czech version.
author: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.keywords: CZ, Czech, Localization, Finance  
ms.date: 10/08/2026
ms.reviewer: bholtorf
ms.author: bholtorf
ai-usage: ai-assisted
---

# Multi-circuit accounting in the Czech version

According to accounting standards, an accounting entity can post transactions within multiple internal accounting areas, known as *circuits*: **Financial Accounting**, **Internal Accounting**, and **Off-Balance Accounting**.

To set up the accounting area for a G/L account, use the **G/L Account Group** field on the account card. [!INCLUDE[prod_short](../../includes/prod_short.md)] prevents you from posting a single transaction with G/L accounts that belong to different circuits. If you try, you get the error message: "You cannot post an entry with accounts from different circuits."

## Set up the accounting area for a G/L account

1. Choose the **Tell Me** icon, enter **Chart of Accounts**, and then choose the related link.
1. Open the G/L account that you want to assign to a circuit.
1. In the **G/L Account Group** field, select **Financial Accounting**, **Internal Accounting**, or **Off-Balance Accounting**.

Transactions that involve only accounts from the same circuit post as usual. If you combine accounts from different circuits in the same journal batch, document, or document posting, [!INCLUDE[prod_short](../../includes/prod_short.md)] blocks the posting.

## Check already-posted entries

Use the **G/L Account Group Posting Check** report to find documents that were posted before the circuits were set up, or that otherwise mix G/L accounts from different circuits. Run the report from the G/L account card, specify a **From Date** and **To Date**, and review the resulting list of documents and entries for each affected posting date.

## Related information

- [Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
