---
title: Allocate Recurring Costs and Income
description: Outlines the tasks to allocate an entry in a recurring general journal to several different accounts when you post the journal.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 283, 5629
ms.date: 11/11/2026
ms.custom: bap-template
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Allocate recurring costs and income

You can allocate an entry in a recurring general journal to several accounts when you post the journal. To learn more about recurring general journals, go to [Work with recurring journals](ui-work-general-journals.md#work-with-recurring-journals).

The following allocation methods are available:

* **Allocation Quantity**: Distribute the amount in proportion to the quantities on the allocation lines.
* **Allocation %**: Distribute the amount using the percentage on each allocation line.
* **Amount**: Specify a fixed allocation amount in local currency.

Fixed asset transactions also support allocations, which you set up separately through fixed asset posting groups.
<!--You can also distribute the cost or revenue of a line to an intercompany partner when you post a sales or purchase document. When you post the document, a line will be posted in your general journal, and a corresponding line will be created in the intercompany outbox.-->

The following procedures describe how to prepare to allocate costs in a recurring general journal by defining allocation keys. When you define allocation keys, you complete and post the journal like any other recurring general journal. Learn more in [Work with General Journals](ui-work-general-journals.md).

> [!IMPORTANT]  
> **Allocation Accounts** aren't supported in recurring journals. While the **Allocation Account** option is available in the **Account Type** field on the lines of the journal, this option isn't supported. Instead, use the allocations feature as described in this article.
>
> If you defined allocation accounts in a previous version of [!INCLUDE [prod_short](includes/prod_short.md)], update the setup to use allocations.

## To set up allocation keys

You can allocate an entry in a recurring general journal to several different accounts when you post the journal. The allocation can be a quantity, percentage, or amount.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Recurring General Journals**, and then choose the related link.
1. Choose the **Batch Name** field to open the **General Journal Batches** page.
1. Select an existing batch, or choose **New** to create one. For a new batch, fill in **Name**, such as CLEANING, and **Description**, such as Cleaning Expenses Journal.
1. Close the **General Journal Batches** page to return to the journal. Select an existing journal line or create a new line and fill in its fields. Allocations apply to the selected line, not to the whole batch.
1. Choose the **Allocations** action.
1. Add a line for each allocation. Fill in **Account No.** and either **Allocation %**, **Allocation Quantity**, or **Amount**.
1. To allocate among dimensions, select an allocation line, choose **Dimensions**, and assign the dimension values.
1. For percentage or quantity allocations, review the automatically calculated **Amount** on each allocation line. These amounts have the opposite sign from **Amount (LCY)** on the recurring journal line.
1. Choose **OK** to return to the **Recurring General Journals** page. Review **Allocated Amt. (LCY)**, which shows the total allocation amount in local currency. For a fully allocated line without a balancing account, this total must offset **Amount (LCY)**.
1. Post the journal.

## To change an allocation key that is already set up

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Recurring General Journals**, and then choose the related link.
1. In **Batch Name**, select the batch that contains the journal line.
1. Choose the line with the allocation, and then choose the **Allocations** action.
1. Change the relevant fields, and then choose **OK**.

## Related information

[Closing Years and Periods](year-close-years-periods.md)    
[Work with General Journals](ui-work-general-journals.md)    
[Posting Documents and Journals](ui-post-documents-journals.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
