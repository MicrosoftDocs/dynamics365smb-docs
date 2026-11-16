---
title: Walkthrough of Basic Project Management
description: Use Contoso Coffee demo data to add a project task, record training time in a project journal, and create and post a project sales invoice.
author: andreipanko
ms.author: andreipa
ms.topic: how-to
ms.date: 11/12/2026
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# Walkthrough of basic project management

This walkthrough demonstrates several core processes:

- Add project tasks to projects
- Record time spent on a project
- Invoice a project

## Prerequisites

On the **Contoso Demo Tool** page, generate all data for the **Job** module. This walkthrough uses the default module configuration. Learn more in [Introduction to Contoso Coffee demo data](../contoso-coffee-intro.md).

## Adding a project task

### Scenario  

Simon, the project manager, wants to record time spent teaching the customer how to use the espresso machine. Simon wants to use a separate task in the project for installing a commercial machine on-site.

### Steps

1. Create the project task.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Projects**, and then choose the related link.
    1. Open the project with the description **Installation of S-200 Semi-Automatic** and external document number **F-1**. Note its project number for the later steps.
    1. In the **Tasks** area, choose the **New Line** action, and then enter the following values:
 
    |Project Task No.|Description|Project Task Type|
    |------------|-----------|-------------|  
    |230|Customer Training|Posting|

1. Indent the project tasks.
   1. In the **Tasks** area, choose the **Indent Project Tasks** action.
   1. Confirm your wish to indent tasks by selecting **Yes**.

### Results

 - Now time and expenses can be recorded to the new project task

## Record time spent on a project

### Scenario  

Edgin, the technician installing the machine, needs to record one hour spent teaching staff how to use the machine. The default module configuration represents the technician with resource **RESOURCE3**.

### Steps

1. Create a project journal line.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Project Journals**, and then choose the related link.
    1. Select the batch **CONTOSO**. The demo data creates the batch, but doesn't fill it with project journal lines.
    1. Create a new line, set **Posting Date** to the work date, and then enter the following values:
 
    |Project No.|Project Task No.|Line Type|Type|No.|Description|Quantity|
    |-------|------------|---------|----|---|-----------|--------|
    |The project number you noted earlier|230|Billable|Resource|RESOURCE3|Customer training|1|

1. Post the time entry.
   1. Choose the **Post** action.
   1. Confirm your wish to post the lines by selecting **Yes**.

### Results

- Project Ledger Entries and Resource Ledger Entries of type *Usage* are created.
- On the Project Card, the Costs and Prices in the Tasks area reflect the new balances waiting to be invoiced.
- On the Project Card, the Project Details FactBox reflects the totals of the prices.

## Creating a sales invoice for a project

### Scenario  

Simon needs to create and post an invoice to be sent to the customer with the time and expenses from the project.

### Steps

1. Create the sales invoice.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Projects**, and then choose the related link.
    1. In the list of projects, choose the **Create Project Sales Invoice** action.
    1. Set the **Project No.** filter to the project number you noted earlier.
    1. Choose **OK** to generate the sales invoice. You receive a confirmation of how many invoices are generated.

1. Post the time and expense invoice.

   1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Sales Invoices**, and then choose the related link.
   1. Select the invoice created for the project to open it for review.
   1. Choose the **Post** action.

### Results

- Project Ledger Entries and Resource Ledger Entries of type *Sales* are created.
- On the Project Card, the Costs and Prices in the Tasks area reflect the new invoiced balances.
- On the Project Card, the Project Details FactBox reflects the totals of the prices in the Invoiced Price section.

## Related information

[Introduction to Contoso Coffee demo data for projects](contoso-coffee-jobs-intro.md)  
[Projects](../../projects-manage-projects.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
