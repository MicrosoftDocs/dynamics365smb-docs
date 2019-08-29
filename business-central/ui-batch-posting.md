---
title: How to Post Multiple Documents at the Same Time | Microsoft Docs
description: Instead of posting individual documents one by one, you can select multiple non-posted documents in a list for batch posting, either for immediate posting or scheduled to, for example, the end of the day.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.date: 08/29/2019
ms.author: sgroespe

---
# Post Multiple Documents at the Same Time
Instead of posting individual documents one by one, you can select multiple non-posted documents in a list for batch posting, either for immediate posting or scheduled to, for example, the end of the day. This may be useful if only a supervisor can post documents created by other users or to avoid system performance issues from posting during work hours.

> [!NOTE]
> To batch post documents, you must set up a job queue entry for the immediate or scheduled task in question. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## To post multiple purchase invoices
The following procedure explains how to batch post purchase invoices. The steps are similar for all purchase and sales documents where the **Batch Post** action is available.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.  
2. On the **Purchase Invoices** page, proceed to select all invoices to be posted:
3. In the **No.** field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.
4. Select the check box for all the lines representing purchase invoices that you want to post at the same time.
5. Choose the **posting** action, and then choose the **Post Batch** action.
6. On the **Batch Post Purchase Invoices** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

The purchase invoices will not be added to a dedicated job queue entry, which defines when the documents are posted. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## See Also
[Posting Documents and Journals](ui-post-documents-journals.md)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Edit Posted Documents](across-edit-posted-document.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
