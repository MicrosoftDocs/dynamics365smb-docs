---
title: Set Up the Chart of Accounts (contains video)
description: The chart of accounts shows the ledger accounts that store your financial data. You can change the default accounts in the COA, and you can add new accounts.
author: edupont04


ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: COA, cha of acc
ms.search.form: 16, 17, 18, 118, 386, 391
ms.date: 01/21/2022
ms.author: edupont

---
# Set Up or Change the Chart of Accounts

The chart of accounts shows the ledger accounts that store your financial data. [!INCLUDE[prod_short](includes/prod_short.md)] includes a standard chart of accounts that is ready to support your business.
However, you can change the default accounts, and you can add new accounts.
<br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE43KO9?rel=0]

## Add or change accounts

From the chart of accounts, you can open each G/L account and add or change settings. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

If necessary, you can use more than one line for a general ledger account name. In the **G/L Account Card** page, in the **Account** group, choose **Extended Texts**, and then fill in one or more lines with the text that is to be copied and the account name.  

For accounts of the **Total** account type, you must fill in the **Totaling** field. For **End-Total** accounts, this field is filled in automatically by the Indent function. After you have set up all the accounts, choose the **Process** action,and then choose **Indent Chart of Accounts**.  

> [!IMPORTANT]
> If you have entered definitions in the **Totaling** fields for **End-Total** accounts before executing the indent function, you must enter them again because the function overwrites the values in all **End-Total** fields.

## Delete accounts

You can delete a general ledger account. However, before you delete it, the following must be true:  

* The balance on the account must be zero.  
* The **Allow G/L Acc. Deletion Before** field must be set on the **General Ledger Setup** page, and the account must not have ledger entries on or after that date.  
* If the **Check G/L Account Usage** field on the **General Ledger Setup** page is selected, then the account must not be used in any posting groups or posting setup.  

[!INCLUDE[prod_short](includes/prod_short.md)] will prevent you from deleting a general ledger account that stores data that is needed in the chart of accounts.  

## Block deletion of G/L accounts

[!INCLUDE [2022_releasewave1](includes/2022_releasewave1.md)]

2022 release wave 2 introduces an extra safeguard against the accidental deletion of G/L accounts even in the scenarios where the criteria are met.  

A new field, **Block Deletion of G/L Accounts**, is added to the **General Ledger Setup** page. The field acts as an extra validation when a user tries to delete an account where there are ledger entries after the date that is specified in the **Check G/L Acc. Deletion After** field.

When the **Block Deletion of G/L Accounts** field is set to *Yes*, you cannot delete G/L accounts that have ledger entries after the date in the **Check G/L Acc. Deletion After** field. In order to delete such an account, a user with access to the **General Ledger Setup** page must first set this field to *No*. Then the account can be deleted.  

We recommend setting the **Block Deletion of G/L Accounts** field to *Yes*. We also recommend that you always have a date set in the **Check G/L Acc. Deletion After** field, such as the time you're required to store your finance data.  

## See Related Training at [Microsoft Learn](/learn/modules/chart-accounts-dynamics-365-business-central/index)

## See Also

[The General Ledger and the Chart of Accounts](finance-general-ledger.md)  
[Reconciling Bank Accounts](bank-manage-bank-accounts.md)  
[Work with Dimensions](finance-dimensions.md)  
[Importing Data from Other Finance Systems](across-import-data-configuration-packages.md)  
[Work with Account Schedules](bi-how-work-account-schedule.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Close Income Statement Accounts in the French Version](LocalFunctionality/France/how-to-close-income-statement-accounts.md)  
[Print Income Statements in the Australian Version](LocalFunctionality/Australia/how-to-print-income-statements.md)  
[Print Income Statements in the New Zealand Version](LocalFunctionality/NewZealand/how-to-print-income-statements.md)  
[Set Up and Close Income Statement Balances in the Spanish Version](LocalFunctionality/Spain/how-to-set-up-and-close-income-statement-balances.md)  
[Indent and Validate the Chart of Accounts in the Spanish Version](LocalFunctionality/Spain/how-to-indent-and-validate-chart-of-accounts.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]


[!INCLUDE[footer-include](includes/footer-banner.md)]