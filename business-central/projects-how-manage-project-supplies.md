---
title: Manage Job Supplies
description: Describes the different ways to to manage the supply and purchase of material and services for jobs.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, material, purchase
ms.search.form: 98, 1020 
ms.date: 06/22/2021
ms.author: bholtorf

---
# Manage Job Supplies
Managing project supplies of items, services, and expenses is an integral and critical aspect of the execution of all jobs. You can use inventory quantities or make job-specific purchases using purchase orders or purchase invoices. For example, a service job on a computer requires a new disk. You create a purchase invoice to buy a new disk and record the job that it will be used on.

If the purchase process does not require that the physical transaction be recorded separately, then a purchase may be processed on the **Job G/L Journal** page. For more information, see [To post a job-related expense](projects-how-manage-project-supplies.md#to-post-a-job-related-expense).

## To purchase items or services for a job
The following procedure shows how to use a purchase invoice to purchase products for a job. The same steps apply when using a purchase order.  

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Invoices**, and then choose the related link.  
2. Choose the **New** action and fill in the fields as necessary. For more information, see [Record Purchases](purchasing-how-record-purchases.md).
3. In the **Job No.** and **Job Task No.** fields, select the information of the job that you want to purchase items or services for. Use the personalization tools if a field is not visible. For more information, see [Personalize Your Workspace](ui-personalization-user.md).

    The value that you select in the **Job Line Type** field defines whether a planning line is created when you post the usage of the item. If the field contains **Billable**, then job planning lines that are ready to be invoiced to the customer are created. For more information, see [Invoice Jobs](projects-how-invoice-jobs.md).
4. Choose the **Post** action.

## To view the value of purchases for a job
1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Jobs**, and then choose the related link.
2. Open a relevant job card.

    On the **Tasks** FastTab, the **Outstanding Orders** field shows the total outstanding amount, in local currency, of inventory items and services on purchase documents for the job task line.  

    The **Amt. Rec. Not Invoiced** field shows the value of items delivered on purchase documents, but not yet invoiced.  
3. Choose either of the fields to open the **Purchase Lines** page where you can review information about the related purchase document lines, including which items or services have been received.

## To post a job-related expense
If you incur extraordinary or one-time job expenses, you can use the **Job G/L Journal** page to post them directly to the relevant job account.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Job G/L Journals**, and then choose the related link.  
2. Create a new line and enter information about the expense, including information in the **Job No.** and **Job Task No** fields.  
3. When the journal is complete, choose the **Post** action.

## See Also
[Project Management](projects-manage-projects.md)  
[Finance](finance.md)  
[Purchasing](purchasing-manage-purchasing.md)         
[Sales](sales-manage-sales.md)      
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
