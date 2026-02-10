---
title: Basic Experience extension | Microsoft Docs
description: This extension is a modernized alternative to Microsoft Dynamics C5.
author: brentholtorf
ms.topic: article
ms.search.keywords: C5, financials, extension
ms.search.form: 20600, 
ms.date: 11/10/2023
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# The Basic Experience extension

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

If you have been using Microsoft Dynamics C5, Microsoft partners can help you transition to a more modern solution that is based on [!INCLUDE[prod_short](includes/prod_short.md)], so you can continue to enjoy the same streamlined capabilities as Dynamics C5.

This extension is intended for small businesses and can support up to three users. If you need more users, you must upgrade to a [!INCLUDE[prod_short](includes/prod_short.md)] license and uninstall this extension.

> [!NOTE]
> As of now, this extension is available only to customers in Denmark and Iceland.

## What's available

The following table describes the capabilities that are available if you install the Basic Experience extension.

|Area  |Functionality  |
|---------|---------|
|**General Ledger** |Basic finance, financial reports, fixed assets, bank management, bank reconciliation, payments, direct debit, dimensions, multiple currencies, budgets, workflow, document management/OCR, consolidation, unlimited companies|
|**Accounts Receivable/Sales** |Basic receivables, sales invoicing, sales discounts, pricing, sales tax, contact management |
|**Accounts Payable/Purchase** |Basic payables, purchase invoicing |
|**Project Management** |Jobs, job pricing, time sheets, assignments, tasks, resources |
|**Inventory** |Basic inventory, item substitutions, item cross reference |

## Getting started

This extension is a bit different than most, and you'll need help from a Microsoft partner to install and set it up. So that you know what to expect, here's a high-level view of what the Microsoft partner does.

1. Create a new [!INCLUDE[prod_short](includes/prod_short.md)] tenant. This can be either a trial or a Cloud Solution Provider (CSP) version.
2. Add at least one user who is assigned to a Basic Experience license in your Microsoft Entra account.
3. Remove all companies, including the sample Cronus company.
4. Create a new company that doesn't contain any sample data or setups.
5. Add the **Demo RapidStart** package. <!--what does the package contain?-->
6. Download and install the Basic Experience extension from Marketplace.

## Migrating data

Bring your Dynamics C5 data along. After your Microsoft partner installs the Basic Experience extension, you'll have an empty company. An easy way to move your data from Dynamics C5 to Basic Experience is to use the C5 Data Migration extension, which is included in [!INCLUDE[prod_short](includes/prod_short.md)]. The extension migrates customers, vendors, items, and your general ledger accounts and their entries.

## Related information

[The C5 Data Migration Extension](ui-extensions-c5-data-migration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
