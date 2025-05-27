---
title: Post Multiple Documents at the Same Time
description: Learn how to select multiple non-posted documents in a list for immediate or scheduled batch posting in Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 
ms.reviewer: bholtorf
ms.date: 06/25/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
---
# Post Multiple Documents at the Same Time

Instead of posting individual documents one by one, you can select multiple non-posted documents in a list for immediate posting or for batch posting according to a schedule, such as at the end of the day. This may be useful if only a supervisor can post documents created by other users or to avoid system performance issues from posting during work hours.

## To post multiple purchase orders immediately

The following procedure explains how to post multiple purchase orders immediately. The steps are similar for all purchase and sales documents.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.
2. On the **Purchase Orders** page, proceed to select all orders to be posted:
3. In the **No.** field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.
4. Select the check box for all the lines representing orders that you want to post at the same time.
5. Choose the **Posting** action, and then choose the **Post** action.
6. Choose the **Yes** button on the confirmation message.

## To batch post multiple purchase orders

The following procedure explains how to batch post purchase orders. The steps are similar for all purchase and sales documents where the **Batch Post** action is available.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.  
2. On the **Purchase Orders** page, proceed to select all orders to be posted:
3. In the **No.** field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.
4. Select the check box for all the lines representing orders that you want to post at the same time.
5. Choose the **Posting** action, and then choose the **Post Batch** action.
6. On the **Batch Post Purchase Order** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Choose the **OK** button.
8. To view potential issues that occurred during batch posting of documents, open the **Error Message Register** page.

> [!NOTE]
> Posting of multiple documents might take some time and block other users. Consider enabling background posting. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## To set up background posting with job queues
Job queues are an effective tool to schedule the running of business processes in the background, such as when multiple users are trying to post sales orders, but only one order can be processed at a time.  

The following procedure explains how to set up background posting of sales orders. The steps are similar for purchasing.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales & Receivables Setup**, and then choose the related link.
2. On the **Sales & Receivables Setup** page, choose the **Post with Job Queue** check box.
3. Choose the **Job Queue Category Code** field, and then specify the **SALESPOST** code.

    > [!NOTE]
    > Some jobs change the same data and should not run at the same time because that can cause conflicts. For example, background jobs for sales documents will try to modify the same data at the same time. Job queue categories help prevent these kinds of conflicts by ensuring that when one job is running, another job that belongs to the same job queue category will not run until it finishes. For example, a job that belongs to a Sales job queue category will wait until all other sales related jobs are done. You specify a job queue category on the **Background Posting** FastTab on the **Sales & Receivables Setup** page.
    >
    > [!INCLUDE[prod_short](includes/prod_short.md)] provides job queue categories for sales, purchase, and general ledger posting. We recommend that one of these, or one that you create, is always specified. If you experience failures due to conflicts, consider setting up a category for all sales, purchase, and general ledger background posting.

    If you also want sales documents to be printed when they are posted, select the **Post & Print with Job Queue** check box on the **Sales & Receivables Setup** page.  
    If you select **PDF** in the **Report Output Type** field, successfully posted purchase orders will be available in the **Report Inbox** part on your Role Center.

    > [!IMPORTANT]  
    > If you set up a job that will post and print documents, and the printer displays a dialog box, such as a request for credentials or a warning about low printer ink, your document is posted but not printed. The corresponding job queue entry eventually times out and the **Status** field is set to **Error**. Accordingly, we recommend that you do not use a printer setup that requires interaction with the display of printer dialog boxes in conjunction with background posting.

    Next time that you post sales documents, [!INCLUDE [prod_short](includes/prod_short.md)] automatically creates a job queue entry for each document and run the jobs in the background, one by one.

4. To verify that the job queue is working as expected, post a sales order. For more information, see [Sell Products](sales-how-sell-products.md).
    The sales order will now be added to a dedicated job queue entry, which defines when the documents are posted. 

### To view status from a sales or purchase document
If the job queue cannot post the sales order, the status is changed to **Error** and the sales order is added to the list of sales orders that the user must handle manually.
1. From the document that you have tried to post with background posting, choose the **Job Queue Status** field, which will contain **Error**.
2. Review the error message and fix the problem.

Alternatively, you can review on the **Job Queue Log Entries** page if the sales order was posted successfully. For more information, see the [Monitor the job queue](#monitor-the-job-queue) section.

## To create a job queue entry for batch posting of sales orders

Alternatively, you can postpone postings for when it is convenient for your organization. For example, in your business it might make sense to run certain routines when most of the data entry for the day has concluded. You can achieve this by setting the job queue up to run various batch-posting reports, such as the **Batch Post Sales Orders**, **Batch Post Sales Invoices**, and similar reports. [!INCLUDE[prod_short](includes/prod_short.md)] supports background posting for all sales, purchasing, and service documents.

The following procedure shows how to set the **Batch Post Sales Orders** report up to automatically post sales orders at 4 PM on weekdays.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Queue Entries**, and then choose the related link.  
2. Choose the **New** action.  
3. In the **Object Type to Run** field, select **Report**.  
4. In the **Object ID to Run** field, select 296, **Batch Post Sales Orders**.

   You can also use following reports:
  
   * 900 **Batch Post Assembly Orders**
   * 497 **Batch Post Purchase Invoices**
   * 496 **Batch Post Purchase Orders**
   * 498 **Batch Post Purch. Credit Memos**
   * 6665 **Batch Post Purch. Ret. Orders**
   * 298 **Batch Post Sales Credit Memos**
   * 297 **Batch Post Sales Invoices**
   * 296 **Batch Post Sales Orders**
   * 6655 **Batch Post Sales Return Orders**
   * 6005 **Batch Post Service Cr. Memos**
   * 6004 **Batch Post Service Invoices**
   * 6001 **Batch Post Service Orders**

5. Select the **Report Request Page** check box.
6. In the **Batch Post Sales Orders** request page, define what is included during automatic posting of sales orders, and then choose the **OK** button.

    > [!IMPORTANT]
    > Remember to set strict filters; otherwise, [!INCLUDE [prod_short](includes/prod_short.md)] will post all documents, even if they are not ready. Consider setting a filter on the **Status** field for the value *Released*, and a filter on the **Posting Date** field for the value *..today*. For more information, see [Sorting, Searching, and Filtering](ui-enter-criteria-filters.md).
7. Select all check boxes from **Run on Mondays** through **Run on Fridays**.
8. In the **Starting Time** field, enter 4 PM.
9. Choose the **Set Status to Ready** action.

Sales orders that are within defined filters will now be posted every weekday at 4 PM.

## Monitor the job queue

If you set up background posting with job queues, make it a regular task to monitor the job queue to catch any issues. You can track the status in the **Job Queue Entries** page. For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).  

As an administrator, you can use [Application Insights](/azure/azure-monitor/app/app-insights-overview) to gather and analyze telemetry that you can use to identify problems. For more information, see [Monitoring and Analyzing Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) in the developer and administration content.  

## Related information

[Posting Documents and Journals](ui-post-documents-journals.md)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Edit Posted Documents](across-edit-posted-document.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
