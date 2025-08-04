---
title: Record Consumption or Usage of Project Resources and Items
description: This article describes how to record the consumption or use of items or resources for projects in project management.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 02/22/2024
ms.custom: bap-template
---
# Record consumption or usage for projects

From the **Project Card** page, you can open the **Project Planning Lines** page to review and record use on various parts of your project. This information is automatically updated when you modify and transfer information between projects and project journals or project invoices. This requires that you turn on the **Apply Usage Link by Default** toggle on the **Project Setup** page. Learn more at [Set Up Projects](projects-how-setup-jobs.md).  

For example, for planning lines of type **Budget**, you can enter the quantity of a resource, and then specify the quantity to transfer to the project journal. If the type of the planning line is **Billable**, you can enter the quantity of the resource, and then specify the quantity to transfer to an invoice. To learn more about invoicing the customer, go to [Invoice Projects](projects-how-invoice-jobs.md). By comparing the original quantity, remaining quantity, or posted quantity you can quickly review use information. To learn more about how to estimate budgeted values during planning, go to [Manage Project Budgets](projects-how-manage-budgets.md).  

The following procedures describe how to record actual (budgeted) quantities and costs with a project journal. Alternatively, you can use purchase documents to record purchases for a project. Learn more at [Manage Project Supplies](projects-how-manage-project-supplies.md).

## To record usage for a project planning line of type Budget

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Projects**, and then choose the related link.  
2. Select the project, and then choose the **Project Planning Lines** action. 
3. Select a project planning line of type **Budget** or **Both Budget and Billable** for which you want to record usage.   

    > [!NOTE]
    > You can also record usage for a project planning line of type **Billable**. Typically, you use these lines to create invoices, but you can also transfer the information to a journal. Learn more at [Invoice Projects](projects-how-invoice-jobs.md) 

4. In the **Qty. To Transfer to Journal** field, enter the quantity to transfer. The default quantity is the value that you enter in the **Quantity** field.

    The **Remaining Quantity** field shows the quantity that remains to complete the project and transfer to the journal.
5. Choose the **Create Project Journal Lines** action.

    > [!TIP]
    > If you are going to add more project planning lines for this project, wait with this step until you have added all project planning lines.
6. On the **Project Transfer Project Planning Line** page, fill in the fields as necessary, and then choose the **OK** button. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Choose the **Open Project Journal** action.  
8. On the **Project Journal** page, select the relevant line and then choose the **Post** action.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

9. On the **Project Planning Lines** page, review the recorded usage by observing the **Quantity**, **Remaining Quantity**, and **Qty. To Transfer to Journal** fields.  
10. Repeat steps 3 through 8 to record additional usage.  

## To create project journal lines manually

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Project Journals**, and then choose the related link.  
2. In the **Batch Name** field, choose a relevant project journal batch.  
3. On a new line, enter document number, project number, project task number, type, and the quantity of the type being consumed.  
4. When the project journal lines are complete, choose the **Post** action.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## To view project usage estimates and post updates

You can view project usage up to the completion of a project in one step. To do so, you use the **Project Calc. Remaining Usage** batch job for all the tasks up to and including the end of a project.  

This lets you track and compare your original estimates against actual results and make modifications or new entries as needed. For example, you may have estimated that a project required 10 hours, and to date, it has taken 15 hours. You can add the extra five hours to the existing journal line or create a new journal line to report these five hours as overtime, which is another work type. The appropriate cost and price are calculated, and you can then post to the journal.  

> [!NOTE]  
> Item entries create item ledger entries and reduce the inventory quantity. The **Post Inventory Cost to G/L** batch job transfers the cost from inventory to the general ledger. Resource entries create resource ledger entries.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Project Journals**, and then choose the related link.  
2. Select a relevant project journal, and then choose the **Calc. Remaining Usage** action.  
3. On the **Project Calc. Remaining Usage** page, enter the document number and posting date that is to be inserted in the journal, and then choose the **OK** button.  
4. Update the journal with any modifications that may be needed.  
5. Choose the **Post**.

## Create inventory and warehouse pick documents for a project

Use the **Create Inventory Pick** and **Create Warehouse Pick** actions on the **Project Card** page. To create or register a pick document, use the **Put-away/Pick Lines/Movement Lines** or **Registered Pick Lines** actions. Learn more at [Flows for Production, Assembly, and Projects](design-details-internal-warehouse-flows.md).

You can use the actions under the following conditions:

* The **Status** of the project is **Open**.
* The **Line Type** of the project planning line is **Budget** or **Both Budget and Billable**.
* The **Type** of the project planning line is **Item**.
* **Require Pick** is enabled for the related location.
* **Directed Pick and Put-away** is disabled.

> [!NOTE] 
> Although the setting is called **Require Pick**, you can still post consumption directly from the project journal line for the location. If your location is set up to require pick processing but not shipment processing, you use the **Inventory Pick** page to organize and print the picking information. You also use the page to enter and post the result of the pick, which in turn posts the consumption of the items. 
> 
> If your location is set up to require both pick and shipment processing, meaning that you have chosen both the **Require Pick** and **Require Shipment** fields on the **Location Card** page, use the **Warehouse Pick** page to handle the pick. Warehouse picks are similar to inventory picks. The difference is that rather than posting the picking information you register the pick. This registration doesn't post consumption, it just makes the items available for posting. As a warehouse manager, you can use a pick worksheet to organize pick information before creating the individual warehouse pick instructions

## To review planning lines for a project ledger entry

After you have posted project journal lines, you can see the planning lines that are associated with the project journal entries that have been posted.

> [!NOTE]  
> This requires that the **Apply Usage Link** check box has been selected for the project. For more information, see [Set up projects](projects-how-setup-jobs.md).  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Project Journals**, and then choose the related link.  
2. Select a relevant project journal, and then choose the **Ledger Entries** action.  
3. On the **Project Ledger Entries** page, choose **Show Linked Project Planning Lines** action.

## Related information

[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
