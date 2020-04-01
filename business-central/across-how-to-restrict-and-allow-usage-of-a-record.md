---
    title: How to Restrict and Allow Usage of a Record | Microsoft Docs
    description: If you want to restrict a record from being used in certain activities, for example, until the record has been approved, you can incorporate two workflow responses in a workflow that controls the usage of the record.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Restrict and Allow Usage of a Record
If you want to restrict a record from being used in certain activities, for example, until the record has been approved, you can incorporate two workflow responses in a workflow that controls the usage of the record. One workflow response will restrict usage of the record as defined by the workflow event and conditions. Another workflow response will allow usage of the record as defined by the workflow event and conditions. Two responses exist in the generic version of [!INCLUDE[d365fin](includes/d365fin_md.md)] for this purpose: **Restrict usage of a record.** and **Allow usage of a record.**.

> [!NOTE]  
>  The generic version of [!INCLUDE[d365fin](includes/d365fin_md.md)] offers support for restricting a record from being posted, from being exported as a payment, and from being printed as a check. To support other restrictions, a Microsoft partner must customize the application code.  

> [!NOTE]  
>  The workflow functionality to restrict and allow records from being used is not related to the functionality to block item, customer, and vendor records from being posted.

The following procedure describes how to restrict purchase orders from being posted until they have been approved. The new workflow will be based on the existing Purchase Invoice Approval Workflow workflow template.  

## To create a workflow step that restricts posting of unapproved purchase orders  
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then choose the related link.  
2. On the **Workflows** page, create a new workflow named Purchase Order Approval Workflow. For more information, see [Create Workflows](across-how-to-create-workflows.md).  
3. Choose the **Copy From Workflow Template** action.  
4. Choose the **Source Workflow Code** field, and then, on the **Workflow Templates** page, choose the Purchase Invoice Approval Workflow workflow template.  

     Notice that the first two workflow steps are about restricting and then allowing usage of purchase invoices. Proceed to change the event condition on the first step of the new workflow to specify that it applies to purchase orders.  
5. On the **Workflow Steps** FastTab, choose the **Event Conditions** field, and then, for the **Document Type** filter, select **Order**.  
6. Proceed to edit, delete, or add other workflow steps to fit a business process that begins by restricting unapproved purchase orders from being posted.  

## See Also  
[Create Workflows](across-how-to-create-workflows.md)   
[Workflow](across-workflow.md)   
