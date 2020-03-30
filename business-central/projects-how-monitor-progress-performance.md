---
title: Define a WIP Method and Monitor Job Progress| Microsoft Docs
description: Describes how you can create a work in process (WIP) method and calculate WIP to estimate the financial value of jobs while they are ongoing.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, KPI, work in process, work in progress
ms.date: 04/01/2020
ms.author: sgroespe

---
# Monitor Job Progress and Performance
As a job progresses, materials, resources, and other expenses are consumed and must be posted to the job. Work in Process (WIP) is a feature that enables you to estimate the financial value of jobs in the general ledger while the jobs are ongoing. In many cases, you might post expenses for a job before invoicing a job. When only expenses have been posted, your financial statement will be inaccurate. For more information, see [Understanding WIP Methods](projects-understanding-wip.md).

To track the value in the general ledger, you can calculate WIP and post the value to the general ledger.

You can calculate WIP based on the following:

* Cost Value
* Sales Value
* Recognizable Cost
* Percentage of Completion
* Completed Contract

If you want to view the result using a different method, you can change the method and calculate WIP again. There is no limit to the number of times that you calculate WIP. WIP is only calculated, it does not get posted to the general ledger. After you have calculated WIP, you can post to the general ledger.

## To create a job WIP method
You can create a job WIP method that reflects the needs of your organization. After you have created it, you can set it as the default job WIP calculation method that will be used in your organization.  

> [!NOTE]
> After you have used your new method to create WIP entries, you cannot delete the method or modify it.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job WIP Methods**, and then choose the related link.  
2. Choose the **New** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Close the page.   
4. To make this new method the default, choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs Setup**, and then choose the related link.  
5. In the **Default WIP Method** field, choose the method from the list.

## To define a WIP method for a job
When you create a new job, you must specify which job WIP method that applies. In some cases, which Job WIP method that you can use has been set up for you as a default.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Choose the **New** action. For more information, see [Create Jobs](projects-how-create-jobs.md).  
3. On the **Job Card** page, in the **WIP Method** field, select a WIP method from the list. If a default method has been defined, you can select another option if needed.  

## To calculate WIP
You can determine the WIP amount that is to be posted to balance sheet accounts for the period end reporting. You use the **Job Calculate WIP** batch job to do this.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Calculate WIP**, and then choose the related link.  
2. Choose the **Calculate WIP** action.
3. On the **Job Calculate WIP** page, fill in the fields as necessary.
4. Choose the **OK** button.  

> [!NOTE]  
>   The batch job only calculates the WIP. It is not posted to the general ledger. To do so, you must run the **Post WIP to G/L** batch job when you have calculated the WIP. For more information, see the following procedure.

## To post WIP
When you have calculated WIP, you can post it to balance sheet accounts for the period end reporting. You use the **Job Post WIP to G/L** batch job to do this.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Post WIP to G/L**, and then choose the related link.  
2. On the **Job Post WIP to G/L** page, fill in the fields as necessary.  
3. Choose the **OK** button.

## To view job usage estimates and post updates
You can view job usage up to the completion of a project in one step. To do so, you use the **Job Calc. Remaining Usage** batch job for all the tasks up to and including the end of a job.  

This lets you track and compare your original estimates against actual results and make modifications or new entries as needed. For example, you may have estimated that a job required 10 hours, and to date, it has taken 15 hours. You can add the extra five hours to the existing journal line or create a new journal line to report these five hours as overtime, which is another work type. The appropriate cost and price are calculated, and you can then post to the journal.  

> [!NOTE]  
>   Item entries create item ledger entries and reduce the inventory quantity. The **Post Inventory Cost to G/L** batch job transfers the cost from inventory to the general ledger. Resource entries create resource ledger entries.  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.  
2. Select a relevant job journal, and then choose the **Calc. Remaining Usage** action.  
3. On the **Job Calc. Remaining Usage** page, enter the document number and posting date that is to be inserted in the journal, and then choose the **OK** button.  
4. Update the journal with any modifications that may be needed.  
5. Choose the **Post**.

## To view job ledger entries
All job-related entries are recorded in job registers and are numbered sequentially, starting with 1. From the job register, you can get an overview of all job ledger entries.    

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Registers**, and then choose the related link.
2. Select a relevant register, and then choose **Job Ledger** action.

On the **Job Ledger Entries** page you can review the entries that are associated with any job.  

## See Also
[Managing Projects](projects-manage-projects.md)
[Managing Inventory Costs](finance-manage-inventory-costs.md)   
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)         
[Sales](sales-manage-sales.md)      
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
