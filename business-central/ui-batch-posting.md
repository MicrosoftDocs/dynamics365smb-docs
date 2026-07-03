---
title: Post multiple documents at the same time
description: Learn how to select multiple nonposted documents in a list for immediate or scheduled batch posting in Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.form: 
ms.reviewer: bholtorf
ms.date: 07/03/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Post multiple documents at the same time

Instead of posting documents one by one, you can select multiple documents in a list to post them immediately, or post them as a batch according to a schedule, such as at the end of the day. For example, batch posting can be useful if only a supervisor can post documents created by other users, and to avoid system performance issues from posting during work hours.

## Post multiple purchase orders immediately

The following procedure explains how to post multiple purchase orders right away. The steps are similar for all purchase and sales documents.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Orders**, and then choose the related link.
2. On the **Purchase Orders** page, proceed to select all orders to be posted:
3. In the **No.** field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.
4. Select the checkbox for all the lines representing orders that you want to post at the same time.
5. Choose the **Posting** action, and then choose the **Post** action.
6. Choose the **Yes** button on the confirmation message.

## Batch post multiple purchase orders

The following procedure explains how to batch post purchase orders. The steps are similar for all purchase and sales documents where the **Batch Post** action is available.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Orders**, and then choose the related link.  
2. On the **Purchase Orders** page, proceed to select all orders to be posted:
3. In the **No.** field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.
4. Select the checkbox for all the lines representing orders that you want to post at the same time.
5. Choose the **Posting** action, and then choose the **Post Batch** action.
6. On the **Batch Post Purchase Order** page, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Choose the **OK** button.
8. If there were issues, you can review them on the **Error Message Register** page.

> [!NOTE]
> Posting multiple documents might take some time and block other users. Consider enabling background posting. Learn more in [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

## Schedule background posting with the job queue

You can use the job queue to schedule business processes to run in the background. For example, posting documents on a schedule helps avoid situations where multiple users want to post sales orders at the same time, but orders only process one after another.  

Before you can post a batch of documents though, there are a few things to set up. The following procedure explains how to set up background posting of sales orders. The steps are similar for purchasing.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sales & Receivables Setup**, and then choose the related link.
2. On the **Sales & Receivables Setup** page, choose the **Post with Job Queue** checkbox.
3. Choose the **Job Queue Category Code** field, and then specify the **SALESPOST** code.

    > [!NOTE]
    > Some jobs change the same data. To avoid conflicting changes, you shouldn't run them at the same time. For example, background jobs for sales documents modify the same data at the same time. Job queue categories help prevent these kinds of conflicts. Categories ensure that when one job is running, another job that belongs to the same category waits until it finishes. For example, a job that belongs to a Sales job queue category waits until all other sales related jobs are done. You specify a job queue category on the **Background Posting** FastTab on the **Sales & Receivables Setup** page.
    >
    > [!INCLUDE[prod_short](includes/prod_short.md)] provides job queue categories for sales, purchase, and general ledger posting. We recommend that one of these categories, or one that you create, is always specified. If you experience errors due to conflicts, consider setting up a category for all sales, purchase, and general ledger background posting.

    If you also want sales documents to be printed when they're posted, select the **Post & Print with Job Queue** checkbox on the **Sales & Receivables Setup** page.  
    If you select **PDF** in the **Report Output Type** field, successfully posted purchase orders are available in the **Report Inbox** part on your Role Center.

    > [!IMPORTANT]  
    > If you want to set up a job that posts and prints documents, we recommend that you don't use a printer setup that requires user interaction. For example, a display of printer dialog boxes that request credentials or show a warning about low printer ink. When that happens and someone isn't there to react, your document posts but doesn't print. The corresponding job queue entry eventually times out and the **Status** field is set to **Error**.

    The next time that you post sales documents, [!INCLUDE [prod_short](includes/prod_short.md)] automatically creates a job queue entry for each document and run the jobs in the background, one by one.

4. To verify that the job queue works as expected, post a sales order. Learn more in [Sell Products](sales-how-sell-products.md).
    The sales order is added to a job queue entry that defines when the documents are posted.

## Create a job queue entry for batch posting of sales orders

Alternatively, you can postpone posting to happen at a time that's convenient for your organization. For example, it might make sense for your business to run certain routines when most of your data entry is done for the day. You can set up the job queue to run various batch-posting reports, such as the **Batch Post Sales Orders**, **Batch Post Sales Invoices**, and similar reports. [!INCLUDE[prod_short](includes/prod_short.md)] supports background posting for all sales, purchasing, and service documents.

The following procedure shows how to set the **Batch Post Sales Orders** report up to automatically post sales orders at 4 PM on weekdays.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Job Queue Entries**, and then choose the related link.  
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

5. Select the **Report Request Page** checkbox.
6. In the **Batch Post Sales Orders** request page, define what is included during automatic posting of sales orders, and then choose the **OK** button.

    > [!IMPORTANT]
    > Remember to set strict filters. Otherwise, [!INCLUDE [prod_short](includes/prod_short.md)] posts all documents, even if they aren't ready. Consider setting a filter on the **Status** field for the value **Released**, and a filter on the **Posting Date** field for the value *..today*. Learn more in [Sorting, Searching, and Filtering](ui-enter-criteria-filters.md).
    >
    > The **Posting Date** field can be tricky when you batch post recurring documents, such as recurring sales invoices. To use the document date, leave the field empty and don't turn on **Replace Posting Date**. If you specify a specific date, each recurrence for some documents uses that date. It's a good idea to double-check your setup to ensure that you use the correct posting date.
7. Select the checkboxes for the days of the week on which the job runs.
8. In the **Starting Time** field, enter the time of day the job starts. For example, **4 PM**.
9. Choose the **Set Status to Ready** action.

### View status from a sales or purchase document

If the job queue can't post a sales or purchase document, its status changes to **Error** and it's added to the list of sales orders that you must handle manually.

1. From the document that you posted with background posting, choose the **Job Queue Status** field (which contains **Error**).
2. Review the error message and fix the problem.

Alternatively, you can review on the **Job Queue Log Entries** page if the document posted successfully. Learn more in [Monitor the job queue](#monitor-the-job-queue) section.

## Monitor the job queue

If you set up background posting with job queues, make it a regular task to monitor the job queue to catch any issues. You can track the status in the **Job Queue Entries** page. Learn more in [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).  

As an administrator, you can use [Application Insights](/azure/azure-monitor/app/app-insights-overview) to gather and analyze telemetry that you can use to identify problems. Learn more in [Monitoring and Analyzing Telemetry](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) in the developer and administration content.  

## Related information

[Posting Documents and Journals](ui-post-documents-journals.md)  
[Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md)  
[Edit Posted Documents](across-edit-posted-document.md)  
[Correct or Cancel Unpaid Purchase Invoices](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Finding Pages and Information with Tell Me](ui-search.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
