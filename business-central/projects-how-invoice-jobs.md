---
title: Create a project sales invoice to invoice a project
description: Describes how to invoice customers for project expenses as a project progresses and costs accumulate.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: project invoice
ms.search.form: 1002, 1007, 
ms.date: 03/03/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Invoice projects

During a project, costs from resource usage, materials, and project-related purchases can accumulate. As the project progresses, these transactions get posted to the project journal. It's important to record all costs in the project journal before you invoice the customer. You can invoice customers after the project is finished, or at certain intervals based on an invoicing schedule.

You can invoice:

* Multiple projects using a **Project Create Sales Invoice** task.
* Whole projects, projects within a project, or individual project planning lines using the relevant action in the project pages.
* Combine multiple project planning lines from different projects into a single sales invoice using **Get Project Planning Lines** action on the **Sales Invoice** page.

## To create multiple project sales invoices

You can create an invoice for a project or for one or more project tasks:

* When the work to invoice is complete.
* When you reach the date for invoicing set on an invoicing schedule.

The following procedure shows how to use a batch job to invoice multiple projects.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Project Create Sales Invoice**, and then choose the related link.  
2. Fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Set filters to specify the projects to invoice.
4. Choose the **OK** button to create the invoices.  

You can review and post created invoices on the **Sales Invoices** page.

> [!NOTE]
> Alternatively, invoice a customer by selecting the project, and then choosing the **Create Project Sales Invoice** action, or use the **Create Sales Invoice** action in the project tasks.

## To create and post project sales invoice from project planning lines

You can create an invoice from a project planning lines, and specify the quantity of the item, resource, or general ledger account.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, and then choose the related link.
2. Open a relevant project.
3. Select a project task for which the **Project Task Type** field contains **Posting**, and then choose the **Project Planning Lines** action.  
4. On a project planning line, in the **Qty. To Transfer to Invoice** field, enter the quantity of the item, resource, general ledger account type that you want to invoice.  
5. Choose the **Create Sales Invoice** action.
6. On the **Project Transfer to Sales Invoice** page, enter the posting date and whether you want to create a new invoice or append this invoice to an existing one.
7. Choose the **OK** button.  
8. On the **Project Planning Lines** page, choose the **Sales Invoices/Credit Memos** action.

    The **Sales Invoice** page opens, showing the quantity that you transferred to the invoice.
9. Make any other changes, and then choose the **Post** action.

> [!NOTE]  
> The procedure is similar for creating, reviewing, and posting a project-related sales credit memo.

## Invoice one customer for multiple project tasks

You can simplify your invoicing process by sending one invoice to a customer for multiple projects. Add project planning lines from multiple projects to a sales invoice in one go. This process is similar to creating a sales invoice from a project planning line and entering a value in the **Append to Sales Invoice No.** field.

Here's an overview of the process.

1. Create a new sales invoice, and fill in the **Sell-to Customer No.** field. If needed, also fill in the **Bill-to Customer No.** and **Currency Code** fields.
2. On the **Lines** FastTab, choose the **Get Project Planning Lines** action. The **Get Project Planning Lines** page shows billable project planning lines from projects for the sell-to customer, bill-to customer, and invoicing currency where the quantity to invoice is more than zero. 
3. Choose the lines you want to add to the invoice, and then choose **OK**.

Repeat these steps if you want to add another set of project planning lines. You can also delete the invoice or its lines and start over.

> [!NOTE]
> There are a couple of limitations:
>
> * The **Get Project Planning Lines** action isn't available on sales orders or sales quotes.
> * You can't filter on the **Ship-to Code** or **Contact No.** fields.

## Issue a credit memo for a project

When a credit is due to a customer for something you invoiced for a project, you can create a credit memo to reimburse them. You can issue a credit memo for job planning lines of the types **Billable** or **Both Budget and Billable**. This credit memo ensures that job planning always reflects the correct planned invoice/credit memo lines for the project before you post sales invoices and credit memos. To learn more about sales credit memos, go to [Process sales returns or cancellations](sales-how-process-sales-returns-cancellations.md).

To issue a credit memo for a planning line, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Projects**, and then choose the related link.
1. Open the project you want to issue a credit memo for.
1. If the **Blocked** field is filled in, clear the field so that you can work with the project.
1. In the **Status** field, change the status from **Completed** to **Open**.
1. Choose the **Project Planning Lines** action.
1. Create a new planning line, and enter the same information as the line you want to credit. However, in the **Quantity** field, enter the same quantity but as a negative value. For example, if the quantity you want to credit is 10, enter a quantity of -10.
1. Choose the **Create Sales Credit Memo** action.
1. On the **Project Transfer to Credit Memo** page, fill in the fields as necessary, and then choose **OK**.
1. To review and post the credit memo, on the **Project Planning Lines** page, choose the **Sales invoices/credit memos** action.
1. On the **Sales Credit Memo** page, review the details. If it looks good, post the memo. 

## Related information

[Managing Projects](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Sales](sales-manage-sales.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
