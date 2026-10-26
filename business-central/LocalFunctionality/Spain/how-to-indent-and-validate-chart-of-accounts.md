---
title: Indent and Validate Chart of Accounts
description: Learn how to configure general ledger accounts, indent the chart of accounts, and validate account structure in Business Central for Spain.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:  indent chart of account, validate chart of account, G/L account card page
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Indent and validate chart of accounts

You can indent and validate the chart of accounts on the **G/L Account Card** page. You can enter a maximum of 20 numbers. Accounts are sorted in string order, as shown in the following example.  

1  
10  
101  
2  
20  
2100001  
3  
31  

## Steps to indent and validate the chart of accounts  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Chart of Accounts**, and then choose the related link.  
1. Choose the **New** action.  
1. On the **General** FastTab, in the **No.** field, enter the number of the general ledger account that you're setting up.  
1. In the **Account type** field, select **Posting** or **Heading**. **Posting** implies that entries can be posted to the account. **Heading** implies that entries can't be posted to the account.  

    > [!NOTE]  
    > For Portugal, select **Posting** or **Total** in the **Account type** field.  

1. In the **Income Stmt. Bal. Acc.** field, select the account to which the changes will be sent after correction.  
1. Enter information into the other relevant fields.  
1. Choose the **OK** button to close the **G/L Account Card** page.  
1. On the **Chart of Accounts** page, select an account, and then choose **Indent Chart of Accounts**.  
1. To validate the chart of accounts, choose the **Yes** button in the dialog. After validation, you're notified whether the chart of accounts is correct.  
1. Choose the **OK** button.  

## Steps to validate the chart of accounts in Portugal  

1. On the **Chart of Accounts** page, choose the **Check Chart of Accounts** action.  
1. Choose the **Yes** button.  

## Related information

[Spain Local Functionality](spain-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
