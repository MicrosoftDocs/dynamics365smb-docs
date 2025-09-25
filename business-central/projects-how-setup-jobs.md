---
title: Set up projects, prices, and project posting groups
description: Describes how to set up general information about projects.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/17/2025
ms.custom: bap-template
ms.search.keywords: project management
ms.search.form: 211, 463, 1012
ms.service: dynamics-365-business-central
---
# Set up projects, prices, and project posting groups

As a project manager, you can set up each of the projects that you manage in [!INCLUDE[prod_short](includes/prod_short.md)]. Use the **Project Setup** page to define how you'll use project features.

For each project, specify various information:

* Prices for project items
* Project resources
* Project G/L accounts
* Project posting groups (required)

## To set general information for projects

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project Setup**, and then choose the related link.
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> The **Apply Usage Link by Default** toggle on the **Projects Setup** page indicates whether project ledger entries are linked to project planning lines by default. Turn on the toggle to apply this setting to all new projects. You can enable or disable project usage tracking for a specific project by turning the **Apply Usage Link** toggle on or off on the **Project Card** page. The **Apply Usage Link** toggle also activates warehouse handling, planning, assembly-to-order, item tracking, and reservation capabilities for project.

### To set up project usage tracking

When you're working on a project, you might want to know how your usage is tracking against your plan. To explore usage, you can create a link between your project planning lines and the actual usage. The link lets you track your costs and understand how much work remains. By default, the project planning line type is **Budget**, but using the line type **Both Budget and Billable** has similar effects.

After you set up usage tracking by turning on the **Apply Usage Link by Default** toggle, you can review information on the project planning line. For example, you can set the quantity of the resource, item, or general ledger account. You can also set the quantity to transfer to the project journal. The **Remaining Quantity** field on the project planning line shows what remains to transfer and post to the project journal.

>[!NOTE]
> If the **Apply Usage Link** is chosen on the project, and the **Line Type** field on the project journal line or purchase line is **Billable**, new project planning lines of the line type **Both Budget and Billable** are created when you post the project journal or purchase document.  
>
> For more information, see [Record Usage for Projects](projects-how-record-job-usage.md) and [Manage Project Supplies](projects-how-manage-project-supplies.md)

> [!IMPORTANT]
> If you don't specify a value in the **Line Type** field on the project journal line or purchase line, project planning lines aren't created when you post the project journal or purchase document.

### Invoice multiple customers for project tasks

When projects involve multiple customers, billing the right customers for the right tasks can be challenging. [!INCLUDE [prod_short](includes/prod_short.md)] makes billing less complex by letting you specify the bill-to and sell-to customers on each project task line, so you can automatically generate invoices for the correct customers.  Use the **Default Task Billing Method** field to specify whether you're billing one customer, or multiple customers by default. You can change task billing method for a specific project by using the **Task Billing Method** field on the **Project Card** page. To learn more about invoicing multiple customers, go to [Invoice one or more customers for project tasks](projects-how-create-jobs.md#invoice-one-or-more-customers-for-project-tasks).

### Synchronize the cost of used items

The cost of an item (inventory value) that you purchase and later use in project might change during its lifetime. For example, because a freight cost is added to its purchase cost after you post the usage of the item.

In [!INCLUDE [prod_short](includes/prod_short.md)], you can manually or automatically adjust item costs. The adjustment is reflected in the value entries and general ledger. To learn more, go to [Managing Inventory Cost](finance-manage-inventory-costs.md)

In relation to projects, you also have options for how to reflect those adjustments.

To ensure that cost changes automatically adjust in a project each time the **Adjust Cost - Item Entries** batch job is run, turn on the **Automatic Update Project Item Cost** toggle.

If you keep it off, remember to run the **Update Job Project Cost** task manually or by using a job queue entry.

## To set up prices for resources, items, and general ledger accounts for projects

> [!NOTE]
> In 2020 release wave 2, we released new processes for setting up and managing prices and discounts. If you're a new customer, you're using the new experience. If you're an existing customer, whether you are using the new experience depends on whether your administrator has enabled the **New sales pricing experience** feature update in **Feature Management**. For more information, see [Enabling Upcoming Features Ahead of Time](/dynamics365/business-central/dev-itpro/administration/feature-management).

You can set up prices for the items, resources, and general ledger accounts related to a project. 

#### [Current Experience](#tab/current-experience)

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project**, and then choose the related link.  
2. Select the project, and then choose the **Resource**, **Item**, or **G/L Account** action.
3. On the **Project Resource Prices**, **Project Item Prices**, or **Project G/L Account Prices** pages, fill in the fields as necessary.

When you choose a resource, item, or general ledger account for a project, [!INCLUDE [prod_short](includes/prod_short.md)] uses information in the optional fields on project planning lines and project journals. The following table explains how.

|Column1  |Column2  |
|---------|---------|
|**Project Items**|The **Project Task No.**, **Currency Code**, and **Line Discount %** fields. The value in the **Unit Price** field for the item will be used on the project planning lines and project journals when this item is entered. This price overrides the regular customer price (the "best price" mechanism) for items. To use the regular customer price, don't specify project item prices for the project.|
|**General Ledger Accounts**|The information in the **Project Task No.**, **Currency Code**, **Line Discount %**, **Unit Cost Factor**, and **Unit Cost** fields will be used on the project planning lines and project journals when this general ledger account is entered and added to a project. When you choose a general ledger account, project planning lines and project journals use the value in the **Unit Price** field for the general ledger project expense.|
|**Project Resources**|The **Project Task No.**, **Work Type**, **Currency Code**, **Line Discount %**, and **Unit Cost Factor** fields. The value in the **Unit Price** field for the resource is used on project planning lines and project journals when you enter a resource, or a resource assigned to the resource group. This price overrides prices specified on the **Resource Price/Resource Group Prices** page.|

#### [New Experience](#tab/new-experience)

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, and then choose the related link.  
2. Select the relevant project, and then choose the **Sales Price Lists** action.

---

## To set up project posting groups

One aspect of planning projects is deciding which posting accounts to use for project costing. To be able to post projects, you set up accounts for posting for each project posting group. A posting group represents a link between the project and how it should be treated in the general ledger. When you create a project, you specify a posting group, and by default, each task you create for the project is associated with that posting group. However, as you create tasks, you can override the default and select a posting group that is more appropriate.  

> [!NOTE]  
> You must set up accounts in the chart of accounts before you set up posting groups. For more information, see [Set Up or Change the Chart of Accounts](finance-setup-chart-accounts.md).  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project Posting Groups**, and then choose the related link.  
2. Choose the **New** action, and then fill in the fields as described in the following table.  

| Account field | Description | Used in WIP Type |
| --- | --- |  --- |
| **Code** |An identifier for the posting group. You can enter up to 10 characters, including spaces. | |
| **WIP Costs Account** |The WIP account for the calculated cost of the project WIP, which is a balance sheet capital asset account. | Applied Cost, Recognized Costs|
| **WIP Accrued Costs Account** |An account for the Cost Value or Cost of Sales method of WIP calculation. This account is for accrued expense liability on your balance sheet. When a WIP adjustment requires you to increase the usage costs that you post to your income statement, you post to this account. | Accrued Costs|
| **Project Costs Applied Account** |A balancing account to the WIP Costs Account, which is a contra for a negative expense account. Used when **WIP Posting Method Used** is set to *Project*. | Applied Costs, Recognized Costs|
| **Item Costs Applied Account** |Same as  **Project Costs Applied Account**, but used when **WIP Posting Method Used** is set to *Project Ledger Entry*.| |
| **Resource Costs Applied Account** |Same as  **Project Costs Applied Account**, but used when **WIP Posting Method Used** is set to *Project Ledger Entry*.| |
| **G/L Costs Applied Account** |Same as  **Project Costs Applied Account**, but used when **WIP Posting Method Used** is set to *Project Ledger Entry*.| |
| **Project Costs Adjustment Account** |The balancing account to the WIP Accrued Costs account, which is an expense account. | Accrued Costs|
| **G/L Expense Acc. (Budget)** |The sales account that will be used for general ledger expenses in project tasks with this posting group. If left empty, the general ledger account entered on the project planning line is used. | |
| **WIP Accrued Sales Account** |The WIP account for the calculated sales value of the WIP, which is an accrued revenue account for your balance sheet. When a WIP adjustment requires you to increase the recognized revenue, you post to this account. | Accrued Sales, Recognized Sales|
| **WIP Invoiced Sales Account** |The account for the invoiced sales value of the WIP that is not able to be recognized. It is a balance sheet Unearned Revenue account. | Recognized Sales, Applied Sales|
| **Project Sales Applied Account** |The balancing account to the WIP Invoiced Sales account, which is a contra income account. | Applied Sales, Recognized Sales|
| **Project Sales Adjustment Account** |The balancing account to the WIP Project Sales Account, which is an income account. | Accrued Sales|
| **Recognized Costs Account** |The expense account that contains the recognized costs for the project. It is a debit expense account ordinarily. | Recognized Costs|
| **Recognized Sales Account** |The income account that contains the recognized income for the project. It is a credit income account ordinarily. | Recognized Sales|

### Allow multiple people to post project transactions at the same time

To allow people to post transactions for projects at the same time, you can enable the **Enable multiple users to post job ledger entries at the same time** feature update on the **Feature Management** page. By default, the feature isn’t enabled.

> [!NOTE]
> Similar features are available for resource, inventory, and warehouse entries. To learn more, go to:
>
> * [Allow multiple people to post resource transactions at the same time](projects-how-setup-resources.md#allow-multiple-people-to-post-resource-transactions-at-the-same-time)
> * [Allow workers to post inventory transactions at the same time](inventory-how-setup-general.md#allow-workers-to-post-transactions-at-the-same-time)
> * [Design details: Creating warehouse entries](design-details-warehouse-entries.md)

If you enable the feature, [!INCLUDE [prod_short](includes/prod_short.md)] assigns entry numbers for each table from `SequenceNumbers` in the database, which allows people to post transactions at the same time. The result can be that sometimes entries from two or more transactions are interleaved.

There's a similar feature for inventory transactions. An item register might contain any or all of the entry tables, as shown in the following image.

:::image type="content" source="media/interleaved inventory tables.png" alt-text="Screenshot that shows the item register with several entry tables." lightbox="media/interleaved inventory tables.png":::

If you don’t enable the feature, when someone posts a transaction the tables are locked and other users can’t post. [!INCLUDE [prod_short](includes/prod_short.md)] finds the last entry in each table and assigns a number that’s one higher. This numbering ensures that entries that belong to the same register are consecutive, but prevents other people from posting at the same time.

> [!NOTE]
> You might not want to enable the feature if you have a feature or extension that:
>
> * Relies on consecutive entry numbers.
> * Requires that tables are locked throughout the posting process.

## Related information

[Set Up Project Management](projects-setup-projects.md)  
[Video: How to create a project in Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw)  
[Managing Projects](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
