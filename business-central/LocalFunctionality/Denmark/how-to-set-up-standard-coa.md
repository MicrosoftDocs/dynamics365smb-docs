---
title: Standard chart of accounts in Denmark
description: This article explains how to set up a standard chart of accounts in Denmark.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: chart of accounts, Denmark, standard chart of accounts
ms.search.form: 5264, 5266, 5267, 5270
ms.date: 12/16/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Standard chart of accounts in Denmark

The new Danish bookkeeping act requires the use of a standard chart of accounts. Because of this requirement, the Danish tax authority is providing a standard chart of accounts that can be used. Use the chart of accounts when you prepare annual accounts, and when you calculate regular tax and value-added tax (VAT) payments. You can use any chart of accounts that's included on the **Chart of Accounts** page. However, for required reporting, you must use the **G/L Mapping** page to map all general ledger (GL) accounts with the standard chart of accounts that's required by the law.

## Set up a standard chart of accounts

GL accounts require a specific standard chart of accounts for use in Denmark. Before you start, make sure that you install the **Audit Files Extension** Microsoft app. After you configure your GL accounts, your exported files (Standard Audit File for Tax \[SAF-T\] and Regnskab Basis) are based on the configured mappings. To configure a standard chart of accounts, provide the GL account as explained in [Audit file export](../../finance-how-to-export-audit-files.md).

> [!NOTE]
> In accordance with Danish government regulations, new standard accounts and tax codes are required for the year 2025. To configure SAF-T reporting with these new standards, open the **SAF-T Setup Guide** page. Then, select **Standard Account 2025** from the **Standard Account Type** drop-down menu. The setup guide helps you map your accounts to the new standard accounts and apply the newly imported tax codes to the VAT Posting Setup for SAF-T.

Learn more in [Danish Local Functionality](denmark-local-functionality.md), which provides a list of features that are specific to Denmark.

## Related information

- [Financial Management](../../finance.md)  
- [Understanding the General Ledger and Chart of Accounts](../../finance-general-ledger.md)  
- [Work with Dimensions](../../finance-dimensions.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
