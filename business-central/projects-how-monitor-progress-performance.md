---

title: Monitor Job Progress and Performance
description: Describes how you can create a work in process (WIP) method and calculate WIP to estimate the financial value of jobs while they are ongoing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/28/2023
ms.custom: bap-template
ms.search.keywords: project management, KPI, work in process, work in progress
ms.search.form: 89, 92, 1010
---
# Monitor Job Progress and Performance

With the work in process (WIP) feature you can estimate the financial value of ongoing jobs in the general ledger.

As a job progresses, materials and resources are consumed and expenses incurred that must be posted to the job. In many cases, you might post expenses for a job before invoicing. But if only expenses have been posted, your financial statement is inaccurate. To track the actual value of the job, calculate WIP and post it to the general ledger. Learn more at [Understanding WIP Methods](projects-understanding-wip.md).

You can calculate WIP based on the following:

* Cost value
* Sales value
* Recognizable cost
* Percentage of completion
* Completed contract

<!--If you want to view the result using a different method, change the method and calculate WIP again. There's no limit to the number of times you calculate WIP; it doesn't get automatically posted to the general ledger. After you've calculated WIP using the method you prefer, you can post to the general ledger.-->
<!--Unhide the above paragraph?-->

## Create a job WIP method

Create a job WIP method that meets the needs of your organization and set it as the default.  

> [!NOTE]
> After you've used your new method to create WIP entries, you cannot modify or delete that method.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **job wip methods**, then choose the related link.  
2. Choose the **New** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Close the page.   
4. To make this new method the default, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **jobs setup**, then choose the related link.  
5. In the **Default WIP Method** field, choose the method from the list.

## Define a WIP method for a job

When you create a new job, you must specify which job WIP method applies. In some cases, the job WIP method you use is already set as the default.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **jobs**, then choose the related link.
2. Choose the **New** action. Learn more at [Create Jobs](projects-how-create-jobs.md).  
3. On the **Job Card** page, in the **WIP Method** field, select a WIP method from the list. If a default method has been defined, you can select another option if needed.  

### Define a WIP method for a job task

You can define a WIP method for a job task, exclude some job tasks from WIP calcualtion, or group tasks to be calcualted together. 

If you want to calculate WIP for each job task individually, WIP posting provides defined dimensions for the specific tasks.

The **WIP-Total** specifies job tasks you want to group together when calculating WIP and recognition. In any group of tasks, there needs to be one task that satisfies two conditions:
<!--But doesn't the parenthetical below contradict this -* if there is no total, the application sets the total for you, meaning the condition does not HAVE to be satisfied, right? Or am I missing something?-->

* Has a **WIP-Total** set to *Total*. (If there are no job tasks with **WIP-Total** set to *Total*, *Total* is set automatically on the last job task line when WIP is calculated for the first time.)

* Has a **Job Task No.** number that's the final one in the group or range of job tasks.

The following table describes the three options:

| Field | Description |
|--|--|
| **\<blank\>** | Leave blank if the job task is part of a group of tasks. |
| **Total** | Defines the range or group of tasks included in the WIP and recognition calculation. Within the group, any job task with **Job Task Type** set to **Posting** is included in the WIP total, unless the task's **WIP-Total** field is set to **Excluded**. |
| **Excluded** | Applies only to a task with **Job Task Type** of **Posting**, in which case the task isn't included when WIP and recognition are calculated. |

In the following example, job tasks are divided into two WIP total groupings, demonstrating how the **WIP-Total** field works:

|Job task no.|Description|Job task type|**WIP-Total** field|  
|------------------|----------------------|----------------------|----------------------|  
|1000|Preparation|Begin-Total|\<blank\>|
|1010|.    Cleaning|Posting|**Excluded**|
|1099|Total preparation|End-Total|\<blank\>|
|1100|Carpeting|Begin-Total|\<blank\>|
|1110|.    Gluing floor|Posting|**Excluded**|
|1120|.    Laying out carpet|Posting|\<blank\>|
|1199|Total carpeting|End-Total|\<blank\>|
|1200|Finish|Begin-Total|\<blank\>|
|1210|.    Vacuum cleaning carpet|Posting|\<blank\>|
|1299|Total finish|End-Total|**Total**|
|1300|Error correction|Begin-Total|\<blank\>|
|1310|.    Error correction|Posting|\<blank\>|
|1399|Total error correction|End-Total|**Total**|

You'll notice:

* *1000* through *1299*: WIP are calculated separately for this group of job tasks. Note however, that two of the tasks, 1010 and 1110, are excluded from the WIP calculation because their job task type is **Posting**.

* *1300* through *1399*: WIP are calculated separately for this group of job tasks.

## Calculate WIP

You can determine the WIP amount to post to balance sheet accounts for the period end reporting. Use the **Job Calculate WIP** batch job to do this.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **job calculate wip**,  then choose the related link.  
2. Choose the **Calculate WIP** action.
3. On the **Job Calculate WIP** page, fill in the fields as necessary.
4. Choose the **OK** button.  

> [!NOTE]  
>   The batch job only calculates the WIP, it does not post it to the general ledger. To post it, run the **Post WIP to G/L** batch job after you've calculated the WIP. Learn more in the following procedure.

## Post WIP

When you've calculated WIP, you can post it to balance sheet accounts for the period end reporting. You use the **Job Post WIP to G/L** batch job to do this.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **job post wip to g/l**,  then choose the related link.  
2. On the **Job Post WIP to G/L** page, fill in the fields as necessary.  
3. Choose the **OK** button.

## Calculate and post job completion entries

When you have completed all activities for a job, including usage posting and invoicing, you must update the job to a **Status** of **Completed**. Then, you must reverse any WIP that has been posted to the general ledger.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **jobs**, then choose the related link.  
2. Select an open job, and then choose the **Edit** action.
3. In the **Status** field, select **Completed**.
4. Follow the assistance steps to calculate and post the WIP. Or follows steps 5 and 6 to do so manually.  
5. Choose the **Calculate WIP** action.
6. On the **Job Calculate WIP** page, fill in the fields as necessary.  

     The job WIP entries created by running the batch job will have the **Job Complete** check box selected to show that they are completion entries.  
7. Choose the **Job Post WIP to G/L** action.
8. On the **Job Post WIP to G/L** page, fill in the fields as necessary.  

     The job WIP general ledger entries created by running the batch job will have the **Job Complete** check box selected to show they are completion entries.

## View job ledger entries

All job-related entries are recorded in job registers and sequentially numbered, starting with 1. From the job register, you can get an overview of all job ledger entries.    

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **job registers**, and choose the related link.
2. Select a relevant register, and then choose **Job Ledger** action.

On the **Job Ledger Entries** page you can review the entries that are associated with any job.  

## See also

[Walkthrough - Calculating Work in Process for a Job](walkthrough-calculating-work-in-process-for-a-job.md)
[Managing Projects](projects-manage-projects.md)  
[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
