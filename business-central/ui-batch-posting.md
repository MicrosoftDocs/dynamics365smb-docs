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
ms.date: 04/01/2020
ms.author: sgroespe

---
# Post Multiple Documents at the Same Time
Instead of posting individual documents one by one, you can select multiple non-posted documents in a list for immediate posting or for batch posting according to a schedule, such as at the end of the day. This may be useful if only a supervisor can post documents created by other users or to avoid system performance issues from posting during work hours.

## To post multiple purchase orders immediately
The following procedure explains how to post multiple purchase orders immediately. The steps are similar for all purchase and sales documents.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. On the **Purchase Orders** page, proceed to select all orders to be posted:
3. In the **No.** field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.
4. Select the check box for all the lines representing orders that you want to post at the same time.
5. Choose the **Posting** action, and then choose the **Post** action.
6. Choose the **Yes** button on the confirmation message.

## To batch post multiple purchase orders
The following procedure explains how to batch post purchase orders. The steps are similar for all purchase and sales documents where the **Batch Post** action is available.

> [!NOTE]
> Batch posting of documents happens in the background as defined by a job queue entry, which must first be set up. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
2. On the **Purchase Orders** page, proceed to select all orders to be posted:
3. In the **No.** field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.
4. Select the check box for all the lines representing orders that you want to post at the same time.
5. Choose the **Posting** action, and then choose the **Post Batch** action.
6. On the **Batch Post Purchase Order** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]
    > To print related reports when posting, such as the **Order Confirmation** report for sales orders, select the **Print** check box.<br /><br /> In the **Report Output Type** field on the **Sales and Receivables Setup** page or **Purchases and Payables Setup** page, you define if the report will be printed or output as a PDF.<br /><br /> Note also that direct printing to a selected printer is only possible in on-premises installations.

7. Choose the **OK** button.
8. To view potential issues that occurred during batch posting of documents, open the **Error Message Register** page.

The purchase orders will now be added to a dedicated job queue entry, which defines when the documents are posted. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

If you select **PDF** in the **Report Output Type** field, successfully posted purchase orders will be available in the **Report Inbox** part on your Role Center.

## See Also
[Posting Documents and Journals](ui-post-documents-journals.md)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Edit Posted Documents](across-edit-posted-document.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
