---
title: Set Up Jobs, Prices, and Job Posting Groups
description: Describes how to set up general information about jobs.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 04/25/2023
ms.custom: bap-template
ms.search.keywords: project management
ms.search.form: 211, 463, 1012
---
# Set Up Jobs, Prices, and Job Posting Groups

As a project manager, you can set up jobs that define each of the projects that you manage in [!INCLUDE[prod_short](includes/prod_short.md)]. Use the **Jobs Setup** page to define how you'll use job features.

For each job, specify various information:

* Prices for job items
* Job resources
* Job G/L accounts
* Job posting groups (required)

## To set general information for jobs

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs Setup**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> The **Apply Usage Link by Default** toggle on the **Jobs Setup** page indicates whether job ledger entries are linked to job planning lines by default. Turn on the toggle to apply this setting to all new jobs. You can enable or disable job usage tracking for a specific job by turning the **Apply Usage Link** toggle on or off on the **Job Card** page.

### To set up job usage tracking

When you're working on a job, you might want to know how your usage is tracking against your plan. To explore usage, you can create a link between your job planning lines and the actual usage. The link lets you track your costs and understand how much work remains. By default, the job planning line type is **Budget**, but using the line type **Both Budget and Billable** has similar effects.

After you set up usage tracking by turning on the **Apply Usage Link by Default** toggle, you can review information on the job planning line. For example, you can set the quantity of the resource, item, or general ledger account. You can also set the quantity to transfer to the job journal. The **Remaining Quantity** field on the job planning line shows what remains to transfer and post to the job journal.

>[!NOTE]
> If the **Apply Usage Link** is chosen on the job, and the **Line Type** field on the job journal line or purchase line is **Billable**, new job planning lines of the line type **Both Budget and Billable** are created when you post the job journal or purchase document.  
>
> For more information, see [Record Usage for Jobs](projects-how-record-job-usage.md) and [Manage Job Supplies](projects-how-manage-project-supplies.md)

> [!IMPORTANT]
> If you don't specify a value in the **Line Type** field on the job journal line or purchase line, job planning lines aren't created when you post the job journal or purchase document.

## To set up prices for resources, items, and general ledger accounts for jobs

> [!NOTE]
> In 2020 release wave 2, we released new processes for setting up and managing prices and discounts. If you're a new customer, you're using the new experience. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

You can set up prices for the items, resources, and general ledger accounts related to a job. 

#### [Current Experience](#tab/current-experience)

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2. Select the job, and then choose the **Resource**, **Item**, or **G/L Account** action.
3. On the **Job Resource Prices**, **Job Item Prices**, or **Job G/L Account Prices** pages, fill in the fields as necessary.

When you choose a resource, item, or general ledger account for a job, [!INCLUDE [prod_short](includes/prod_short.md)] uses information in the optional fields on job planning lines and job journals. The following table explains how.

|Column1  |Column2  |
|---------|---------|
|**Job Resources**|The **Job Task No.**, **Work Type**, **Currency Code**, **Line Discount %**, and **Unit Cost Factor** fields. The value in the **Unit Price** field for the resource is used on job planning lines and job journals when you enter a resource, or a resource assigned to the resource group. This price overrides prices specified on the **Resource Price/Resource Group Prices** page.|
|**Job Items**|The **Job Task No.**, **Currency Code**, and **Line Discount %** fields. The value in the **Unit Price** field for the item will be used on the job planning lines and job journals when this item is entered. This price overrides the regular customer price (the "best price" mechanism) for items. To use the regular customer price, don't specify job item prices for the job.|
|**General Ledger Accounts**|The information in the **Job Task No.**, **Currency Code**, **Line Discount %**, **Unit Cost Factor**, and **Unit Cost** fields will be used on the job planning lines and job journals when this general ledger account is entered and added to a job. When you choose a general ledger account, job planning lines and job journals use the value in the **Unit Price** field for the general ledger job expense.|

#### [New Experience](#tab/new-experience)

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2. Select the relevant job, and then choose the **Sales Price Lists** action.

---

## To set up job posting groups

One aspect of planning jobs is deciding which posting accounts to use for job costing. To be able to post jobs, you set up accounts for posting for each job posting group. A posting group represents a link between the job and how it should be treated in the general ledger. When you create a job, you specify a posting group, and by default, each task you create for the job is associated with that posting group. However, as you create tasks, you can override the default and select a posting group that is more appropriate.  

> [!NOTE]  
> You must set up accounts in the chart of accounts before you set up posting groups. For more information, see [Set Up or Change the Chart of Accounts](finance-setup-chart-accounts.md).  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Posting Groups**, and then choose the related link.  
2. Choose the **New** action, and then fill in the fields as described in the following table.  

| Account field | Description | Used in WIP Type |
| --- | --- |  --- |
| **Code** |An identifier for the posting group. You can enter up to 10 characters, including spaces. | |
| **WIP Costs Account** |The WIP account for the calculated cost of the job WIP, which is a balance sheet capital asset account. | Applied Cost, Recognized Costs|
| **WIP Accrued Costs Account** |An account for the Cost Value or Cost of Sales method of WIP calculation. This account is for accrued expense liability on your balance sheet. When a WIP adjustment requires you to increase the usage costs that you post to your income statement, you post to this account. | Accrued Costs|
| **Job Costs Applied Account** |A balancing account to the WIP Costs Account, which is a contra for a negative expense account. Used when **WIP Posting Method Used** is set to *Job*. | Applied Costs, Recognized Costs|
| **Item Costs Applied Account** |Same as  **Job Costs Applied Account**, but used when **WIP Posting Method Used** is set to *Job Ledger Entry*.| |
| **Resource Costs Applied Account** |Same as  **Job Costs Applied Account**, but used when **WIP Posting Method Used** is set to *Job Ledger Entry*.| |
| **G/L Costs Applied Account** |Same as  **Job Costs Applied Account**, but used when **WIP Posting Method Used** is set to *Job Ledger Entry*.| |
| **Job Costs Adjustment Account** |The balancing account to the WIP Accrued Costs account, which is an expense account. | Accrued Costs|
| **G/L Expense Acc. (Budget)** |The sales account that will be used for general ledger expenses in job tasks with this posting group. If left empty, the general ledger account entered on the job planning line is used. | |
| **WIP Accrued Sales Account** |The WIP account for the calculated sales value of the WIP, which is an accrued revenue account for your balance sheet. When a WIP adjustment requires you to increase the recognized revenue, you post to this account. | Accrued Sales, Recognized Sales|
| **WIP Invoiced Sales Account** |The account for the invoiced sales value of the WIP that is not able to be recognized. It is a balance sheet Unearned Revenue account. | Recognized Sales, Applied Sales|
| **Job Sales Applied Account** |The balancing account to the WIP Invoiced Sales account, which is a contra income account. | Applied Sales, Recognized Sales|
| **Job Sales Adjustment Account** |The balancing account to the WIP Job Sales Account, which is an income account. | Accrued Sales|
| **Recognized Costs Account** |The expense account that contains the recognized costs for the job. It is a debit expense account ordinarily. | Recognized Costs|
| **Recognized Sales Account** |The income account that contains the recognized income for the job. It is a credit income account ordinarily. | Recognized Sales|

## See also

[Set Up Project Management](projects-setup-projects.md)  
[Video: How to create a job in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw)  
[Managing Projects](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
