---
    title: Basic Experience Extension | Microsoft Docs
    description: This extension is a modernized alternative to Microsoft Dynamics C5.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: C5, financials, extension
    ms.date: 04/01/2021
    ms.author: bholtorf


---
# The Basic Experience Extension
If you have been using Microsoft Dynamics C5, Microsoft partners can help you transition to a more modern solution that is based on [!INCLUDE[prod_short](includes/prod_short.md)], so you can continue to enjoy the same streamlined capabilities as Dynamics C5.

This extension is intended for small businesses and can support up to three users. If you need more users you must upgrade to a [!INCLUDE[prod_short](includes/prod_short.md)] license and uninstall this extension.

> [!NOTE]
> As of now, this extension is available only for customers in Denmark and Iceland. 

## What's Available
The following table describes the capabilities that are available if you install the Basic Experience extension.

|Area  |Functionality  |
|---------|---------|
|**General Ledger** |Basic Finance, Account Schedules, Fixed Assets, Bank Management, Bank Reconciliation, Payments, Direct Debit, Dimensions, Multiple Currencies, Budgets, Workflow, Document Management/OCR, Consolidation, Unlimited Companies|
|**Account Receivables/Sales** |Basic Receivables, Sales Invoicing, Sales Discounts, Pricing, Sales Tax, Contact Management |
|**Account Payables/Purchase** |Basic Payables, Purchase Invoicing |
|**Project Management** |Jobs, Job Pricing, Time Sheets, Assignment, Tasks, Resources |
|**Inventory** |Basic Inventory, Item Substitutions, Item Cross Reference |

## Getting Started
This extension is a bit different than most, and you will need help from a Microsoft partner to install and set it up. Just so that you know what to expect, here's a high-level view of what the Microsoft partner will do.

1. Create a new [!INCLUDE[prod_short](includes/prod_short.md)] tenant. This can be either a trial or a CSP version.
2. Add at least one user who is assigned to a Basic Experience license in your Azure Active Directory account.
3. Remove all companies, including the sample Cronus company.
4. Create a new company that does not contain any sample data or setups.
5. Add the **Demo RapidStart** package. <!--what does the pockage contain?-->
6. Download and install the Basic Experience extension from AppSource.

## Migrating Data
Bring your Dynamics C5 data along. After your Microsoft partner installs the Basic Experience extension you will have an empty company. An easy way to move your data from Dynamics C5 to Basic Experience is to use the C5 Data Migration extension, which is included in [!INCLUDE[prod_short](includes/prod_short.md)]. The extension migrates customers, vendors, items, and your general ledger accounts and their entries.

## See Also
[The C5 Data Migration Extension](ui-extensions-c5-data-migration.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]