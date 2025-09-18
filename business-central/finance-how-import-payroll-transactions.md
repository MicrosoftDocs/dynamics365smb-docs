---
title: Import payroll transactions
description: To manage salary, you import and post financial transactions from your payroll provider to the general ledger, using a payroll extension such as Ceridian.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Ceridian, Quickbooks, salary
ms.search.form: 1660, 1661, 36601
ms.date: 08/09/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Import payroll transactions

To account for salary payments and related transactions, you must import and post financial transactions made by your payroll provider to the general ledger. To do this, you first import a file that you receive from the payroll provider into the **General Journal** page. Then you map the external accounts in the payroll file to the relevant G/L accounts. Lastly, you post the payroll transactions according to the account mapping.

> [!NOTE]  
> To use this functionality, an extension for payroll import must be installed and enabled. The Ceridian Payroll and the Quickbooks Payroll File Import extensions are pre-installed in [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md).

## To import a payroll file

1. [!INCLUDE[open-search](includes/open-search.md)], enter **General Journals**, and then choose the related link.
2. In the relevant general journal batch, choose the **Import Payroll Transactions** action. An assisted setup guide opens.
3. Follow the steps on the **Import Payroll Transactions** page.

    > [!TIP]  
    >   In the step about mapping the external payroll records to your G/L accounts, the mappings that you make will be remembered next time the same records are imported. This will save you time as you do not have to manually fill in the **Account No.** field in the general journal every time you have imported recurring payroll transactions.   

    When you choose the **OK** button in the assisted setup guide, the **General Journal** page is filled with lines representing the transactions that the payroll file contains and with the relevant accounts prefilled in the **G/L Account** fields according to mappings you made in the guide.
4. Edit or post the journal lines as for any other general ledger transactions. For more information, see [Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).   

## Related information

[Finance](finance.md)    
[Customizing [!INCLUDE[prod_short](includes/prod_short.md)] Using Extensions](ui-extensions.md)    
[Work with General Journals](ui-work-general-journals.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
