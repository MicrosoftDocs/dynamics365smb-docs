---
title: Create a Job Card for a Job and Specify Tasks
description: For a new project, you create a job card that contains job tasks and planning lines, to help you manage progress and budgets.
author: brentholtorf
ms.topic: conceptual
ms.workload: na
ms.search.keywords: project management, task
ms.search.form: 88, 275, 276, 1001, 1002, 1003, 1004, 1005, 1006, 1007, 1020
ms.date: 08/03/2022
ms.author: bholtorf

---
# Create Jobs

When you start a new project, you must create a job card with integrated job tasks and job planning lines, structured in two layers.  

The first layer consists of job tasks. You must create at least one job task per job because all posting refers to a job task. Having at least one job task in your job enables you to set up job planning lines and to post consumption to the job.

The second layer consists of job planning lines, which specify the detailed use of resources, items and various general ledger expenses.

The layer structure enables you to divide the job into smaller tasks, and therefore use more specific details in budgeting, quotes, and registration. In addition, it gives you insight into how a job is progressing. For example, you can track whether you're meeting designated milestones or if you're on target to meet budget expectations.

> [!TIP]
> Choose the **New Job** action on the **Project Manager** Role Center to launch an assisted setup guide that takes you through the steps of creating a job with integrated tasks and planning lines. The following procedure describes how to perform the steps manually. For an example of how to create a job manually, see [Video: How to create a job in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw).

Sometimes the party that is receiving a service is different from the party that is paying the bill. On the **Jobs** page, you can specify the customer who will benefit from the project in the **Sell-to** fields, and the party to invoice in the **Bill-to** fields. You can also provide the following information: 

* Where the work will happen by selecting from a list of ship-to addresses for the customer.
* Add information about external references to simplify communication about the project.
* Overwrite the standard financial terms of the project.

## To create a job card

You create a job card and then create job task lines and job planning lines for it.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2. Choose the **New** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To specify the job with information on other jobs, choose the **Copy Job** action, fill in the fields as necessary, and then choose the **OK** button.

> [!NOTE]  
> If you are using time sheets with your job, you must also designate a person responsible. This person can approve time sheets for the employee tasks associated with the job. For more information, see [Set Up Time Sheets](projects-how-setup-time-sheets.md).

Optionally, mark actions on project as blocked using the **Blocked** field. the following table describes the effect of the options for this field.

|Option  |Description  |
|---------|---------|
|Blank |All actions are allowed.|
|Posting    |You can work with planning lines, but the job is blocked for posting. Choosing this option means that you cannot post any usage or sale on the job.|
|All  |All actions are blocked.|

## To create tasks for a job

A key part of creating a job is to specify the various tasks involved in the job. You specify tasks by creating one line per task on the **Tasks** FastTab on the **Job Card** page. Every job must have at least one task.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Open the job card for a relevant job.
3. On the **Tasks** FastTab, fill in the fields as necessary on a new line.
4. To indent tasks and create a hierarchy, Choose the **Tasks** action, the then choose **Indent Job Tasks** action.
5. Repeat steps 3 and 4 for all the tasks that you need for the job.
6. To specify the job tasks with information on other job tasks, choose the **Copy Job Tasks from** action, fill in the fields as necessary, and then choose the **OK** button.

## To create planning lines for a job

You can refine your new job tasks on job planning lines. A planning line can capture the information that you want to track for a job. For example, you can track the resources the job requires, or the items that are needed. For example, you have a task to get a customer to approve a job. You associate the task with planning lines for items such as meeting the customer and assigning a resource.  

A job planning line can have one of the following types.  

| Type | Description |
| --- | --- |
| **Budget** |Provides estimated usage and costs for the job, typically in a time and materials type project. Planning lines of this type can't be invoiced. |
| **Billable** |Provides estimated invoicing to the customer, typically in a fixed price project. |
| **Both Budget and Billable** |Provides budgeted usage equal to what you want to invoice. |

> [!NOTE]
> While you enter information on job planning lines, cost information is automatically filled in. For example, the cost, price, and discount for resources and items are based on information from the resource and item. 

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Open a relevant job card.
3. Select a job task for which the **Job Task Type** field contains **Posting**, and then choose the **Job Planning Lines** action.  
4. On the **Job Planning Lines** page, on a new line, fill in the fields as necessary.
5. Repeat steps 3 and 4 for all planning lines that you need for the job task.

## See also

[Project Management](projects-manage-projects.md)  
[Video: How to create a job in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
