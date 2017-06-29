---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Communicate Production Plans
When a supply plan is established through master planning and material requirements planning, it must be communicated to the respective [Purchasing](../Purchasing/purchasing.md) and [production](../Production/production.md) departments. This step consists mainly of initiating the planned supply orders, typically by auto\-creating them with a function in the planning tools.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Select the suggested supply orders that will be changed with the Carry Out batch job.|Accept Action Message|  
|Transform and communicate planning worksheet lines into executable supply orders to the different departments: Purchasing, Production, and Warehouse.|Carry Out Action Msg.\-Plan.|  
|Transform suggested planning lines in the **Order Planning** window into executable supply orders one item BOM level at a time.|Make Supply Orders|  
|Create purchase orders for subcontracted operations.|"Generating the Subcontract Purchase Order" in [Using the Subcontracting Worksheet](../OperationsPlanning/how-to-calculate-subcontracting-worksheets-and-create-subcontract-purchase-orders.md)|  
|Move a production order to its next stage.|Status|  
|Release planned or firm planned production orders for execution.|[How to: Release Production Orders by Status Change](../OperationsPlanning/how-to-release-production-orders-by-status-change.md)|  
|Release multiple production orders with a batch job.|[How to: Release Production Orders Automatically](../OperationsPlanning/how-to-release-production-orders-automatically.md)|  
|Print a list of the production orders that are ready to release.|Prod. Order \- List|  
  
## See Also  
 [Schedule Production Activities](../Production/schedule-production-activities.md)   
 [Execute Production](../Production/execute-production.md)