---
title: How to restrict and allow usage of a record
description: To restrict a record from being used, you can incorporate two workflow responses in a workflow that controls the usage of the record.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 04/26/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Restrict and allow usage of a record

If you want to restrict a record from being used in certain activities, for example, until the record has been approved, you can add two workflow responses in the workflow that controls the use of the record. One workflow response restricts usage of the record as defined by the workflow event and conditions. The other workflow response allows the use of the record as defined by the workflow event and conditions. Two responses exist in the default version of [!INCLUDE[prod_short](includes/prod_short.md)] for this purpose: **Add record restriction** and **Remove record restriction**.

> [!NOTE]  
> The default version of [!INCLUDE[prod_short](includes/prod_short.md)] offers support for restricting a record from being posted, from being exported as a payment, and from being printed as a check. To support other restrictions, a Microsoft partner must customize the application code.  

> [!NOTE]  
> The workflow functionality to restrict and allow records from being used is not related to the functionality to block item, customer, and vendor records from being posted.

The following procedure describes how to restrict purchase orders from being posted until they've been approved. The new workflow is based on the *Purchase Invoice Approval Workflow* template.  

## Create a workflow step that restricts posting of unapproved purchase orders

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Workflows**, then choose the related link.  
2. On the **Workflows** page, choose the **New Workflow from Template** action. Learn more at [Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md).
3. On the **Workflow Templates** page, choose the *Purchase Invoice Approval Workflow* template.  

   Note that the first two workflow steps are about restricting and then allowing usage of purchase invoices. Change the event condition on the first step of the new workflow to specify that it applies to purchase orders.  
4. On the **Workflow Steps** FastTab, choose the **On Condition** field for the first step, then, for the **Document Type** filter, select **Order**.  
5. Proceed to edit, delete, or add other workflow steps to reflect a business process that begins by restricting unapproved purchase orders from being posted.  

## Related information

[Use Approval Workflows](across-use-workflows.md)  
[Create Approval Workflows](across-how-to-create-workflows.md)  
[Workflow](across-workflow.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
