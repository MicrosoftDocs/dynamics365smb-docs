---
title: Block or unblock lots
description: Learn how to block and unblock inventory lots using workflows and grade-specific controls to ensure quality compliance.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Block or unblock lots

This article explains how to automatically block and unblock inventory lots (serial numbers and packages) using workflows and result-specific controls. 

There are two main approaches for lot blocking:

- **Workflow-Based Blocking**: Block lots,serial numbers and pacakges using workflows.
- **Result-Based Blocking**: Document-specific blocking based on quality inspection results.

Both approaches help ensure that noncompliant inventory isn't used inappropriately, while allowing flexible quality control processes.

## Workflow-based lot blocking

Workflow-based blocking creates or modifies **Lot No. Information Card** pages to completely block lots for all transactions (except warehouse operations when configured). You access **Lot No. Information Card** pages from the **Lot No. Information List** page.
Similar for **Serial No. Information Card** and **Package No. Informatuion Card**.

### Set up a block-on-fail workflow

The following procedure describes the key settings for a workflow that blocks lots when quality inspections fail.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Workflows**, and then choose the related link.
1. Create a new workflow. For example, name it "Block Lot Example."
1. Configure a workflow step, as follows:

   1. In the **When Event** field, choose **A Quality Inspection is finished**.
   1. In the **On Condition** field, add a filter for the **Result Code** field, and then set **FAIL** as the filter value.
   1. In the **Then Response** field, choose **Block Lot in the Inspection**. This setting creates a lot information card with the status **Blocked**.

### Set up block-on-creation, and unblock on pass workflows

The following procedures describe the key settings for workflows that block lots immediately when inspections are created, and unblock them when inspections pass.

#### Block on inspection creation

1. Create a new workflow. For example, name it "Block Lot on Creation."
1. In the **When Event** field, choose **A Quality Inspection is Created**.
1. In the **Then Response** field, choose **Block lot in the inspection**.

   The result is that all lots are blocked immediately when inspections are created.

#### Unblock on pass

1. Create a new workflow. For example, name it "Unblock on Pass."  
1. In the **When Event** field, choose **A Quality Inspection is Finished**.
1. In the **On Condition** field, add a filter for the **Result Code** field, and then set **Pass** as the filter value.
1. In the **Then Response** field, choose **Unblock Lot in the Inspection**.

## Result-based document blocking

Result-based blocking provides granular, document-specific controls based on the current grade of quality inspection. Unlike complete lot blocking, this approach lets you block specific transaction types while permitting others, based on the inspection result.

The following list describes how [!INCLUDE [prod_short](includes/prod_short.md)] evaluates results:

- Multiple inspections for the same lot might have different results. The **Quality inspection selection criteria** field on the **Quality Management Setup** page specifies which inspections to consider when evaluating whether to block a document-specific transaction.
- Result priorities determine which controls take precedence. Higher priority results override lower priority results.

### Examples of result configurations

The following table shows a sample configuration for three inspection results. The **INPROGRESS** result restricts most transactions while inspections are in progress — you can store and move items for inspections, but not use them in business transactions. The **FAIL** result requires quarantine when a quality inspection fails, blocking all use and allowing only quarantine and disposal activities. The **PASS** result allows normal business operations when a quality inspection passes, enabling all transactions for items with confirmed quality.

| Result | Priority | Allow Sales | Allow Transfer | Allow Consumption | Allow Pick | Allow Put-away | Allow Movement | 
|---|---|---|---|---|---|---|---|
|**INPROGRESS**| 0 | **No** <br> (can't sell unconfirmed quality) | **No** <br>  prevent distribution before inspection is complete | **No** <br> can't use in production |  **No** <br> prevent picking for shipments | **Yes** <br> allow warehouse storage| **Yes** <br> allow movement to inspection areas| 
|**FAIL**| 1 |  **No** <br> (can't sell nonconforming items) |  **No** <br> prevent distribution of failed items | **No** <br> can't use defective materials |  **No** <br> prevent accidental picking | **Yes** <br> allow quarantine storage | **Yes** <br> allow movement for disposal| 
|**PASS**| 2 | **Yes** <br> (approved for customer shipment) | **Yes** <br> approved for distribution| **Yes** <br> approved for production use | **Yes** <br> approved for warehouse operations | **Yes** <br> normal warehouse operations | **Yes** <br> normal warehouse operations| 

To learn more about quality inspection results, go to [Configure quality inspection results](qms-configuring-grades.md).


## Related information

[Purchase Receipt Inspections without Warehouse Handling](qms-purchase-receipt-testing-simple.md)  
[Purchase Receipt Inspections with Warehouse Handling](qms-purchase-receipt-testing-warehouse.md)  
[Configuring Workflows](qms-quality-workflows.md)  
[Processing Non-Compliant Items](qms-non-compliant-processing.md)  
[Quality Management Overview](qms-overview.md)
