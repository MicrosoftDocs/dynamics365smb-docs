---
title: Manage project supplies
description: Describes the different ways to manage the supply and purchase of material and services for projects.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: project management, material, purchase
ms.search.form: 98, 1020 
ms.date: 08/20/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Manage project supplies

You should manage project supplies of items, services, and expenses as an integral and critical aspect of all projects. You can use inventory quantities or make project-specific purchases through purchase orders or purchase invoices. For example, a service project on a computer requires a new disk. You create a purchase invoice to buy a new disk and record the project that uses it.

If the purchase process doesn't require you to record the physical transaction separately, you can process a purchase on the **Project G/L Journal** page. For more information, see [To post a project-related expense](projects-how-manage-project-supplies.md#to-post-a-project-related-expense).

## Manual or semi-automated replenishment

If you already know which supplies you need to replenish for a project, you can create a purchase order. To learn more, go to [To manually purchase items or services for a project](#manually-purchase-items-or-services-for-a-project).

However, if you aren't sure what you're missing, you can use a semi-automated process where you create a purchase order directly from a project. [!INCLUDE [prod_short](includes/prod_short.md)] helps by listing all items and shows whether they're available or unavailable. You can adjust the quantities to replenish on the lines.  

The semi-automated process creates a purchase order for each vendor from which you purchase the items, including any quantity changes that you made on the **Create Purchase Orders** page. You can continue to process the purchase order or orders, for example, by editing or adding purchase order lines. 

Later, you can review the purchase lines linked to the project either from the **Project Card** page or **Project Planning Lines** by choosing the **Purchase Lines** action. To learn more, go to [Use a semi-automated replenishment process for a project](#use-a-semi-automated-replenishment-process-for-a-project).

> [!NOTE]
> As in other cases that involve advanced inventory processes, such as reservation, warehousing, and assemble-to-order, the project's status must be **Open** and the **Apply Usage Link** toggle must be turned on.

### Use a semi-automated replenishment process for a project

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.
2. Open a project that you want to purchase items for.
3. Choose the **Create Purchase Orders** action.
4. The **Create Purchase Orders** page shows a line for each item on the project. Lines for both fully available quantities and unavailable quantities show by default. To show only unavailable quantities, choose the **Show Unavailable** action.
5. The **Quantity to Purchase** field contains the unavailable quantity. To purchase a different quantity, edit the value in the field. 

   > [!Note]
   > You can also change the **Quantity to Purchase** field on unavailable lines, even though they represent fully available quantities.

6. You can also turn on the **Reserve** toggle if you want to reserve the quantity on the purchase line against a demand ninstead of filling out the **Project No.** and **Project Task NO.** fields on the purchase line. By default, the **Reserve** toggle is hidden on the page. You can personalize the page to add the toggle. To learn more, go to [Personalize your workspace](ui-personalization-user.md).
7. Select **OK**.

You can review the purchase lines linked to the project either from the **Project Card** page or **Project Planning Lines** by choosing the **Purchase Lines** action.

### Replenish a project manually

The following procedure shows how to use a purchase invoice to purchase products for a project. The same steps apply when using a purchase order.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.  
2. Choose the **New** action and fill in the fields as necessary. For more information, see [Record Purchases](purchasing-how-record-purchases.md).
3. In the **Project No.** and **Project Task No.** fields, select the information of the project that you want to purchase items or services for. Use the personalization tools if a field isn't visible. To learn more, go to [Personalize Your Workspace](ui-personalization-user.md).

    The value that you select in the **Project Line Type** field defines whether a planning line is created when you post the usage of the item. If the field contains **Billable**, then project planning lines that are ready to be invoiced to the customer are created. To learn more, go to [Invoice Projects](projects-how-invoice-jobs.md).
4. Choose the **Post** action.

## To view the value of purchases for a project

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Projects**, and then choose the related link.
2. Open a relevant project card.

    On the **Tasks** FastTab, the **Outstanding Orders** field shows the total outstanding amount, in local currency, of inventory items and services on purchase documents for the project task line.  

    The **Amt. Rec. Not Invoiced** field shows the value of items delivered on purchase documents, but not yet invoiced.  
3. Choose either of the fields to open the **Purchase Lines** page where you can review information about the related purchase document lines, including which items or services are received.

## To post a project-related expense

If you incur extraordinary or one-time project expenses, you can use the **Project G/L Journal** page to post them directly to the relevant project account.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Project G/L Journals**, and then choose the related link.  
2. Create a new line and enter information about the expense, including information in the **Project No.** and **Project Task No** fields.  
3. When the journal is complete, choose the **Post** action.

## See also

[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
