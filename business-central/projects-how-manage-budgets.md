---
title: Set Up and Manage a Budget for a Project
description: Describes how to plan resources and forecast and control the costs of a project by setting up a budget for each project.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: project budget, forecast
ms.search.form: 1002, 1007
ms.date: 02/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Manage Project Budgets

You can set up a budget for each project. The budget is used to plan the resources that you allocate to a project. The budget can be either general with few entries or it can contain more entries that are divided into activity levels. You can then compare the budgeted amounts with the actual usage as recorded in the project journal. By monitoring differences between actual usage and budgeted usage, you can control an ongoing project and improve the quality of future projects by reducing the risk of underestimating costs.

The following procedure describes how to estimate budgeted costs during planning. For information about recording budgeted versus actual project prices and costs, see [Record Usage for Projects](projects-how-record-job-usage.md).  

## <a name="JobBudgetCosts"></a> To estimate the budgeted costs for a project

When a customer wants to know the price of a project that will be invoiced based on usage, you must determine the budgeted costs for the project. Use the **Project Task Lines** page to do that.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, and then choose the related link.  
2. Open a relevant project.
3. Select a task line of type Posting, and then choose the **Project Planning Lines** action.
4. On a new line, fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

For the **Line Type** field, refer to the following information.  

| Line Type | Description |
| --- | --- |
| **Both Budget and Billable** |The cost and price amounts entered on the planning line are the budgeted costs for the particular planning line. The price amount will be invoiced. |
| **Budget** |The customer is not charged for usage. Usage isn't transferred to an invoice, but is used to calculate WIP. |
| **Billable** |The customer is charged for usage. Usage is transferred to the invoice, based on the quantity specified in the **Qty. to Transfer to Invoice** field. |

> [!NOTE]  
> The **Planned Delivery Date** field for the planning line contains the date when usage related to the planning line is expected to be completed. It is also the date when the planning line may be transferred to a sales invoice and posted. <br /><br /> On the underlying project task on the **Project Card** page, the **Start Date** and **End Date** fields respectively contain the value of the **Planned Delivery Date** field on the earliest and latest project planning lines in the related **Project Planning Lines** page.

> [!NOTE]  
> When you fill in the **Quantity** field, all total price and total cost information will be calculated and filled in for that planning line. You can edit them at any time.

On the **Project Card** page, you can now see a summary of the total budgeted costs, budgeted price, billable cost and billable price for each task.

For information about recording budgeted versus actual project prices and costs, see [Record Usage for Projects](projects-how-record-job-usage.md).

## Related information

[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
