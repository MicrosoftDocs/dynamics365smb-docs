---
title: Walkthrough of Basic Jobs
description: This article guides you through several core processes in project management.
author: andreipanko
ms.author: andreipa
ms.topic: how-to
ms.date: 05/31/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Walkthrough of Basic Jobs

This walkthrough demonstrates several core processes:

- Add project tasks to projects
- Record expenses for time and material to a project
- Invoice a project

## Adding a project task

### Scenario  

Simon, the project manager, wants to be record time spent teaching the customer how to use the espresso machine product. Simon wants to use a separate task in the job for installing a commercial machine on-site.

### Steps

1. Create the Project Task.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Projects**, and then choose the related link.  
    2. Select the Job *J00010*.
	3. In the **Tasks** area, choose the **New Line** action, and then enter the following values:
 
    |Project Task No.|Description|Project Task Type|
    |------------|-----------|-------------|  
    |220|Customer Training|Posting|

2. Indent the Project Tasks.
   1. In the Tasks area, locate the **Indent Project Tasks** action.
   2. Confirm your wish to indent tasks by selecting **Yes**.

### Results

 - Now time and expenses can be recorded to the new project task

## Record time and material expenses to a project

### Scenario  

Edgin, the technician installing the machine, needs to record the time and the materials used during installation to the job for billing. Edgin already added the travel and materials, and now needs to add the time for teaching staff how to use the machine.

### Steps

1. Create the extra project journal lines.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Project Journals**, and then choose the related link.  
    2. Select the batch *CONTOSO*. You see several lines of Resource and Item types, reflecting the time (for the technician and the vehicle) and materials (the machine and supplies) used.
	3. Create a new line, and then enter the following values:
 
    |Project No.|Project Task No.|Type|No.|Description|Quantity|
    |-------|------------|----|---|-----------|--------|  
    |J00010|220|Resource|EDGIN|Customer training|1|

2. Post the time and expense.
   1. Choose the **Post** action.
   2. Confirm your wish to post the lines by selecting **Yes**.

### Results

- Project Ledger Entries and Resource Ledger Entries of type *Usage* are created.
- Item Ledger Entries are created to negatively adjust the inventory.
- On the Project Card, the Costs and Prices in the Tasks area reflect the new balances waiting to be invoiced.
- On the Project Card, the Project Details FactBox reflects the totals of the prices.

## Creating a sales invoice for a project

### Scenario  

Simon needs to create and post an invoice to be sent to the customer with the time and expenses from the project.

### Steps

1. Create the sales invoice.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Projects**, and then choose the related link.  
    2. In the list of Jobs, choose the **Create Project Sales Invoice** action.
    3. Set the **Project No.** filter to *J00010*.
    4. Choose **OK** to generate the sales invoice. You receive a confirmation of how many invoices are generated.

2. Post the time and expense invoice.

   1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.  
   2. Select the last invoice to open it for review.
   3. Choose the **Post** action.

### Results

- Project Ledger Entries and Resource Ledger Entries of type *Sales* are created.
- On the Project Card, the Costs and Prices in the Tasks area reflect the new invoiced balances.
- On the Project Card, the Project Details FactBox reflects the totals of the prices in the Invoiced Price section.
