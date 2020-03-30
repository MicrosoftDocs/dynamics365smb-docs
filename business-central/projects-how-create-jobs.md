---
title: Create a Job Card for a Job and Specify Tasks| Microsoft Docs'
description: For a new project, you create a job card that contains job tasks and planning lines, to help you manage progress and budgets.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.workload: na
ms.search.keywords: project management, task
ms.date: 04/01/2020
ms.author: sgroespe

---
# Create Jobs
When you start a new project, you must create a job card with integrated job tasks and job planning lines, structured in two layers.  

The first layer consists of job tasks. You must create at least one job task per job because all posting refers to a job task. Having at least one job task in your job enables you to set up job planning lines and to post consumption to the job.

The second layer consists of job planning lines, which specify the detailed use of resources, items and various general ledger expenses.

The layer structure enables you to divide the job into smaller tasks, and therefore use more specific details in budgeting, quotes, and registration. In addition, it gives you insight into how a job is progressing. For example, you can track whether you are meeting designated milestones or if you are on target to meet budget expectations.

> [!TIP]
> Choose the **New Job** action on the **Project Manager** Role Center to launch an assisted setup guide that takes you through the steps of creating a job with integrated tasks and planning lines. The following procedure describes how to perform the steps manually. For an example of how to create a job manually, see [Video: How to create a job in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw).

## To create a job card
You create a job card and then create job task lines and job planning lines for it.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2. Choose the **New** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To specify the job with information on other jobs, choose the **Copy Job** action, fill in the fields as necessary, and then choose the **OK** button.

> [!NOTE]  
>   If you are using time sheets with your job, you must also designate a person responsible. This person can approve time sheets for the employee tasks associated with the job. For more information, see [Set Up Timesheets](projects-how-setup-time-sheets.md).

## To create tasks for a job
A key part of creating a job is to specify the various tasks involved in the job. You do this by adding new lines on the **Tasks** FastTab on the **Job Card** page, one task per line. Every job must have at least one task.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Open the job card for a relevant job.
3. On the **Tasks** FastTab, fill in the fields as necessary on a new line.
4. To indent tasks and create a hierarchy, Choose the **Tasks** action, the then choose **Indent Job Tasks** action.
5. Repeat steps 3 and 4 for all the tasks that you need for the job.
6. To specify the job tasks with information on other job tasks, choose the **Copy Job Tasks from** action, fill in the fields as necessary, and then choose the **OK** button.

## To create planning lines for a job
You can refine your new job tasks on job planning lines. A planning line can be used to capture any information that you want to track for a job. You can use planning lines to add information such as what resources are required or to capture what items are needed to perform the job. For example, if you have a task to obtain customer approval of a job, you can associate that task with planning lines for items such as meeting with the customer and assigning a resource.  

A job planning line can have one of the following types.  

| Type | Description |
| --- | --- |
| **Budget** |Provides estimated usage and costs for the job, typically in a time and materials type project. Planning lines of this type cannot be invoiced. |
| **Billable** |Provides estimated invoicing to the customer, typically in a fixed price project. |
| **Both Budget and Billable** |Provides budgeted usage equal to what you want to invoice. |

**Note**. As you enter information on job planning lines, cost information is automatically filled in. For example, the cost, price, and discount for resources and items are initially based on the information that is defined on the resource and item cards.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Open a relevant job card.
3. Select a job task for which the **Job Task Type** field contains **Posting**, and then choose the **Job Planning Lines** action.  
4. On the **Job Planning Lines** page, on a new line, fill in the fields as necessary.
5. Repeat steps 3 and 4 for all planning lines that you need for the job task.

## See Also

[Project Management](projects-manage-projects.md)  
[Video: How to create a job in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
