---
title: Overview of tasks to allocate costs and income
description: Outlines the tasks to allocate an entry in a recurring general journal to several different accounts when you post the journal.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.devlang: al
ms.search.form: 283, 5629
ms.date: 12/06/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Allocate recurring costs and income

You can allocate an entry in a recurring general journal to several accounts when you post the journal. To learn more about recurring general journals, go to [Work with recurring journals](ui-work-general-journals.md#work-with-recurring-journals).

The following allocation methods are available:

* Quantity
* Percentage (%)
* Amount

The allocation features work with recurring general journals and in fixed asset journals.
<!--You can also distribute the cost or revenue of a line to an intercompany partner when you post a sales or purchase document. When you post the document, a line will be posted in your general journal, and a corresponding line will be created in the intercompany outbox.-->

The following procedures describe how to prepare to allocate costs in a recurring general journal by defining allocation keys. When allocation keys are defined, you complete and post the journal like any other recurring general journal. For more information, see [Work with General Journals](ui-work-general-journals.md).

> [!IMPORTANT]  
> **Allocation Accounts** aren't supported in recurring journals. While the **Allocation Account** option is available in the **Account Type** field on the lines of the journal, this option isn't supported. Instead, use the allocations feature as described in this article.
>
> If you defined allocation accounts in a previous version of [!INCLUDE [prod_short](includes/prod_short.md)], update the setup to use allocations.

## To set up allocation keys

You can allocate an entry in a recurring general journal to several different accounts when you post the journal. The allocation can be a quantity, percentage, or amount.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Recurring General Journals**, and then choose the related link.
2. Choose the **Batch Name** field to open the **General Journal Batches** page.
3. You can either modify allocations on an existing batch in the list or create a new batch with allocations.
   * To create a new batch, choose the **New** action, and go to the next step.
   * To change the allocations of an existing journal, select the journal and go to step 7.    
4. In the **Name** field, enter a name for the batch, such as CLEANING. In the **Description** field, enter a description, such as Cleaning Expenses Journal.
5. When you're done, close the page. A new, empty recurring journal opens.
6. Fill in the fields on the line.
7. Choose the **Allocations** action.
8. Add a line for each allocation. You must fill in either the **Allocation %**, **Allocation Quantity**, or **Amount** field. You must also fill in the **Account No.** field and, if you're allocating the transaction among global dimensions, the global dimension fields.
9. If you enter a percentage on a line, the amount in the **Amount** field is calculated automatically. These amounts have the opposite sign from the total amount in the **Amount** field in the recurring journal.
10. After entering the allocations lines, choose **OK** to return to the **Recurring General Journal** page. The **Allocated Amt. (USD)** field is filled in and matches the **Amount** field.
11. Post the journal.

## To change an allocation key that is already set up

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Recurring General Journals**, and then choose the related link.
2. On the **Recurring General Journals** page, select the journal with the allocation.
3. Choose the line with the allocation, and then choose the **Allocations** action.
4. Change the relevant fields, and then choose **OK**.

## Related information

[Closing Years and Periods](year-close-years-periods.md)    
[Work with General Journals](ui-work-general-journals.md)    
[Posting Documents and Journals](ui-post-documents-journals.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
