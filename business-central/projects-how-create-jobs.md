---
title: Create a project card for a project and specify tasks
description: For a new project, you create a project card that contains project tasks and planning lines, to help you manage progress and budgets.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: project management, task
ms.search.form: 88, 275, 276, 1001, 1002, 1003, 1004, 1005, 1006, 1007, 1020
ms.date: 02/24/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Create projects

When you start a new project, you must create a project card with integrated project tasks and project planning lines, structured in two layers.  

The first layer consists of project tasks. You must create at least one project task per project because all posting refers to a project task. Having at least one project task in your project enables you to set up project planning lines and to post consumption to the project.

The second layer consists of project planning lines, which specify the detailed use of resources, items and various general ledger expenses.

The layer structure enables you to divide the project into smaller tasks, and therefore use more specific details in budgeting, quotes, and registration. In addition, it gives you insight into how a project is progressing. For example, you can track whether you're meeting designated milestones or if you're on target to meet budget expectations.

> [!TIP]
> Choose the **New Project** action on the **Project Manager** Role Center to launch an assisted setup guide that takes you through the steps of creating a project with integrated tasks and planning lines. The following procedure describes how to perform the steps manually. <!-- For an example of how to create a project manually, go to [Video: How to create a project in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw).-->

## To create a project card

You create a project card and then create project task lines and project planning lines for it.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, and then choose the related link.  
2. Choose the **New** action, and then fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. To base the project on information from another project, choose the **Copy Project** action, fill in the fields as necessary, and then choose the **OK** button.

> [!NOTE]  
> If you're using time sheets with your project, you must also designate a person responsible. This person can approve time sheets for the employee tasks associated with the project. For more information, see [Set Up Time Sheets](projects-how-setup-time-sheets.md).

> [!NOTE]  
> The **Apply Usage Link** toggle indicates whether project ledger entries are linked to project planning lines. The **Apply Usage Link** toggle also activates warehouse handling, planning, assembly-to-order, item tracking, and reservation capabilities for a project.

Optionally, mark actions on project as blocked using the **Blocked** field. The following table describes the effect of the options for this field.

|Option  |Description  |
|---------|---------|
|Blank |All actions are allowed.|
|Posting    |You can work with planning lines, but the project is blocked for posting. You can't post usage or sales for the project.|
|All  |All actions are blocked.|

## To create tasks for a project

A key part of creating a project is to specify the various tasks involved in the project. You specify tasks by creating one line per task on the **Tasks** FastTab on the **Project Card** page. Every project must have at least one task.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, and then choose the related link.
2. Open the project card for a relevant project.
3. On the **Tasks** FastTab, fill in the fields as necessary on a new line.
4. To indent tasks and create a hierarchy, Choose the **Tasks** action, the then choose **Indent Project Tasks** action.
5. Repeat steps 3 and 4 for all the tasks that you need for the project.
6. To specify the project tasks with information on other project tasks, choose the **Copy Project Tasks from** action, fill in the fields as necessary, and then choose the **OK** button.

## Invoice one or more customers for project tasks

Sometimes the party that is receiving a service is different from the party that pays the bill. Also, sometimes you might need to invoice multiple customers for tasks in the project. On the **Project Card** page, use the **Task Billing Method** field to specify whether you're billing one customer, or multiple customers.

If the customer who is receiving the service also pays the bill, in the **Bill-to** and **Ship-to** fields, choose **Default (Customer)** and **Default (Sell-to Address)**.

If you're billing multiple customers, you can specify the customer who receives the service and the customer to invoice for each task in the project. You can also provide the following information:

* Select the ship-to address for the customer where the work happens.
* Add information about external references to simplify communication about the project.
* Overwrite the standard financial terms of the project.

## Specify a default location for project items

You can save time on data entry by specifying a default location and bin for projects on the **Project Card** page. When you create tasks, project planning lines, and project journal lines for the project, [!INCLUDE [prod_short](includes/prod_short.md)] assigns the default location. You can, however, change the location code and bin on tasks and lines if needed.

If you define a **To-Project Bin Code** on the location, the bin code is populated when you select the location code. If your warehouse flow requires warehouse picks, you can also define other bins from which to consume items.

These fields are the defaults when you create project tasks. Existing project tasks don't change.

There are a few things to know about using default locations:

* For project tasks, if you define a **To-Project Bin Code** on the location, the bin code is assigned when you select the location code. If your warehouse flow requires warehouse picks, you can also define other bins from which to consume items.
* For project planning lines, the **Location Code** is based on the value selected on the project planning line when you select an item. If a bin code isn't defined for the project task, the bin from the default bin content is selected. You can change both values manually.
* For project journal lines, the **Location Code** is based on the value selected on the job journal line when you select an item. If a bin code isn't defined for the project task, the bin from default bin content is selected. You can change both values manually.

> [!NOTE]
> The processes businesses use to pick items in their warehouses differ, depending on whether they use basic or advanced warehouse configurations. To learn more about the options for warehouse configuration, go to [Overview of different configuration options](design-details-warehouse-management.md#overview-of-different-configuration-options).

## To create planning lines for a project

You can refine your new project tasks on project planning lines. A planning line can capture the information that you want to track for a project. For example, you can track the resources the project requires, or the items that are needed. For example, you have a task to get a customer to approve a project. You associate the task with planning lines for items such as meeting the customer and assigning a resource.  

A project planning line can have one of the types described in the following table.  

| Type | Description |
| --- | --- |
| **Budget** |Provides estimated usage and costs for the project, typically in a time and materials type project. You can't invoice planning lines of this type. |
| **Billable** |Provides estimated invoicing to the customer, typically in a fixed price project. |
| **Both Budget and Billable** |Provides budgeted usage equal to what you want to invoice. |

> [!NOTE]
> While you enter information on project planning lines, cost information is automatically filled in. For example, the cost, price, and discount for resources and items are based on information from the resource and item.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, and then choose the related link.
2. Open a relevant project card.
3. Select a project task for which the **Project Task Type** field contains **Posting**, and then choose the **Project Planning Lines** action.  
4. On the **Project Planning Lines** page, on a new line, fill in the fields as necessary.
5. Repeat steps 3 and 4 for all planning lines that you need for the project task.

> [!TIP]
> If the line is for an item, you can use the **Item Availability by** action to explore the item's availability by location, event, or period.

## Avoid document number errors when you post project journals

If you use a number series for project journal batches, you can't post the journal if the document numbers aren't consecutive. If needed, you can correct the order of document numbers when you post project journals.

On the **Project Journals** page, the **Document No.** field is editable so that you can specify different document numbers for different journal lines, or the same document number for related journal lines.

If a number series is specified in the **No. Series** field on the project journal batch, document numbers for individual or grouped lines must be sequential when you post a project journal. If they aren't, you can't post the journal. To avoid getting stuck, use the **Renumber Document Numbers** action on the **Project Journals** page before you post the journal. If you group journal lines by document number before you use the action, they stay grouped but might be assigned a different document number.

> [!TIP]
> The **Renumber Document Numbers** action also works on filtered views.

## Related information

[Project Management](projects-manage-projects.md)  
[Video: How to create a project in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
