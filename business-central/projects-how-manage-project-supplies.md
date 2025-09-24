---
title: Manage project supplies
description: Describes the different ways to manage the supply and purchase of material and services for projects.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: project management, material, purchase
ms.search.form: 98, 1020 
ms.date: 01/27/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Manage project supplies

You should manage project supplies of items, services, and expenses as an integral part of all projects. You can use inventory quantities or make project-specific purchases through purchase orders or purchase invoices. For example, when service on a computer requires a new disk, you create a purchase invoice to buy a new disk and record the project that uses it.

If the purchase process doesn't require you to record the physical transaction separately, you can process a purchase on the **Project G/L Journal** page. For more information, see [To post a project-related expense](projects-how-manage-project-supplies.md#to-post-a-project-related-expense).

## Manual or semi-automated replenishment

If you already know which supplies you need to replenish for a project, you can create a purchase order. To learn more, go to [Manual or semi-automated replenishment](#manual-or-semi-automated-replenishment).

However, if you aren't sure what you're missing, you can use a semi-automated process where you create a purchase order directly from a project. [!INCLUDE [prod_short](includes/prod_short.md)] helps by listing all items and shows whether they're available or unavailable. You can adjust the quantities to replenish on the lines.  

The semi-automated process creates a purchase order for each vendor from which you purchase the items, including any quantity changes that you made on the **Create Purchase Orders** page. You can continue to process the purchase order or orders, for example, by editing or adding purchase order lines.

Later, you can review the purchase lines linked to the project either from the **Project Card** page or **Project Planning Lines** by choosing the **Purchase Lines** action. To learn more, go to [Use a semi-automated replenishment process for a project](#use-a-semi-automated-replenishment-process-for-a-project).

> [!NOTE]
> As in other cases that involve advanced inventory processes, such as reservation, warehousing, and assemble-to-order, the project's status must be **Open** and the **Apply Usage Link** toggle must be turned on.

### Use a semi-automated replenishment process for a project

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, and then choose the related link.
2. Open a project that you want to purchase items for.
3. Choose the **Create Purchase Orders** action.
4. The **Create Purchase Orders** page shows a line for each item on the project. Lines for both fully available quantities and unavailable quantities show by default. To show only unavailable quantities, choose the **Show Unavailable** action.
5. The **Quantity to Purchase** field contains the unavailable quantity. To purchase a different quantity, edit the value in the field.

   > [!NOTE]
   > You can also change the **Quantity to Purchase** field on unavailable lines, even though they represent fully available quantities.

6. You can also turn on the **Reserve** toggle if you want to reserve the quantity on the purchase line against a demand instead of filling out the **Project No.** and **Project Task NO.** fields on the purchase line. By default, the **Reserve** toggle is hidden on the page. You can personalize the page to add the toggle. To learn more, go to [Personalize your workspace](ui-personalization-user.md).
7. Select **OK**.

You can review the purchase lines linked to the project either from the **Project Card** page or **Project Planning Lines** by choosing the **Purchase Lines** action.

### Replenish a project manually

The following procedure shows how to use a purchase invoice to purchase products for a project. The same steps apply when using a purchase order.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Purchase Order**, and then choose the related link.  
2. Choose the **New** action and fill in the fields as necessary. For more information, see [Record Purchases](purchasing-how-record-purchases.md).
3. In the **Project No.** and **Project Task No.** fields, select the information of the project that you want to purchase items or services for. Use the personalization tools if a field isn't visible. To learn more, go to [Personalize Your Workspace](ui-personalization-user.md).

    The value that you select in the **Project Line Type** field defines whether a planning line is created when you post the usage of the item. If the field contains **Billable**, then project planning lines that are ready to be invoiced to the customer are created. To learn more, go to [Invoice Projects](projects-how-invoice-jobs.md).

### How posting purchases affects inventory and WIP

When you post a receipt, the inventory is received and immediately written-off by an item ledger entry of the type **Negative Adjustment**. To avoid affecting WIP calculation, the project ledger entries don't include purchase order lines that aren't of the type **G/L Account**.

Project ledger entries are created as follows:

* From a purchase order, when you choose the **Post** action and choose **Invoice**.
* From a purchase invoice, when you choose the **Get Receipt Lines** action on the **Lines** FastTab, and then the **Post** action.

### To view the value of purchases for a project

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, and then choose the related link.
2. Open a relevant project card.

    On the **Tasks** FastTab, the **Outstanding Orders** field shows the total outstanding amount, in local currency, of inventory items and services on purchase documents for the project task line.  

    The **Amt. Rec. Not Invoiced** field shows the value of items delivered on purchase documents but not invoiced.  
3. Choose either of the fields to open the **Purchase Lines** page where you can review information about the related purchase document lines, including which items or services are received.

## To post a project-related expense

If you incur extraordinary or one-time project expenses, you can use the **Project G/L Journal** page to post them directly to the relevant project account.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project G/L Journals**, and then choose the related link.  
2. Create a new line and enter information about the expense, including information in the **Project No.** and **Project Task No** fields.  
3. When the journal is complete, choose the **Post** action.

## Receive items for projects with warehouse receipts or put-aways

[!INCLUDE [prod_short](includes/prod_short.md)] offers advanced warehouse handling for purchase orders that are linked to projects. Save some time by using warehouse receipts or inventory put-aways to directly receive and register usage of items for projects.

Use the following methods to receive items:

- Post receipt and consumption from the order line.
- Post receipt and consumption from an inventory put-away document.
- Post receipt and consumption from a warehouse receipt document.

### To post receipt and consumption from an inventory put-away document

When your location is set up to require processing put-aways but not receipts, use an **Inventory Put-away** document to record and post put-away and receipt information for your purchase orders.

You can create an inventory put-away in three ways:

- Create the inventory put-away directly from the purchase order by choosing the **Create Inventory Put-away/Pick** action.
- Create inventory put-aways for several source documents at the same time by using the **Create Inventory Put-away/Pick/Movement** batch job.
- Create the put-away in two steps by first by releasing the purchase orders to make the items available to be put away. You can create the inventory put-away based on the source document on the **Inventory Put-away** page.

> [!NOTE]
> If bins are mandatory for the location, make sure that the **Bin Code** is filled in the purchase order lines.

### To post the inventory put-away

1. On the **Inventory Put-aways** page, open a previously created put-away document.
1. Enter the quantity that was put away in the **Qty. to Handle** field.
1. After you put away the items, choose the **Post** action.

The results of these steps are that you post the receipt of the source document lines that were put away. There are two item ledger entries for each line. One entry for receipt, and one to immediately write off the received quantity for the project. There are no project ledger entries until you post the invoice. If the location uses bins, posting also creates warehouse entries to post the bin quantity changes.

### To post receipt and consumption from a warehouse receipt document

You must get the lines from the released purchase order that the receipt is for. You can create warehouse receipts in one of two ways:

- In a push fashion, when work is done on an order-by-order basis. Choose the **Create Warehouse Receipt** action on the **Purchase Order** page to create warehouse receipt for a source document.
- In a pull fashion, where you use the **Release** action on the **Purchase Order** page to release the document to the warehouse. A warehouse employee creates a warehouse receipt for one or more released source documents.

> [!NOTE]
> If you use bins, the default bin is suggested. You can either accept the default bin or specify the bin to put the items in.

### To post the warehouse receipt

1. On the **Warehouse Receipts** page, open the warehouse receipt.
1. The **Qty. to Receive** field contains the quantity outstanding for each line, but you can change the quantity as needed.
1. After you received the items, choose the **Post** action.

The results of these steps are that you post the receipt of the source document lines. There are two item ledger entries for each receipt line. One entry for the receipt, and one to immediately write off the received quantity for the project.

There are no project ledger entries until you post the invoice.

If the location uses bins, posting also creates warehouse entries to post the bin quantity changes.

> [!NOTE]
> Warehouse put-away documents aren't created, even if your warehouse processes require both receipt and warehouse put-away.

### Good to know

- Return orders aren't supported for locations with directed put-away and pick. You need to undo consumption via a project journal, and then create return order for items in inventory.
- If purchase documents were created before the update, you can post them directly. If you want to use warehouse handling, reopen and release the purchase orders again.
- You can't edit the **No.**, **Variant Code**, **Project No.**, and **Project Task No.** fields on purchase lines if warehouse receipts or inventory put-aways exist.

## Related information

[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
