---
title: Monitor project progress and performance
description: Describes how you can create a work in process (WIP) method and calculate WIP to estimate the financial value of projects while they're ongoing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 08/19/2024
ms.custom: bap-template
ms.search.keywords: project management, KPI, work in process, work in progress
ms.search.form: 89, 92, 1010
ms.service: dynamics-365-business-central
---

# Monitor project progress and performance

The work in process (WIP) feature lets you estimate the financial value of ongoing projects in the general ledger.

As a project progresses, materials and resources are consumed and expenses incurred that you must post to the project. In many cases, you might post expenses for a project before invoicing. But if you only post expenses, your financial statement is inaccurate. To track the actual value of the project, calculate WIP and post it to the general ledger. The following are the standard WIP methods:

* Cost value
* Sales value
* Recognizable cost
* Percentage of completion
* Completed contract

You can also create a WIP method that meets the needs of your organization and set it as the default. Learn more at [Understanding WIP Methods](projects-understanding-wip.md).

If you want to view the result using a different method, change the method and recalculate WIP. You can recalculate WIP as often as you like. The value isn't automatically posted to the general ledger. After you calculate WIP using the method you prefer, you can post to the general ledger.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project WIP Methods**, then choose the related link.  
2. Choose the **New** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Close the page.
4. To make this new method the default, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Projects Setup**, then choose the related link.  
5. In the **Default WIP Method** field, choose the method from the list.

## Define a WIP method for a project

When you create a new project, you must specify which project WIP method applies. In some cases, the project WIP method you use is already set as the default.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, then choose the related link.
2. Choose the **New** action. Learn more at [Create Projects](projects-how-create-jobs.md).  
3. On the **Project Card** page, in the **WIP Method** field from the **Posting** FastTab, select a WIP method from the list. If a default method is defined, you can select another option if needed.  

### Define a WIP method for a project task

You can define a WIP method for a project task, exclude project tasks from WIP calculation, or group tasks to be calculated together.

If you want to calculate WIP for each project task individually, WIP posting provides defined dimensions for the specific tasks.

The **WIP-Total** specifies project tasks you want to group together when calculating WIP and recognition. In any group of tasks, there needs to be one task that satisfies two conditions:
<!--But doesn't the parenthetical below contradict this -* if there is no total, the application sets the total for you, meaning the condition does not HAVE to be satisfied, right? Or am I missing something?-->

* **WIP-Total** is set to **Total**. If there are no project tasks with **WIP-Total** set to Total, Total is set automatically on the last project task line when WIP is calculated for the first time.
* The number in the **Project Task No.** field is the final one in the group or range of project tasks.

The following table describes the options:

| Field | Description |
|--|--|
| **\<blank\>** | Leave blank if the project task is part of a group of tasks. |
| **Total** | Defines the range or group of tasks included in the WIP and recognition calculation. Within the group, any project task with **Project Task Type** set to **Posting** is included in the WIP total, unless the task's **WIP-Total** field is set to **Excluded**. |
| **Excluded** | Applies only to a task with **Project Task Type** of **Posting**, in which case the task isn't included when WIP and recognition are calculated. |

In the following example, project tasks are divided into two WIP total groupings, demonstrating how the **WIP-Total** field works:

|Project task no.|Description|Project task type|**WIP-Total** field|  
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

You notice:

* For *1000* through *1299*, WIP is calculated separately for this group of project tasks. Note, however, that two of the tasks, 1010 and 1110, are excluded from the WIP calculation because their project task type is **Posting**.
* For *1300* through *1399*, WIP is calculated separately for this group of project tasks.

## Calculate WIP

You can determine the WIP amount to post to balance sheet accounts for the period end reporting by using the **Project Calculate WIP** batch job.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project Calculate WIP**, then choose the related link.  
2. Choose the **Calculate WIP** action.
3. On the **Project Calculate WIP** page, fill in the fields as necessary.
4. Choose the **OK** button.  

> [!NOTE]  
> The batch job only calculates the WIP, it doesn't post it to the general ledger. To post WIP, run the **Post WIP to G/L** batch job after you've calculated the WIP. Learn more in the following procedure.

### Review warnings

If your WIP calculation results in a *WIP was calculated with warnings* message, you might want to review the warnings.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project WIP Cockpit**, and then choose the related link.  
2. Select the project for which you want to review warnings. The **WIP Warnings** toggle is enabled for projects that have WIP warnings.
3. Choose the **Show Warning** action.

### Delete WIP entries

If you want to try different WIP methods, you might get a *The Project Task cannot be modified because the project has associated project WIP entries* error. To be able to check WIP method, delete existing WIP entries.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project WIP Cockpit**, and then choose the related link.  
2. Select the project for which you want to delete WIP entries.
3. Choose the **Delete WIP Entries** action.

## Post WIP

When you calculate WIP, you can post it to balance sheet accounts for the period end reporting. Use the **Project Post WIP to G/L** batch job.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project Post WIP to G/L**, and then choose the related link.  
2. On the **Project Post WIP to G/L** page, fill in the fields as necessary.  
3. Choose the **OK** button.

## Calculate and post project completion entries

After you complete all activities for a project, including posting usage and invoicing, you must update the project's status to **Completed**. Then, you must reverse any WIP that was posted to the general ledger.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, then choose the related link.  
2. Select an open project, and then choose the **Edit** action.
3. On the **Posting** FastTab, in the **Status** field, select **Completed**.
4. Follow the assistance steps to calculate and post the WIP, or follow steps 5 and 6 to do so manually.  
5. Choose the **Calculate WIP** action.
6. On the **Project Calculate WIP** page, fill in the fields as necessary.  

     The project WIP entries created by running the batch job have the **Project Complete** checkbox selected to show that they're completion entries.  
7. Choose the **Post WIP to G/L** action.
8. On the **Project Post WIP to G/L** page, fill in the fields as necessary.  

     The project WIP general ledger entries created by running the batch project have the **Project Complete** checkbox selected to show that they're completion entries.

## View project ledger entries

All project-related entries are recorded in project registers and sequentially numbered, starting with 1. From the project register, you can get an overview of all project ledger entries.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project Registers**, and choose the related link.
2. Select a relevant register, and then choose **Project Ledger** action.

On the **Project Ledger Entries** page, you can review the entries that are associated with any project.  

## Related information

[Walkthrough - Calculating Work in Process for a Project](walkthrough-calculating-work-in-process-for-a-job.md)    
[Project management analytics overview](projects-analytics-overview.md)  
[Managing Projects](projects-manage-projects.md)    
[Managing Inventory Costs](finance-manage-inventory-costs.md)    
[Finance](finance.md)    
[Purchasing](purchasing-manage-purchasing.md)    
[Sales](sales-manage-sales.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
