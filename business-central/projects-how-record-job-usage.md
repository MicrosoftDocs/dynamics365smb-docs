---
title: Record Consumption or Usage of Job Resources and Items
description: This article describes how to record the consumption or use of items or resources for jobs in project management.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 03/08/2023
ms.custom: bap-template
---
# Record Consumption or Usage for Jobs

From the **Job Card** page, you can open the **Job Planning Lines** page to review and record use on various parts of your job. This information is automatically updated when you modify and transfer information between jobs and job journals or job invoices. This requires that you turn on the **Apply Usage Link by Default** toggle on the **Job Setup** page. Learn more at [Set Up Jobs](projects-how-setup-jobs.md).  

For example, for planning lines of type **Budget**, you can enter the quantity of a resource, and then specify the quantity to transfer to the job journal. If the type of the planning line is **Billable**, you can enter the quantity of the resource, and then specify the quantity to transfer to an invoice. To learn more about invoicing the customer, go to [Invoice Jobs](projects-how-invoice-jobs.md). By comparing the original quantity, remaining quantity, or posted quantity you can quickly review use information. To learn more about how to estimate budgeted values during planning, go to [Manage Job Budgets](projects-how-manage-budgets.md).  

The following procedures describe how to record actual (budgeted) quantities and costs with a job journal. Alternatively, you can use purchase documents to record purchases for a job. Learn more at [Manage Job Supplies](projects-how-manage-project-supplies.md).

## To record usage for a job planning line of type Budget

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.  
2. Select the job, and then choose the **Job Planning Lines** action. 
3. Select a job planning line of type **Budget** or **Both Budget and Billable** for which you want to record usage.   

    > [!NOTE]
    > You can also record usage for a job planning line of type **Billable**. Typically, you use these lines to create invoices, but you can also transfer the information to a journal. Learn more at [Invoice Jobs](projects-how-invoice-jobs.md) 

4. In the **Qty. To Transfer to Journal** field, enter the quantity to transfer. The default quantity is the value that you enter in the **Quantity** field.

    The **Remaining Quantity** field shows the quantity that remains to complete the job and transfer to the journal.
5. Choose the **Create Job Journal Lines** action.

    > [!TIP]
    > If you are going to add more job planning lines for this job, wait with this step until you have added all job planning lines.
6. On the **Job Transfer Job Planning Line** page, fill in the fields as necessary, and then choose the **OK** button. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Choose the **Open Job Journal** action.  
8. On the **Job Journal** page, select the relevant line and then choose the **Post** action.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

9. On the **Job Planning Lines** page, review the recorded usage by observing the **Quantity**, **Remaining Quantity**, and **Qty. To Transfer to Journal** fields.  
10. Repeat steps 3 through 8 to record additional usage.  

## To create job journal lines manually

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.  
2. In the **Batch Name** field, choose a relevant job journal batch.  
3. On a new line, enter document number, job number, job task number, type, and the quantity of the type being consumed.  
4. When the job journal lines are complete, choose the **Post** action.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## To view job usage estimates and post updates

You can view job usage up to the completion of a project in one step. To do so, you use the **Job Calc. Remaining Usage** batch job for all the tasks up to and including the end of a job.  

This lets you track and compare your original estimates against actual results and make modifications or new entries as needed. For example, you may have estimated that a job required 10 hours, and to date, it has taken 15 hours. You can add the extra five hours to the existing journal line or create a new journal line to report these five hours as overtime, which is another work type. The appropriate cost and price are calculated, and you can then post to the journal.  

> [!NOTE]  
> Item entries create item ledger entries and reduce the inventory quantity. The **Post Inventory Cost to G/L** batch job transfers the cost from inventory to the general ledger. Resource entries create resource ledger entries.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.  
2. Select a relevant job journal, and then choose the **Calc. Remaining Usage** action.  
3. On the **Job Calc. Remaining Usage** page, enter the document number and posting date that is to be inserted in the journal, and then choose the **OK** button.  
4. Update the journal with any modifications that may be needed.  
5. Choose the **Post**.

## Create inventory and warehouse pick documents for a job

To create inventory and warehouse pick documents for jobs, your administrator must enable **Feature Update: Enable inventory and warehouse pick from Jobs** on the **Feature Management** page.

The feature adds the **Create Inventory Pick** and **Create Warehouse Pick** actions to the **Job Card**. To create or register a pick document, use the **Put-away/Pick Lines/Movement Lines** or **Registered Pick Lines** actions. Learn more at [Flows for Production, Assembly, and Jobs](design-details-internal-warehouse-flows.md).

You can use the actions under the following conditions:

* The **Status** of the job is **Open**.
* The **Line Type** of the job planning line is **Budget** or **Both Budget and Billable**.
* The **Type** of the job planning line is **Item**.
* **Require Pick** is enabled for the related location.
* **Directed Pick and Put-away** is disabled.

> [!NOTE] 
> Although the setting is called **Require Pick**, you can still post consumption directly from the job journal line for the location. If your location is set up to require pick processing but not shipment processing, you use the **Inventory Pick** page to organize and print the picking information. You also use the page to enter and post the result of the pick, which in turn posts the consumption of the items. 
> 
> If your location is set up to require both pick and shipment processing, meaning that you have chosen both the **Require Pick** and **Require Shipment** fields on the **Location Card** page, use the **Warehouse Pick** page to handle the pick. Warehouse picks are similar to inventory picks. The difference is that rather than posting the picking information you register the pick. This registration doesn't post consumption, it just makes the items available for posting. As a warehouse manager, you can use a pick worksheet to organize pick information before creating the individual warehouse pick instructions

## To review planning lines for a job ledger entry

After you have posted job journal lines, you can see the planning lines that are associated with the job journal entries that have been posted.

> [!NOTE]  
> This requires that the **Apply Usage Link** check box has been selected for the job. For more information, see [Set Up Jobs](projects-how-setup-jobs.md).  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job Journals**, and then choose the related link.  
2. Select a relevant job journal, and then choose the **Ledger Entries** action.  
3. On the **Job Ledger Entries** page, choose **Show Linked Job Planning Lines** action.

## See also

[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
