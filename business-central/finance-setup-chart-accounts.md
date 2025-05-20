---
title: Set up or change the chart of accounts
description: Learn about setting up your chart of accounts (COA) with the ledger accounts that store your financial data.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: COA, cha of acc
ms.search.form: 16_Primary, 17, 18, 118, 386, 391
ms.date: 05/19/2025
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Set up or change the chart of accounts

The chart of accounts (COA) shows the ledger accounts that store your financial data. [!INCLUDE[prod_short](includes/prod_short.md)] includes a standard COA that is ready to support your business. You can, however, change the default accounts, and you can add new accounts.
<br><br>  

> [!Video https://learn-video.azurefd.net/vod/player?id=944c65b0-9b0f-4d35-b330-de2fad57143a]

## Add or change accounts

From the COA, you can open each general ledger (G/L) account and add or change settings. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] 

If necessary, you can use more than one line for a general ledger account name. On the **G/L Account Card** page, in the **Account** group, choose **Extended Texts**, and then fill in one or more lines with the account name and copied text.  

For accounts of the **Total** account type, you must fill in the **Totaling** field. For **End-Total** accounts, this field is filled in automatically by the Indent function. After you set up the accounts, choose the **Process** action, then choose **Indent Chart of Accounts**.  

> [!IMPORTANT]
> If you entered definitions in the **Totaling** fields for **End-Total** accounts before using the indent function, you must enter them again because the function overwrites the values in all **End-Total** fields.

## Delete accounts

You can delete a general ledger account. However, before you delete it, the following conditions must be true:  

* The balance on the account must be zero.  
* The **Allow G/L Acc. Deletion Before** field must be set on the **General Ledger Setup** page, and the account must not have ledger entries on or after that date.  
* If the **Check G/L Account Usage** field on the **General Ledger Setup** page is selected, the account must not be used in any posting groups or posting setup.  

[!INCLUDE[prod_short](includes/prod_short.md)] prevents you from deleting a general ledger account that stores data that is needed in the chart of accounts.  

You can also specify when to allow people to delete accounts. On the **General Ledger Setup** page, the **Block Deletion of G/L Accounts** toggle works together with the date in the **Check G/L Acc. Deletion After** field to act as an extra validation. If you turn on the **Block Deletion of G/L Accounts** toggle, you can't delete G/L accounts with ledger entries after the date in the **Check G/L Acc. Deletion After** field. To delete such an account, someone with access to the **General Ledger Setup** page must turn off the **Block Deletion of G/L Accounts** toggle.  

Turning on the **Block Deletion of G/L Accounts** field is often a best practice, as is setting the date in the **Check G/L Acc. Deletion After** field, for example, to the date through which regulations require you to store finance data.  

### Video guidance

This video shows how to specify whether, and when, people can delete G/L accounts.

>[!VIDEO https://learn-video.azurefd.net/vod/player?id=b13b7e4c-5e2f-4f23-80cc-fccbc58d2fd2]

## Learning path: Set up the chart of accounts in Dynamics 365 Business Central

Want to learn how to set up the chart of accounts in [!INCLUDE [prod_short](includes/prod_short.md)]? Then start on the following learning path [Set up the chart of accounts in Dynamics 365 Business Central](/training/modules/chart-accounts-dynamics-365-business-central).

## Related information

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
