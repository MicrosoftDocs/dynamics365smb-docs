---
title: Finance - Czech local functionality
description: Learn about Czech-specific finance features in Business Central, including corrections posting, statutory reporting, and tools to help you track and manage your company's finances.
author: v-pejano
ms-service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: CZ, Czech, Finance, Posting
ms.date: 06/02/2025
ms.reviewer: v-soumramani
ms.author: v-pejano
---

# Finance in the Czech version

In the Czech Republic, you can track and manage your finances with these specific [!INCLUDE[prod_short](../../includes/prod_short.md)] features.

## Corrections posting (Red Storno)

According to legal requirements, costs and revenues are typically only posted to either the debit or credit side of a general ledger (G/L) account. Companies in Eastern Europe usually enforce accounting policies requiring you to post certain inventory and G/L transactions as corrections. The reason for this is that auditors and revenue authorities conduct accounting controls against this rule.  

The purpose of the corrections posting feature is to allow the:

- Accounting manager to enforce corrective posting on desired G/L accounts.  
- Accounting manager to enforce corrective posting in inventory postings (such as negative transfer entries and expected costs posting).  
- Accounting manager to enforce corrective posting of canceling in fixed assets.
- User to enforce corrective posting with one select (in G/L, inventory, and project postings).  

## Statutory company information

Many documents are circulating within and outside company structures. Local legislations set the minimum statutory requirements for such documents. It's possible to divide such requirements into roughly three groups:

- Company officials' names must be present on some internal and external documents.
- Document footers, which most external documents must contain, consists of basic company information, usually in the company's partner language.
- Registration numbers must be visible in internal and external documents.

This statutory company information feature provides a solution for each group requirement. You can:

- Define company officials and designate them as General Manager, Accounting Managers, and Finance Managers for use in internal and external documents.
- Define document footers in different languages, which can be used on different reports and documents.
- Store additional company registration numbers and other registration information on the **Company Information** page for use in documents.

## Internal financial documents

Users perform general ledger operations and must have the capability to print documents for these operations, in a layout in compliance with legal requirements. You might also want to print a document for posted general ledger operations. For these reasons, this internal financial documents feature provides the following reports:

- General Journal – Test Report - Used to print documents from G/L journals.
- General Ledger Document Report - Used to print posted general ledger operations.

## Accounting output documents  

In order to comply with legislation, reporting features, and local reporting practices of Czech companies, this feature provides the following reports:

- General journal
- General ledger
- Accounting sheets
- Turnover report by global dimension
- Open G/L entries to date
- Inventory account to date
- Joining bank account adjustment
- Joining G/L account adjustment
- G/L value-added tax (VAT) reconciliation
- All payments on hold
- Open customer entries at date
- Open vendor entries at date
- Fiscal year balance – standard adjusted report 
- Trial balance by period – standard adjusted report 

## Financial reports

As one of the most extensively used features for analysis and reporting, Eastern European countries/regions often ask for the following improvements of the standard financial reports feature:

- Common list of expressions – This capability creates named lines for use in formulas in all financial reports. This is achieved by defining one of the financial reports as a common list of expressions called a *shared financial report.*
- Saving results (current state) of analysis – This improvement enables you to store results of analysis to use later in financial reports, modification of results, and the retrieval of results.
- Formula drill-down – With this capability you can drill down on the results of formulas, including totaling type formulas. When you drill down on the result of a formula, you see a new page containing the list of elements used to calculate the results and their description.
- Additional data sources – In addition to being able to perform analysis on G/L entries, now you can also perform analysis on VAT, customer, vendor, and value entries.

## Statutory statements

Companies must create financial statements according to accounting law 563/1991, specifically the balance sheet, and the profit and loss statement. The statutory statements feature enables the creation of those reports:

- Balance sheet
- Income statement

These reports use the financial report feature with the statement structure defined.

The **Acc. Schedule Name** table contains this new field in the Czech version:

- **Acc. Schedule Type** – Balance sheet or income statement option

The **Acc. Schedule Line** table contains these new fields in the Czech version:

- **Row Correction** – Links to another line for balance sheet setup.
- **Assets/Liabilities Type** – Assets or liabilities for balance sheet setup.
- **Calc** – Always, never, when positive, and when negative options.

Users typically want to map defined balance sheet and profit and loss statements to Microsoft Excel file templates with the necessary design for a statement printout. This feature provides the new setup of Excel templates and statement file mapping so you can export financial report data to Excel files.

## WIP extended posting

The Czech legal work in progress (WIP) posting scheme includes the following new general ledger accounts:

- Consumption account
- Change in inventory of WIP account
- Change in inventory of product account  

With the WIP extended posting feature, you can correctly perform Czech WIP and production posting. That means you can set up a combination location and inventory posting group for the consumption, work in progress, change of semi-finished product, and change of product accounts.

This new posting scheme is used in the following transactions:

- Consumption posting in the consumption journal
- Posting the costs of capacities in the output journal
- Finishing orders and automatic production reporting

## Additional finance features

Use the following table to learn more about additional finance features available for the Czech Republic.

| Article | Description |
|:-|:-|
| [Year closing operations](year-close-operations.md) | Helps you close or open the required account books to comply with accounting legislation at the end of the fiscal year. |
| [General ledger entries application](general-ledger-entries-application.md) | In addition to the application of customer and vendor ledger entries, the general ledger entries application are also introduced. With it, you can work with temporary and transfer accounts in the general ledger. |
| [Exchange rate updating](exchange-rate-update.md) | Makes it possible to automatically update currency exchange rates from the external service provided by the ČNB (Czech National Bank). |

## Related information

[Czech Local Functionality](czech-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
