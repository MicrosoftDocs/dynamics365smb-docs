---
title: Create a Job Sales Invoice to Invoice a Job| Microsoft Docs
description: Describes how to invoice customers for job expenses as a project progresses.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project invoice
ms.date: 04/01/2020
ms.author: sgroespe

---
# Invoice Jobs
During the project, job costs from resource usage, materials, and job-related purchases can accumulate. As the job progresses, these transactions get posted to the job journal. It is important that all costs get recorded in the job journal before you invoice the customer.

> [!NOTE]
> You can also purchase external resources unrelated to a job, for example, to invoice a vendor for work delivered. For more information, see [Record Purchases](purchasing-how-record-purchases.md).

You can invoice the whole job from the **Job Task Lines** page or only invoice selected billable lines from the **Planning Lines** page. Invoicing can be done after the job is finished or at certain intervals during the job's progress based on an invoicing schedule.

> [!NOTE]  
>   If you select **Billable** in the **Job Line Type** field on the purchase documents for job-related purchases, then job planning lines that are ready to be invoiced to the customer are created. For more information, see [Manage Project Supplies](projects-how-manage-project-supplies.md).

## To create and post a job sales invoice
You can create an invoice for a job or for one or more job tasks for a customer when either the work to be invoiced is complete or the date for invoicing based on an invoicing schedule has been reached.

From the **Jobs** page, you can invoice a customer by selecting the job, and then choosing the **Create Job Sales Invoice** action. The following procedure shows how to use a batch job to invoice multiple jobs.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Create Sales Invoice**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Set filters if you want to limit the jobs that the batch job will process.
4. Choose the **OK** button to create the invoices.  

## To create multiple job sales invoices from job planning lines
You can create an invoice from a job planning lines, and indicate at that time the quantity of the item, resource, or general ledger account that you want to invoice.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Open a relevant job.
3. Select a job task for which the **Job Task Type** field contains **Posting**, and then choose the **Job Planning Lines** action.  
4. On a job planning line, in the **Qty. To Transfer to Invoice** field, enter the quantity of the item, resource, general ledger account type that you want to invoice.  
5. Choose the **Create Sales Invoice** action.
6. On the **Job Create Sales Invoice** page, enter the posting date and whether you want to create a new invoice or append this invoice to an existing one.
7. Choose the **OK** button.  

    On the job planning line, in the **Qty. Transferred to Invoice** field, you can see the quantity.
8. On the **Job Planning Lines** page, choose the **Sales Invoices/Credit Memos** action.

    The **Sales Invoice** page opens, showing the quantity that you have transferred to the invoice.  
9. Make any additional changes, and then choose the **Post** action.

> [!NOTE]  
>   The above procedure is similar for creating, reviewing, and posting a job-related sales credit memo.

## To calculate and post job completion entries
When you have completed all activities for a job, including usage posting and invoicing, you must update the job to have a **Status** of **Completed**. Then, you must reverse any WIP that has been posted to the general ledger.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2. Select an open job, and then choose the **Edit** action.
3. In the **Status** field, select **Completed**.
4. Follow the assistance steps to calculate and post WIP. Alternatively, follows steps 5 and 6 to do so manually.  
5. Choose the **Calculate WIP** action.
6. On the **Job Calculate WIP** page, fill in the fields as necessary.  

     The job WIP entries created by running the batch job will have the **Job Complete** check box selected to show that they are completion entries.  
7. Choose the **Job Post WIP to G/L** action.
8. On the **Job Post WIP to G/L** page, fill in the fields as necessary.  

     The job WIP general ledger entries created by running the batch job will have the **Job Complete** check box selected to show they are completion entries.

## See Also
[Managing Projects](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)         
[Sales](sales-manage-sales.md)      
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
