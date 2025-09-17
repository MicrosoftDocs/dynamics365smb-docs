---
title: Compensation localization for Czech
description: Enables offsetting receivables and payables in Business Central for Czech companies, supporting mutual settlements between customers and vendors.
author: v-pejano
ms.topic: article
ms.search.keywords: Czech, Compensation, Finance, CZ, Cash
ms.date: 09/17/2025
ms.reviewer: bv-soumramani
ms.author: v-pejano
---

# Compensation localization for Czech (extension)

The Compensation solution helps companies for offsetting receivables and payables. Compensations are used when the company's customer is also its vendor.  
Entries to be counted can be entered manually or automatically from the Compensation Card. In addition, there are functions to mark entries to count and recalculating the balance.  
There's also a print-out of the Agreement on Mutual Settlement of Receivables and Payables under Czech legislation.

## Key features

- **View Balance as Vendor/Balance as Customer** – to view the balance as vendor on a customer card and the balance as customer on a vendor card, users must set a customer and vendor business relation with a contact to indicate to the system that even though particular company is registered as a vendor and as a customer, it is in fact the same company.
- **Compensation Setup** – Compensation Nos., Compensation Bal. Account No., etc.,
- **Compensation Card** – lines for compensation,
- Function - **Suggest lines for compensation**, Release,
- **Agreement on Mutual Settlement of Receivables and Payables** printout,
- **Compensation posting** – posted Compensation is created, entries application is posted.

## Compensation Setup

Before using the compensation app, it is necessary to set the basic parameters that relate to the bal. account number to which the credits are to be posted (Compensation Bal. Account). If necessary, it is also possible to set the maximum rounding amount for the compensation and the Debit Rounding Account and Credit Rounding Account.

![Compensation Setup](Media/Compensation-setup.png "Compensation Setup")

## Create Compensation

Follow the steps below to create compensation:

1. Choose the ![Lightbulb that opens the Tell me Feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Compensations** and choose the related link.
2. On **Compensations** page create with action **New** new compensation.
3. In the general section, fill in the fields for description, company type (customer/vendor/contact), company name and posting date.
4. Compensation lines can be set manually or by using action Propose compensation lines.

### Using action Propose compensation lines

1. Click on the Propose compensation lines function to open the Compensations Proposal tab
2. In this section, you select the customer document and the vendor document you want to use for compensation, to make a selection you need to click on Customer Ledger Entries where you will see the option to set or delete a mark (this way you mark specific invoices). You then repeat the same on the vendor side.
3. To add options to the rows, click OK
4. Then release the compensation using the Release action, print using the action Print and  send to the other side for signature.
5. The compensation can only be posted using the Post function after the other side has received the signed compensation
6. After posting, you can move to the posted compensation tab and print a mutual agreement to perform the compensation.

### Manual row settings

1. On the Compensations tab, go to the compensation rows and manually fill in the following fields: Source Type and Source Entry No.
2. Issue the compensation using action Release

## Checking the posted compensation

Follow the steps below to check the posted compensation:

1. Open the Posted Compensation.
2. Click on the Find Entries link.
3. This will open a page tab with a list of related entries, where you can check which accounts the compensation has been posted to by selecting G/L Entry.

## Related information

- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
