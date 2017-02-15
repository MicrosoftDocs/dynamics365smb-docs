---
title: 'How to: Import Payroll Transactions| Microsoft Docs'
description: Describes how to import salary payments and related transactions from your payroll provider into the general ledger.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/20/2016
ms.author: SorenGP

---
# How to: Import Payroll Transactions
To account for salary payments and related transactions, you must import and post financial transactions made by your payroll provider to the general ledger. To do this, you first import a file that you receive from the payroll provider into the **General Journal** window. Then you map the external accounts in the payroll file to the relevant G/L accounts. Lastly, you post the payroll transactions according to the account mapping.

**Note**: To use this functionality, an extension for payroll import must be installed and enabled. The Ceridian Payroll and the Quickbooks Payroll File Import extensions are pre-installed in [!INCLUDE[d365fin](includes/d365fin_md.md)]. For more information, see [Customizing [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] Using Extensions](ui-extensions.md).

## To import a payroll file
1. In the top right corner, choose the **Search for Page or Report** icon, enter **General Journals**, and then choose the related link.
2. In the relevant general journal batch, choose the **Import Payroll Transactions** action. An assisted setup guide opens.
3. Follow the steps in the **Import Payroll Transactions** window.

    **Tip**: In the step about mapping the external payroll records to your G/L accounts, the mappings that you make will be remembered next time the same records are imported. This will save you time as you do not have to manually fill in the **Account No.** field in the general journal every time you have imported recurring payroll transactions.   

    When you choose the **OK** button in the assisted setup guide, the **General Journal** window is filled with lines representing the transactions that the payroll file contains and with the relevant accounts prefilled in the **G/L Account** fields according to mappings you made in the guide.
4. Edit or post the journal lines as for any other general ledger transactions. For more information, see [How to: Work With General Journals](ui-work-general-journals.md).   

## See Also
[Finance](finance.md)  
[Customizing [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] Using Extensions](ui-extensions.md)  
[How to: Work With General Journals](ui-work-general-journals.md)  
