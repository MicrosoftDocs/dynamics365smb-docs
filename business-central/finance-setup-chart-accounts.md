---
title: Set Up the Chart of Accounts
description: You change the default accounts in the chart of accounts (COA), and you can add new accounts.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: COA, cha of acc
ms.date: 04/01/2020
ms.author: edupont

---
# Setting Up or Changing the Chart of Accounts
The chart of accounts shows the ledger accounts that store your financial data. [!INCLUDE[d365fin](includes/d365fin_md.md)] includes a standard chart of accounts that is ready to support your business.
However, you can change the default accounts, and you can add new accounts.
<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE43KO9?rel=0]


## Adding or Changing Accounts
From the chart of accounts, you can open each G/L account and add or change settings.

> [!NOTE]  
>   You can delete a general ledger account. However, before you delete it, the following must be true:  
>  
>   * The balance on the account must be zero.  
>   * The **Allow G/L Acc. Deletion Before** field must be set on the **General Ledger Setup** page, and the account must not have ledger entries on or after that date.  
>   * If the **Check G/L Account Usage** field on the **General Ledger Setup** page is selected, then the account must not be used in any posting groups or posting setup.  

[!INCLUDE[d365fin](includes/d365fin_md.md)] will prevent you from deleting a general ledger account that stores data that is needed in the chart of accounts.  

## See Related Training at [Microsoft Learn](/learn/modules/chart-accounts-dynamics-365-business-central/index)

## See Also
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Working with Dimensions](finance-dimensions.md)  
[Importing Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Work with Account Schedules](bi-how-work-account-schedule.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]
