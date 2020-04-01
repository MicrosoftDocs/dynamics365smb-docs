---
title: Set Up Jobs Prices and Job Posting Groups| Microsoft Docs
description: Describes how to set up general jobs information, and set up prices for job items, resources, and G/L accounts and jobs posting groups.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.workload: na
ms.search.keywords: project management
ms.date: 04/01/2020
ms.author: edupont

---
# Set Up Jobs

As a project manager, you can set up jobs that define each of the projects that you manage in [!INCLUDE [prodshort](includes/prodshort.md)]. On the **Jobs Setup** page, you must specify how you want to use certain job features.

For each job, you then specify individual job cards with information about prices for job items, job resources, and job G/L accounts, and you must set up job posting groups.

## To set general information for jobs
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs Setup**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> The impact of the **Apply Usage Link by Default** field is rather complex and is therefore explained in the following section.

### To set up job usage tracking

When you are executing a job, you might want to know how your usage is tracking against your plan. To easily do this, you can create a link between your job planning lines and the actual usage. This lets you track your costs and to easily see at how much work remains to be done. By default, the job planning line type is **Budget**, but using the line type **Both Budget and Billable** has similar effects.

If you select the **Apply Usage Link by Default** field, then you can review information on the job planning line. You can set the quantity of the resource, item, or general ledger account and then indicate what quantity you want to transfer to the job journal. The **Remaining Quantity** field on the job planning line will tell you what remains to be transferred and posted to the job journal.

> [!TIP]  
> You can enable or disable job usage tracking for a specific job. The value of the **Apply Usage Link** field on the individual job card overrides the setting in the **Jobs Setup** page.  

When the **Apply Usage Link by Default** check box is selected, and the job planning line type is **Billable**, a job planning line of type **Budget** is created after you post a job journal line.

> [!IMPORTANT]
> If job usage tracking is enabled, either in the **Jobs Setup** page or on the individual job, and the **Line Type** field on the job journal line is blank, then new job planning lines of line type **Budget** are created when you post job journal lines.  
>  
> If job usage tracking is *not* enabled, either in the **Jobs Setup** page or on the individual job, and the **Line Type** field on the job journal line is blank, then no job planning lines are created when you post job journal lines. For more information, see [Record Usage for Jobs](projects-how-record-job-usage.md).

1. Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Jobs Setup**, and then choose the related link.
2. Select the **Apply Usage Link by Default** check box.

## To set up prices for job resources
You can set up specific prices for resources for a job. You use the **Job Resource Prices** page to do this.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2. Select the relevant job, and then choose the **Resource** action.
3. On the **Job Resource Prices** page, fill in the fields as necessary.

The optional information in the **Job Task No.**, **Work Type**, **Currency Code**, **Line Discount %**, and **Unit Cost Factor** fields will be used on the job planning lines and usage journals when this resource is entered and added to the job.  

The value in the **Unit Price** field for the resource will be used on the job planning lines and job journals when this resource, a resource assigned to the resource group, or any resource is entered.  

> [!NOTE]  
>   This price will always override any prices set up in the existing **Resource Price/Resource Group Prices** page.

## To set up prices for job items
You can set up specific prices for items for a job. You use the **Job Item Prices** page to do this.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2. Select the relevant job, and then choose the **Item** action.
3. On the **Job Item Prices** page, fill in the fields as necessary.

The optional information in the **Job Task No.**, **Currency Code**, and **Line Discount %** fields will be used in the job planning lines and job journals when this item is entered or added to the job.  

The value in the **Unit Price** field for the item will be used on the job planning lines and job journals when this item is entered.  

> [!NOTE]  
>   This price will always override the regular customer price (the “best price” mechanism) for items. If you want to use the regular customer price mechanisms, then you should not create any job item prices for the job.

## To set up prices for job general ledger accounts
You can set up specific prices for general ledger expenses for a job. You use the **Job G/L Account Prices** page to do this.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2. Select the relevant job, and then choose the **G/L Account** action.  
3. On the **Job G/L Account Prices** page, fill in the fields as necessary.

The optional information in the **Job Task No.**, **Currency Code**, **Line Discount %**, **Unit Cost Factor**, and **Unit Cost** fields will be used on the job planning lines and job journals when this general ledger account is entered and added to a job.  

The value in the **Unit Price** field for the general ledger job expense will be used on the job planning lines and job journals when this general ledger account is entered.

## To set up job posting groups
One aspect of planning jobs is deciding which posting accounts to use for job costing. To be able to post jobs, you set up accounts for posting for each job posting group. A posting group represents a link between the job and how it should be treated in the general ledger. When you create a job, you specify a posting group, and by default, each task you create for the job is associated with that posting group. However, as you create tasks, you can override the default and select a posting group that is more appropriate.  

> [!NOTE]  
>   The necessary accounts in the chart of accounts must be set up before you set up posting groups. For more information, see [Set Up or Change the Chart of Accounts](finance-setup-chart-accounts.md).  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Posting Groups**, and then choose the related link.  
2. Choose the **New** action, and then fill in the account fields as described in the following table.  

| Account field | Description |
| --- | --- |
| **Code** |A code for the posting group. You can enter up to 10 characters, including spaces. |
| **WIP Costs Account** |The WIP account for the calculated cost of the job WIP, which is a balance sheet capital asset account. |
| **WIP Accrued Costs Account** |An account for the Cost Value or Cost of Sales method of WIP calculation, which is a balance sheet accrued expense liability account. This will be posted to when the WIP adjustment requires that usage costs posted to the income statement be increased. |
| **Job Costs Applied Account** |A balancing account to the WIP Costs Account, which is a contra for a negative expense account. |
| **Item Costs Applied Account** |A balancing account to the WIP Costs Account, which is a contra for a negative expense account. |
| **Resource Costs Applied Account** |A balancing account to the WIP Costs Account, which is a contra for a negative expense account. |
| **Costs Applied Account** |A balancing account to the WIP Costs Account, which is a contra for a negative expense account. |
| **Job Costs Adjustment Account** |The balancing account to the WIP Accrued Costs account, which is an expense account. |
| **G/L Expense Acc. (Budget)** |The sales account that will be used for general ledger expenses in job tasks with this posting group. If left empty, the general ledger account entered on the job planning line is used. |
| **WIP Accrued Sales Account** |The WIP account for the calculated sales value of the WIP, which is a balance sheet Accrued Revenue account. This is posted to when the WIP adjustment requires the recognized revenue to be increased. |
| **WIP Invoiced Sales Account** |The account for the invoiced sales value of the WIP that is not able to be recognized. It is a balance sheet Unearned Revenue account. |
| **Job Sales Applied Account** |The balancing account to the WIP Invoiced Sales account, which is a contra income account. |
| **Job Sales Adjustment Account** |The balancing account to the WIP Job Sales Account, which is an income account. |
| **Recognized Costs Account** |The expense account that contains the recognized costs for the job. It is a debit expense account ordinarily. |
| **Recognized Sales Account** |The income account that contains the recognized income for the job. It is a credit income account ordinarily. |

## See Also

[Set Up Project Management](projects-setup-projects.md)  
[Video: How to create a job in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw)  
[Managing Projects](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
