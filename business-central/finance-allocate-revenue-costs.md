---
title: Allocate revenue and costs to multiple general ledger accounts
description: Learn how to allocate costs to one or more accounts in your general ledger.
author: brentholtorf
ms.author: bholtorf
ms.date: 08/08/2024
ms.topic: how-to
ms.search.keywords: allocate, allocation, accounts
ms.search.form: 39, 2673, 2670, 2674, 
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Allocate revenue and costs to multiple general ledger accounts

This article describes how to use allocation accounts to distribute amounts on sales and purchase documents and general journal lines to different G/L accounts. You can allocate amounts through a fixed or variable distribution.  

Allocation splits a general journal line into the lines defined on the **Allocation Account** page. For example, if you split a rent expense three ways using dimensions, you'll have three lines to post for the allocation. Therefore, you'll have six G/L lines (or possibly more if you're using VAT or sales tax). Although this posts more G/L entries than you might need, it allows you to reverse individual lines instead of reversing the whole allocation.

Allocation accounts also work with deferrals. To learn more about deferrals, go to [Defer Revenues and Expenses](finance-how-defer-revenue-expenses.md).

The following table introduces the allocation methods you can use.

|Allocation Method  |Description  |
|---------|---------|
|Fixed     | When you want to split up expenses in a way that's repeated over a longer period of time, you can use a fixed allocation. A fixed allocation lets you define the allocation split. This split will only change when you change the setup on the **Allocation Account** page.        |
|Variable     | To distribute revenue or expenses based on values that change over time, use the variable allocation method. Variable allocations let you specify the sources to use to calculate the allocation percentages. This method is useful, for example, for splitting employee costs that according to varying headcounts in departments or divisions. Another example is the distributing the cost of rent based on production floor footage that might vary per production line over time. Variable allocations use a combination of dimensions and statistical accounts to determine how amounts distribute over a period of time. To learn more about statistical accounts, go to [Analyze Data with Statistical Accounts](bi-use-statistical-accounts.md). To learn more about dimensions, go to [Work with Dimensions](finance-dimensions.md).        |

## Use a fixed share or percentage method to allocate amounts

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Allocation Account**, and then choose the related link.  
1. On the **Allocation Accounts** page, choose **New**.
1. Fill in the **No.** and **Name** fields.
1. In the **Account Type** field, choose **Fixed**.
1. In the **Destination Account Type** field, choose **G/L Account** or **Bank Account**.
1. In the **Destination Account Number** field, choose the account to post the value to.
1. Optional: Choose the **Dimensions** action, and then specify the dimensions to post for the line.
1. In the **Share** and **Percent** fields, specify how to distribute amounts to the destination account.
  
   > [!TIP]
   > If you enter the actual amount to allocate for a fixed allocation in the **Share** field, the **Percent** field shows the percentage of the total amount.
1. Repeat this process for each account to include in the allocation.

## Use a variable method to allocate amounts

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Allocation Account**, and then choose the related link.  
1. On the **Allocation Accounts** page, choose **New**.
1. Fill in the **No.** and **Name** fields.
1. In the **Account Type** field, choose **Variable**.
1. In the **Destination Account Type** field, choose **G/L Account**.
1. In the **Destination Account Number** field, choose the account to post the value to.
1. In the **Breakdown Account Type** field, choose **Statistical Account**.
1. In the **Calculation Period** field, choose the period for which to distribute amounts.
1. Optional: To filter on specific global dimension values, choose the **Breakdown account balance filters** action, and then specify the filter values.
1. Optional: Choose the **Dimensions** action, and then specify the dimensions to post for the line.

## Allocate amounts on the fly

You create allocation accounts to split revenue and costs for G/L accounts and bank accounts. Automating allocation can save time. However, if you want to use allocation accounts, but you don't want to create them for each G/L account, you can save even more time.

The Inherit from parent option lets you use the allocation account to split amounts for any G/L account on a line on a document or journal. In the **Account Type** field on a document or journal line, you choose a G/L account, and then choose the allocation account in the **Allocation Account No.** field. The amount on the line is split for the G/L account according to the setup in your allocation account. It's a less transparent way of allocating, but you don't have to create an allocation account specifically for the G/L account.

Ad-hoc allocations are easy to set up. Instead of specifying a bank or G/L account in the **Destination Account Type** field on the **Allocation Account** page, choose the **Inherit from parent** option. Leave the **Destination Account Number** field blank. When you choose the G/L account on the document or journal line, that account is used to allocate amounts.

## Verify that amounts distribute correctly before you post them

There are a couple of ways to verify that amounts distribute correctly:

* On the **Allocation Account** page, choose the **Test Allocation** action. Use the **Amount to Allocate** field to test different amounts.
* On the **General Ledger Journals** page, choose the journal, and then use the **Posting Preview** action.

## Adjust the distribution

If you find something in an allocation that you'd like to change, you can adjust the allocation before you post it.  

1. Open the document or journal that has the allocation you want to change.
1. Choose the line, and then choose the **Redistribute Account Allocations** action.
1. On the **Change Allocations** page, make your adjustment.

## Post an allocation transaction

The following steps describe how to post an allocation transaction from a general journal. The steps are the same for sales and purchase documents.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link.  
1. Create a new line. Fill in the fields in the same way you would for any other type of general journal.
1. If you're using a fixed or variable allocation, fill in the following fields:
    1. In the **Account Type** field, choose **Allocation Account**.
    1. In the **Account No.** field, choose the allocation account.
1. If you're using an allocation that uses the Inherit from parent option, do the following:
    1. In the **Account Type** field, choose **G/L Account**.
    1. In the **Account No.** field, choose the G/L account.
    1. In the **Allocation Account No.** field, choose the allocation account that's set up to use the Inherit from parent option. 
1. Choose **Post**.

## Related information

[Work with General Journals](ui-work-general-journals.md)  
