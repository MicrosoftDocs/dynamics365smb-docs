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
# Define Material and Process Structure
When designing products that are assembled or produced within the company before sale, additional specifications are required to define which material goes into the product, and which production operations are required to make them.  
  
 For simple item processing, you use assembly bills of material \(BOMs\) to define the components and resources that go into creating the end item. For more advanced item processing, you use production BOMs and production routings, which are connected to the item card of the produced item.  
  
 A production BOM holds master data that describes the components and subassemblies used in the production of a parent item. After a production order is created for that parent item, its production BOM will determine the calculation of material requirements as represented in the **Prod. Order Components** window. This component list functions as the picking list for the inventory or shop floor workers that must provide materials for the production process.  
  
 A production routing holds master data that describes the process structure of a given produced item. After a production order is created for that item, its routing will determine the scheduling of production operation\(s\) as represented in the **Prod. Order Routing** window and as such functions as a job card to machine operators who perform the work.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Learn the difference between bills of material for simple item processing versus advanced processing.|[Assembly BOMs or Production BOMs](../FullExperience/assembly-boms-or-production-boms.md)|  
|Organize assembly components, subassemblies, or resources under a parent item.|[How to: Create Assembly BOMs](../FullExperience/how-to-create-assembly-boms.md)|  
|Organize production components or subassemblies under a parent item.|[How to: Create Production BOMs](../FullExperience/how-to-create-production-boms.md)|  
|Ensure correct calculation of components needed for an item that is stocked in one unit of measure but produced in another.|[How to: Use the Manufacturing Batch Unit of Measure](../FullExperience/how-to-use-the-manufacturing-batch-unit-of-measure.md)|  
|Define the position of a component or subassembly in the product structure to ensure that the planning system prioritizes by BOM level.|[How to: Calculate Low-Level Codes](../FullExperience/how-to-calculate-low-level-codes.md)|  
|Reflect a slightly different product structure that is still manufactured into the same end item.|[Creating New Versions of Production BOM](../FullExperience/how-to-create-new-versions-of-production-boms.md)s|  
|View a list of all production BOM versions and the numbers of items that are used per BOM.|[How to: Compare Material Quantities in All Production BOM Versions](../FullExperience/how-to-compare-material-quantities-in-all-production-bom-versions.md)|  
|Determine where a component or production BOM is used within existing product structures.|[How to: Find Where Production BOMs Are Used](../FullExperience/how-to-find-where-production-boms-are-used.md)|  
|Add, replace, or remove a component in multiple production BOMs in one action.|Exchange Production BOM Item|  
|Remove a component in multiple production BOMs by a certain date.|[How to: Delete Expired Components](../FullExperience/how-to-delete-expired-components.md)|  
|Sequence production operations and assign them to established production resources.|[How to: Create Routings](../FullExperience/how-to-create-routings.md)|  
|Reflect a slightly different process structure, which outputs the same end item.|[How to: Create New Versions of Routings](../FullExperience/how-to-create-new-versions-of-routings.md)|  
|Connect components to specific operations in order to retain their relationship even though the production BOM or routing is modified.|[How to: Create Routing Links](../FullExperience/how-to-create-routing-links.md)|  
|Set up how to automatically post material consumption when releasing production or automatically post finished output when finishing production.|Flushing Method|  
|Have the Production Journal window show the expected output quantity when first opened.|Preset Output Quantity|  
|Define an operation as a standard task.|[How to: Create Standard Tasks](../FullExperience/how-to-create-standard-tasks.md)|  
|Specify codes that can be used to identify reasons that time or quantities were posted as down time.|Stop Codes|  
|Specify codes that can be used to identify reasons that time or quantities were posted as scrap.|Scrap Codes|  
|Prototype a production order to calculate what is needed to produce a new product.|Simulated Production Order|  
  
## See Also  
 [Configure Production Processes](../FullExperience/configure-production-processes.md)   
 [Execute Production](../FullExperience/execute-production.md)