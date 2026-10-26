---
title: Comply with Electronic Accounting Regulations in Mexico
description: This article explains how Business Central can assist with compliance regarding electronic accounting requirements in Mexico.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: compliance, electronic accounting requirements, electronic accounting
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Comply with electronic accounting regulations in Mexico

Use [!INCLUDE[prod_short](../../includes/prod_short.md)] to prepare XML files for Mexico's electronic accounting requirements. **Export Electr. Accounting** supports the following exports:

* The chart of accounts. This file is to be submitted whenever the chart of accounts is modified.  
* The trial balance, including opening balances, movements (debit/credit), and final balances.  
* All journal transactions, including all actual movements, such as purchases, sales, and so on. This file is to be submitted upon request from the authorities.
* Auxiliary accounts, with opening and closing balances and individual G/L entries for accounts with a SAT account code.

Learn about the structure of these files (also referred to as Annex 24) on the Secretaria de Gobernación website. Use **Export Electr. Accounting** to generate the files.

Confirm which files and submission deadlines apply to your company with SAT or your tax adviser.

## Set up data required to export successfully

Before you export, fill in **RFC Number** on **Company Information** and complete the setup described in this section. The export logs errors and warnings for missing or invalid data. Errors prevent the file from being downloaded. Fix the reported errors and run the export again. Warnings don't prevent the download, but review them before you submit the file.

For the files that contain the chart of accounts and the trial balance:

1. For each account, you must specify an account in the **SAT Account Code** field. Only accounts with a SAT account code are included in the files for the chart of accounts and trial balance.
1. For the chart of accounts export, set **Debit/Credit** to **Debit** or **Credit** on each included G/L account. **Both** isn't supported.

For the file that contains journal transactions:

* On the **Customer Bank Account Card**, **Vendor Bank Account Card**, and **Bank Account** pages you must choose a bank in the **Bank Code** field. It is required if the bank account is used in a transaction.
* On the **Customer Card** and **Vendor Card**, choose an account in the **Preferred Bank Account Code** field. The account is copied to **Recipient Bank Account** on the relevant journal lines. You can change the account before posting.
* The **Fiscal Invoice Number PAC** field on all purchase documents is used to register the UUID of an electronic invoice. You can import electronic invoices (response) when you create a purchase invoice, order, or credit memo. Only the UUID is imported, but this functionality can easily be expanded. After data is imported, it appears on the invoice after posting.
* In the **Payment Method** table, **SAT Payment Method Code** identifies how payment was made for the accounting export. This field is separate from **SAT Method of Payment**, which is used for CFDI invoicing. Ask your partner to help configure the accounting-export field if it isn't available on your page.

## Generate the XML files

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Export Electr. Accounting**, and then choose the related link.
1. Select **Export Type**: **Chart of Accounts**, **Trial Balance**, **Transactions**, or **Auxiliary Accounts**.
1. Enter the **Year** and **Month**.
1. Fill in the additional fields for the selected export type.

    |Export type|Additional information|
    |-----------|----------------------|
    |**Trial Balance**|Select **Normal** or **Complementary** in **Delivery Type**. For a complementary delivery, fill in **Update Date**. To include the year's closing entries, select **Closing Balance Sheet**. The export uses period 13 and doesn't require a month selection.|
    |**Transactions** or **Auxiliary Accounts**|Select **Request Type**. For **AF** or **FC**, fill in **Order Number**. For **DE** or **CO**, fill in **Process Number**.|

1. Select **Export** and save the XML file. If the export reports errors, correct the data and export again.

## Related information

[Mexico Local Functionality](mexico-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
