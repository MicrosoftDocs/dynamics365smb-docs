---
title: Electronic accounting regulations in Mexico
description: This article explains how Business Central can assist with compliance regarding electronic accounting requirements in Mexico.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: compliance, electronic accounting requirements, electronic accounting
ms.date: 02/25/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Comply with electronic accounting regulations in Mexico

In Mexico, individuals and businesses must do their bookkeeping electronically and forward their monthly results to the Mexican Tax Authorities (SAT) as separate XML files at the end of each month. The XML files must contain the following items:

* The chart of accounts. This file is to be submitted whenever the chart of accounts is modified.  
* The trial balance, including opening balances, movements (debit/credit), and final balances.  
* All journal transactions, including all actual movements, such as purchases, sales, and so on. This file is to be submitted upon request from the authorities.

Learn about the structure of these files (also referred to as Annex 24) on the Secretaria de Gobernación website. The **Export Elect. Accounting** functionality is developed to meet this regulatory requirement.

## Set up data required to export successfully

To export the G/L balance information successfully, you must first set up certain data. Missing data results in a warning message that some mandatory fields are blank, but the export isn't canceled. If in doubt, you can submit the file to the authorities to get more details about the missing values. The fields to fill in before you export the XML files are as follows.

For the files that contain the chart of accounts and the trial balance:

1. For each account, you must specify an account in the **SAT Account Code** field. Only accounts with a SAT account code are included in the files for the chart of accounts and trial balance.
1. Every G/L account that is used for export must be defined as either **Debit** or **Credit**. You can't choose the **Both** option.

For the file that contains journal transactions:

* On the **Customer Bank Account Card**, **Vendor Bank Account Card**, and **Bank Account** pages you must choose a bank in the **Bank Code** field. It is required if the bank account is used in a transaction.
* On the **Customer** and **Vendor** pages, you must choose an account in the **Preferred Bank Account** field. When you set a preferred bank account for a customer or vendor, it is automatically copied to the Recipient Bank Account field whenever you make a payment to a vendor or create a cash receipt from a customer. This default value can be changed on the journal lines before posting.
* The **Fiscal Invoice Number PAC** field on all purchase documents is used to register the UUID of an electronic invoice. You can import electronic invoices (response) when you create a purchase invoice, order, or credit memo. Only the UUID is imported, but this functionality can easily be expanded. After data is imported, it appears on the invoice after posting.
* On the **Payment Method** page, in the **SAT Method of Payment** field you must specify how payment was made.

## Generate the XML files

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Export Elect. Accounting**, and then choose the related link.
1. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

## Related information

[Mexico Local Functionality](mexico-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
