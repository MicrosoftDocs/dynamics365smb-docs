---
title: Set Up or Change the Chart of Accounts (contains video)
description: Learn about setting up your chart of accounts (COA) to show the ledger accounts that store your financial data.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: conceptual
ms.search.keywords: COA, cha of acc
ms.search.form: 16, 17, 18, 118, 386, 391
ms.date: 12/19/2023
ms.custom: bap-template

---
# Set Up or Change the Chart of Accounts

The chart of accounts (COA) shows the ledger accounts that store your financial data. [!INCLUDE[prod_short](includes/prod_short.md)] includes a standard COA that is ready to support your business. You can, however, change the default accounts, and you can add new accounts.
<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE43KO9?rel=0]

## Add or change accounts

From the COA, you can open each general ledger (G/L) account and add or change settings. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] 

If necessary, you can use more than one line for a general ledger account name. On the **G/L Account Card** page, in the **Account** group, choose **Extended Texts**, and then fill in one or more lines with the account name and copied text.  

For accounts of the **Total** account type, you must fill in the **Totaling** field. For **End-Total** accounts, this field is filled in automatically by the Indent function. After you have set up all the accounts, choose the **Process** action, then choose **Indent Chart of Accounts**.  

> [!IMPORTANT]
> If you have entered definitions in the **Totaling** fields for **End-Total** accounts before executing the indent function, you must enter them again because the function overwrites the values in all **End-Total** fields.

## Delete accounts

You can delete a general ledger account. However, before you delete it, the following must be true:  

* The balance on the account must be zero.  
* The **Allow G/L Acc. Deletion Before** field must be set on the **General Ledger Setup** page, and the account must not have ledger entries on or after that date.  
* If the **Check G/L Account Usage** field on the **General Ledger Setup** page is selected, the account must not be used in any posting groups or posting setup.  

[!INCLUDE[prod_short](includes/prod_short.md)] prevents you from deleting a general ledger account that stores data that is needed in the chart of accounts.  

You can also specify when to allow people to delete accounts. On the **General Ledger Setup** page, the **Block Deletion of G/L Accounts** toggle works together with the date in the **Check G/L Acc. Deletion After** field to act as an extra validation. If you turn on the **Block Deletion of G/L Accounts** toggle, you can't delete G/L accounts with ledger entries after the date in the **Check G/L Acc. Deletion After** field. To delete such an account, someone with access to the **General Ledger Setup** page must turn off the **Block Deletion of G/L Accounts** toggle.  

Turning on the **Block Deletion of G/L Accounts** field is often a best practice, as is setting the date in the **Check G/L Acc. Deletion After** field, for example, to the date through which regulations require you to store finance data.  

### Video guidance

This video shows how to specify whether, and when, people can delete G/L accounts.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RW1g3oY]

## See Also

[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Work with Dimensions](finance-dimensions.md)  
[Importing Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Work with Financial Reports](bi-how-work-account-schedule.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Close Income Statement Accounts in the French Version](LocalFunctionality/France/how-to-close-income-statement-accounts.md)  
[Print Income Statements in the Australian Version](LocalFunctionality/Australia/how-to-print-income-statements.md)  
[Print Income Statements in the New Zealand Version](LocalFunctionality/NewZealand/how-to-print-income-statements.md)  
[Set Up and Close Income Statement Balances in the Spanish Version](LocalFunctionality/Spain/how-to-set-up-and-close-income-statement-balances.md)  
[Indent and Validate the Chart of Accounts in the Spanish Version](LocalFunctionality/Spain/how-to-indent-and-validate-chart-of-accounts.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
