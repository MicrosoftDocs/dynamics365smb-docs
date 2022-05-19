---
title: Troubleshoot Your Automated Workflows
description: Learn how to troubleshoot the connection between Business Central and Power Automate when you build an automated workflow.

ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/12/2022
ms.author: edupont
author: jswymer
---

# Troubleshoot Your [!INCLUDE[prod_short](includes/prod_short.md)] Automated Workflows

When you connect [!INCLUDE [prod_short](includes/prod_short.md)] with Power Automate to create automated workflows, you might run into error messages. This article provides suggested solutions to frequently recurring problems.

## Flow doesn't run on all records created or changed

### Problem

If an event creates or changes many records, the flow doesn't run on some or all records.

### Possible cause

Currently, there's a limit on how many records that a flow can process. If more than 100 records are created or changed within 30 seconds, the flow won't be triggered.

> [!NOTE]
> For developers, the flow triggering is done via webhook notifications, and this limitation is due to the way the Business Central connector handles `collection` notifications. For more information, see [Working with Webhooks in Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/api-reference/v2.0/dynamics-subscriptions#notes-for-power-automate-flows) in the Developer and Admin help.

## "Entity set not found” error

### Problem

When you create a new Power Automate flow using a [!INCLUDE[prod_short](includes/prod_short.md)] approval trigger, such as *When a purchase document approval is requested*, you might get an error message similar to this one:

`Entity set not found: \<name\>`

The placeholder, `\<name\>`, is the service name of the missing web service, such as *workflowWebhookSubscriptions* or *workflowPurchaseDocumentLines*.

### Possible cause

Using Power Automate for your approvals requires that certain page and codeunit objects are published as web services. By default, most of the required objects are published as web services for you. But in some cases, your environment may have been customized so that these objects are no longer published.

### Fix

Go to the **Web Services** page and make sure that the following objects are published as web services. There should be an entry in the list for each object, with the **Published** check box selected.  

|Object Type|Object ID|Object Name|Service Name|
|-----------|---------|-----------|------------|
|Codeunit|	1544	|WorkflowWebhookSubscription|WorkflowActionResponse|
|Page|	6408|	workflowCustomers|	workflowCustomers|
|Page	|6406	|workflowGenJournalBatches|	workflowGenJournalBatches|
|Page	|6407	|workflowGenJournalLines|workflowGenJournalLines|
|Page	|6409	|workflowItems|	workflowItems|
|Page	|6405	|Purchase Document Line Entity|workflowPurchaseDocumentLines|
|Page|	6404	|workflowPurchaseDocuments|	workflowPurchaseDocuments|
|Page|	6403	|Sales Document Line Entity	|workflowSalesDocumentLines|
|Page|	6402|	workflowSalesDocuments|	workflowSalesDocuments|
|Page|	6410	|workflowVendors|	workflowVendors|
|Page|	831	|workflowWebhookSubscriptions|	workflowWebhookSubscriptions|

> [!NOTE]
> The **Service Name** value must be exactly as shown in the table. Don't change or translate the service name.

For more information about publishing web services, see [Publish a Web Service](across-how-publish-web-service.md).

## See Also

[Use [!INCLUDE[prod_short](includes/prod_short.md)] in an Automated Workflow](across-how-use-financials-data-source-flow.md)  
[Workflow](across-workflow.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]