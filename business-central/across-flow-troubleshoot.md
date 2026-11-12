---
title: Troubleshoot Business Central Power Automate Workflows
description: Learn how to troubleshoot the connection between Business Central and Power Automate when you build an automated workflow.
author: jswymer
ms.topic: troubleshooting
ai-usage: ai-assisted
ms.search.keywords: workflow, OData, Power App, SOAP, Entity set not found, workflowWebhookSubscriptions, Power Automate, 
ms.date: 11/12/2026
ms.author: jswymer
ms.reviewer: v-soumramani
ms.service: dynamics-365-business-central
---

# Troubleshoot Business Central Power Automate workflows

When you connect [!INCLUDE [prod_short](includes/prod_short.md)] with Power Automate to create automated workflows, you might run into error messages. This article provides suggested solutions to recurring problems.

## Flow doesn't run on all records created or changed

### Problem

If an event creates or changes many records, the flow doesn't run on some or all records.

### Possible cause

The Business Central connector for Power Automate can't process webhook `collection` notifications. In Business Central online, if more than 1,000 records are created or changed within 30 seconds, Business Central sends a collection notification instead of individual notifications, and the associated flow isn't triggered. For Business Central on-premises, the thresholds depend on the server configuration.

> [!NOTE]
> Learn more in [Working with webhooks in Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/api-reference/v2.0/dynamics-subscriptions#notes-for-power-automate-flows) in the developer and IT pro help.

## "The response from the Business Central service is too large" error

### Problem

When using an action that interacts with records (such as **Create record (V3)** and **Get record (V3)**), Power Automate might display an error similar to this one:

`The response from the Business Central service is too large`

### Possible cause

The Dynamics 365 Business Central connector for Power Automate requires records to be under 8 MB.

All the Business Central APIs provided by Microsoft return records under this limit, but APIs provided by partners might not. If you see an error "The response from the Business Central service is too large," reach out to the partner who created the API you're using.

## "Entity set not found" error

### Problem

When you create a new Power Automate flow using a [!INCLUDE[prod_short](includes/prod_short.md)] approval trigger, such as **When a purchase document approval is requested**, you might get an error message similar to this one:

`Entity set not found: <ServiceName>`

The placeholder, `<ServiceName>`, is the service name of the missing web service, such as `workflowWebhookSubscriptions` or `workflowPurchaseDocumentLines`.

### Possible cause

Using Power Automate for approvals requires certain page and codeunit objects to be published as web services. By default, most of the required objects are published as web services. But in some cases, your environment might have been customized so these objects are no longer published.

### Fix

Go to the **Web Services** page and make sure the following objects are published as web services. There should be an entry in the list for each object, with the **Published** check box selected.  

| Object Type | Object ID | Object Name | Service Name |
|--|--|--|--|
| Codeunit | 1544 | Workflow Webhook Subscription | WorkflowActionResponse |
| Page | 6408 | workflowCustomers | workflowCustomers |
| Page | 6406 | workflowGenJournalBatches | workflowGenJournalBatches |
| Page | 6407 | workflowGenJournalLines | workflowGenJournalLines |
| Page | 6409 | workflowItems | workflowItems |
| Page | 6405 | Purchase Document Line Entity | workflowPurchaseDocumentLines |
| Page | 6404 | workflowPurchaseDocuments | workflowPurchaseDocuments |
| Page | 6403 | Sales Document Line Entity | workflowSalesDocumentLines |
| Page | 6402 | workflowSalesDocuments | workflowSalesDocuments |
| Page | 6410 | workflowVendors | workflowVendors |
| Page | 831 | workflowWebhookSubscriptions | workflowWebhookSubscriptions |

> [!NOTE]
> The **Service Name** value must be exactly as shown in the table. Don't change or translate the service name.

Learn more in [Publish a web service](across-how-publish-web-service.md).

## Related information

[Use Power Automate Flows in [!INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-financials-data-source-flow.md)  
[Workflow](across-workflow.md)  
[Set Up Automated Workflows](/dynamics365/business-central/dev-itpro/powerplatform/automate-workflows)  
[Switch on Instant Flows](/dynamics365/business-central/dev-itpro/powerplatform/instant-flows)  
[Manage Power Automate Flows](/dynamics365/business-central/dev-itpro/powerplatform/manage-power-automate-flows)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
