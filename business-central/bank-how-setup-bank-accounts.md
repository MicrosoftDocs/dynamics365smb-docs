---
title: Set Up Bank Accounts| Microsoft Docs
description: You can reconcile bank accounts in Financials with statements from the bank.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Yodlee, feed, stream
ms.date: 09/26/2017
ms.author: sgroespe

---
# Set Up Bank Accounts
You use bank accounts in the [!INCLUDE[d365fin](includes/d365fin_md.md)] to keep track of your banking transactions. Accounts can be denominated in your local currency or in a foreign currency. After you have set up bank accounts, you can also use the check printing option.

## To set up bank accounts
1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Accounts**, and then choose the related link.
2. In the **Bank Accounts** window, choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> To fill in the **Balance** field with an opening balance, you must post a bank account ledger entry with the amount in question. You can do this by performing a bank account reconciliation. For more information, see [Reconcile Bank Accounts Separately](bank-how-reconcile-bank-accounts-separately.md). Alternatively, you can implement the opening balance as a part of general data creation in new companies by using the **Migrate Business Data** assisted setup. For more information, see [Getting Started](product-get-started.md).

## To set up your bank account for import or export of bank files
Fields on the **Transfer** FastTab in the **Bank Account Card** window are related to import and export of bank feeds and files. For more information, see [Set Up the Bank Data Conversion Service](bank-how-setup-bank-data-conversion-service.md) and [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Accounts**, and then choose the related link.
2. Open the card for a bank account that you will export or import bank files for.
3. On the **Transfer** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
>   Different file export services and their formats require different setup values in the **Bank Account Card** window. You will be informed about wrong or missing setup values as you try to export the file. So read the short descriptions of the fields carefully or refer to the related procedure topics. For example, exporting a payment file for North American electronic funds transfer (EFT) requires that both the **Last Remittance Advice No.** field and the **Transit No.** field are filled in. For more information, see [Export Payments to a Bank File](payables-how-export-payments-bank-file.md).

## To set up vendor bank accounts for export of bank files
Fields on the **Transfer** FastTab in the **Vendor Bank Account Card** window are related to export of bank feeds and files. For more information, see [Set Up the Bank Data Conversion Service](bank-how-setup-bank-data-conversion-service.md) and [Export Payments to a Bank File](payables-how-export-payments-bank-file.md).

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Vendors**, and then choose the related link.
2. Open the card for a vendor whose bank account you will export payment bank files to.
3. Choose the **Bank Accounts** action.
3. In the **Vendor Bank Account Card** window, on the **Transfer** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## See Also
[Setting Up Banking](bank-setup-banking.md)  
[Managing Bank Accounts](bank-manage-bank-accounts.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
