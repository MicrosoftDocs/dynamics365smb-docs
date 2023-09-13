---
title: Create a Job Sales Invoice to Invoice a Job
description: Describes how to invoice customers for job expenses as a project progresses and costs accumulate.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project invoice
ms.search.form: 1002, 1007, 
ms.date: 06/22/2021
ms.author: bholtorf

---
# Invoice Jobs

During the project, job costs from resource usage, materials, and job-related purchases can accumulate. As the job progresses, these transactions get posted to the job journal. It is important that all costs get recorded in the job journal before you invoice the customer.

> [!NOTE]
> You can also purchase external resources unrelated to a job, for example, to invoice a vendor for work delivered. For more information, see [Record Purchases](purchasing-how-record-purchases.md).

You can invoice the whole job from the **Job Task Lines** page or only invoice selected billable lines from the **Planning Lines** page. Invoicing can be done after the job is finished or at certain intervals during the job's progress based on an invoicing schedule.

> [!NOTE]  
> If you select **Billable** in the **Job Line Type** field on the purchase documents for job-related purchases, then job planning lines that are ready to be invoiced to the customer are created. For more information, see [Manage Project Supplies](projects-how-manage-project-supplies.md).

You can also invoice a company that is not the end customer. Sometimes the party that a project is for is different from the party that is paying the bill. On the **Jobs** page, you can specify the customer who will benefit from the project in the **Sell-to** fields, and the party to invoice in the **Bill-to** fields. 

## To create multiple job sales invoices

You can create an invoice for a job or for one or more job tasks for a customer when either the work to be invoiced is complete or the date for invoicing based on an invoicing schedule has been reached.

The following procedure shows how to use a batch job to invoice multiple jobs.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Create Sales Invoice**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Set filters if you want to limit the jobs that the batch job will process.
4. Choose the **OK** button to create the invoices.  

You can review and post created invoices in the **Sales Invoices** window.

> [!NOTE]
> Alternatively, invoice a customer by selecting the job, and then choosing the **Create Job Sales Invoice** action. 

## To create and post job sales invoice from job planning lines

You can create an invoice from a job planning lines, and indicate at that time the quantity of the item, resource, or general ledger account that you want to invoice.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Open a relevant job.
3. Select a job task for which the **Job Task Type** field contains **Posting**, and then choose the **Job Planning Lines** action.  
4. On a job planning line, in the **Qty. To Transfer to Invoice** field, enter the quantity of the item, resource, general ledger account type that you want to invoice.  
5. Choose the **Create Sales Invoice** action.
6. On the **Job Create Sales Invoice** page, enter the posting date and whether you want to create a new invoice or append this invoice to an existing one.
7. Choose the **OK** button.  
8. On the **Job Planning Lines** page, choose the **Sales Invoices/Credit Memos** action.

    The **Sales Invoice** page opens, showing the quantity that you have transferred to the invoice.
9. Make any additional changes, and then choose the **Post** action.

> [!NOTE]  
>   The above procedure is similar for creating, reviewing, and posting a job-related sales credit memo.

## See also

[Managing Projects](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
