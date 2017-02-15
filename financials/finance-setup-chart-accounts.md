---
title: Setting Up the Chart of Accounts| Microsoft Docs
description: Describes how you can change the chart of accounts.
services: project-madeira
documentationcenter: ''
author: edupont04

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/12/2016
ms.author: edupont

---
# Setting Up or Changing the Chart of Accounts
The chart of accounts shows the ledger accounts that store your financial data. [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] includes a standard chart of accounts that is ready to support your business.
However, you can change the default accounts, and you can add new accounts.  

## Adding or Changing Accounts
From the chart of accounts, you can open each G/L account and add or change settings.

**Note**: You can delete a general ledger account. However, before you delete it, the following must be true:  

* The balance on the account must be zero.  
* The **Allow G/L Acc. Deletion Before** field must be set in the **General Ledger Setup** window, and the account must not have ledger entries on or after that date.  
* If the **Check G/L Account Usage** field in the **General Ledger Setup** window is selected, then the account must not be used in any posting groups or posting setup.  

Financials will prevent you from deleting a general ledger account that stores data that is needed in the chart of accounts.  

## See Also
[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Managing Bank Accounts](bank-manage-bank-accounts.md)  
[Dimensions](finance-dimensions.md)  
[Importing from Other Finance Systems](upload-data.md)  
[How to: Work With GIFI Codes in Canada](ca-finance-work-gifi-codes.md)  
[Working With [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](ui-work-product.md)  
