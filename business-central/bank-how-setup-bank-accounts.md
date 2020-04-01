---
title: Set Up Bank Accounts| Microsoft Docs
description: You can reconcile bank accounts with statements from the bank.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Yodlee, feed, stream
ms.date: 04/01/2020
ms.author: sgroespe

---
# Set Up Bank Accounts
You use bank accounts in the [!INCLUDE[d365fin](includes/d365fin_md.md)] to keep track of your banking transactions. Accounts can be denominated in your local currency or in a foreign currency. After you have set up bank accounts, you can also use the check printing option.<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE3Vhpl?rel=0]

## To set up bank accounts
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. On the **Bank Accounts** page, choose the **New** action.
3. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> To fill in the **Balance** field with an opening balance, you must post a bank account ledger entry with the amount in question. You can do this by performing a bank account reconciliation. For more information, see [Reconcile Bank Accounts](bank-how-reconcile-bank-accounts-separately.md). Alternatively, you can implement the opening balance as a part of general data creation in new companies by using the **Migrate Business Data** assisted setup guide. For more information, see [Getting Started](product-get-started.md).

## To set up your bank account for import or export of bank files
Fields on the **Transfer** FastTab on the **Bank Account Card** page are related to import and export of bank feeds and files. For more information, see [Using the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md) and [Set Up the Envestnet Yodlee Bank Feeds Service](bank-how-setup-bank-statement-service.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.
2. Open the card for a bank account that you will export or import bank files for.
3. On the **Transfer** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
>   Different file export services and their formats require different setup values on the **Bank Account Card** page. You will be informed about wrong or missing setup values as you try to export the file. So read the short descriptions of the fields carefully or refer to the related procedure topics. For example, exporting a payment file for North American electronic funds transfer (EFT) requires that both the **Last Remittance Advice No.** field and the **Transit No.** field are filled in. For more information, see [Export Payments to a Bank File](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).

## To set up vendor bank accounts for export of bank files
Fields on the **Transfer** FastTab on the **Vendor Bank Account Card** page are related to export of bank feeds and files. For more information, see [Using the AMC Banking 365 Fundamentals extension](ui-extensions-amc-banking.md) and [Export Payments to a Bank File](finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. Open the card for a vendor whose bank account you will export payment bank files to.
3. Choose the **Bank Accounts** action.
3. On the **Vendor Bank Account Card** page, on the **Transfer** FastTab, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## See Also
[Setting Up Banking](bank-setup-banking.md)  
[Setting Up Posting Groups](finance-posting-groups.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
