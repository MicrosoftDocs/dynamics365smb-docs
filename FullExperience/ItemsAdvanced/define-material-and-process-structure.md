---
title: "Define Material and Process Structure"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "assembly BOMs, structure"
  - "process structure, about"
  - "production BOMs, structures"
  - "materials, structure"
ms.assetid: fc998dd3-fb42-4759-a8ae-35537b52e0b4
caps.latest.revision: 4
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Define Material and Process Structure
When designing products that are assembled or produced within the company before sale, additional specifications are required to define which material goes into the product, and which production operations are required to make them.  
  
 For simple item processing, you use assembly bills of material \(BOMs\) to define the components and resources that go into creating the end item. For more advanced item processing, you use production BOMs and production routings, which are connected to the item card of the produced item.  
  
 A production BOM holds master data that describes the components and subassemblies used in the production of a parent item. After a production order is created for that parent item, its production BOM will determine the calculation of material requirements as represented in the **Prod. Order Components** window. This component list functions as the picking list for the inventory or shop floor workers that must provide materials for the production process.  
  
 A production routing holds master data that describes the process structure of a given produced item. After a production order is created for that item, its routing will determine the scheduling of production operation\(s\) as represented in the **Prod. Order Routing** window and as such functions as a job card to machine operators who perform the work.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Learn the difference between bills of material for simple item processing versus advanced processing.|[Assembly BOMs or Production BOMs](../DesignAndEngineering/assembly-boms-or-production-boms.md)|  
|Organize assembly components, subassemblies, or resources under a parent item.|[How to: Create Assembly BOMs](../DesignAndEngineering/how-to-create-assembly-boms.md)|  
|Organize production components or subassemblies under a parent item.|[How to: Create Production BOMs](../DesignAndEngineering/how-to-create-production-boms.md)|  
|Ensure correct calculation of components needed for an item that is stocked in one unit of measure but produced in another.|[How to: Use the Manufacturing Batch Unit of Measure](../DesignAndEngineering/how-to-use-the-manufacturing-batch-unit-of-measure.md)|  
|Define the position of a component or subassembly in the product structure to ensure that the planning system prioritizes by BOM level.|[How to: Calculate Low\-Level Codes](../DesignAndEngineering/how-to-calculate-low-level-codes.md)|  
|Reflect a slightly different product structure that is still manufactured into the same end item.|[Creating New Versions of Production BOM](../DesignAndEngineering/how-to-create-new-versions-of-production-boms.md)s|  
|View a list of all production BOM versions and the numbers of items that are used per BOM.|[How to: Compare Material Quantities in All Production BOM Versions](../DesignAndEngineering/how-to-compare-material-quantities-in-all-production-bom-versions.md)|  
|Determine where a component or production BOM is used within existing product structures.|[How to: Find Where Production BOMs Are Used](../DesignAndEngineering/how-to-find-where-production-boms-are-used.md)|  
|Add, replace, or remove a component in multiple production BOMs in one action.|[\($ B\_99001043 Exchange Production BOM Item $\)](../Topic/\($%20B_99001043%20Exchange%20Production%20BOM%20Item%20$\).md)|  
|Remove a component in multiple production BOMs by a certain date.|[How to: Delete Expired Components](../DesignAndEngineering/how-to-delete-expired-components.md)|  
|Sequence production operations and assign them to established production resources.|[How to: Create Routings](../DesignAndEngineering/how-to-create-routings.md)|  
|Reflect a slightly different process structure, which outputs the same end item.|[How to: Create New Versions of Routings](../DesignAndEngineering/how-to-create-new-versions-of-routings.md)|  
|Connect components to specific operations in order to retain their relationship even though the production BOM or routing is modified.|[How to: Create Routing Links](../DesignAndEngineering/how-to-create-routing-links.md)|  
|Set up how to automatically post material consumption when releasing production or automatically post finished output when finishing production.|[\($ T\_27\_5417 Flushing Method $\)](../Topic/\($%20T_27_5417%20Flushing%20Method%20$\).md)|  
|Have the Production Journal window show the expected output quantity when first opened.|[\($ T\_99000765\_5500 Preset Output Quantity $\)](../Production/-$-t_99000765_5500-preset-output-quantity-$-.md)|  
|Define an operation as a standard task.|[How to: Create Standard Tasks](../DesignAndEngineering/how-to-create-standard-tasks.md)|  
|Specify codes that can be used to identify reasons that time or quantities were posted as down time.|[\($ N\_99000779 Stop Codes $\)](../Topic/\($%20N_99000779%20Stop%20Codes%20$\).md)|  
|Specify codes that can be used to identify reasons that time or quantities were posted as scrap.|[\($ N\_99000780 Scrap Codes $\)](../Topic/\($%20N_99000780%20Scrap%20Codes%20$\).md)|  
|Prototype a production order to calculate what is needed to produce a new product.|[\($ N\_99000912 Simulated Production Order $\)](../Topic/\($%20N_99000912%20Simulated%20Production%20Order%20$\).md)|  
  
## See Also  
 [Configure Production Processes](../Production/configure-production-processes.md)   
 [Execute Production](../Production/execute-production.md)