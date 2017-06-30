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
# Issue Materials
The first physical activity in a production process is to prepare the materials that are to be processed in the production operations. Apart from the warehouse activities involved in bringing components to the machine center in question, the issue of materials mainly concerns the way component items are posted to the database as consumed. Consumption posting can be done manually, by filling and posting journal lines after production operations. Or, it can be done automatically depending on the setup of flushing method. Components can be either forward flushed when the production order is released or it can be backward flushed along with output posting when the production order changes to finished.  
  
 As an alternative to the batch journal for consumption posting for multiple production orders, you can use the **Production Journal** window to post consumption and\/or output for one production order line.  
  
 The following table describes a sequence of tasks, with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Learn about the effects of the different setup options for automatic posting of material consumption.|Flushing Method|  
|Ensure that the need for components are aligned with a specific operation - in forward as well as backward flushing.|[How to: Create Routing Links](../how-to-create-routing-links.md)|  
|Check if components are available.|Prod. Order - Shortage List|  
|Request that warehouse workers pick required components by creating the inventory or warehouse pick document.|[How to: Pick for Production in Basic Warehousing](../how-to-pick-for-production-in-basic-warehousing.md)|  
|View or print a report which shows a detailed list of items that must be picked for a specific production order.|Prod. Order - Picking List|  
|Specify the warehouse bin where production consumption is picked - in warehouses without directed put-away and pick.|[How to: Assign Bin Codes on Journal Lines](../how-to-assign-bin-codes-on-journal-lines.md)|  
|Record and post consumption, along with output, for a single released production order line.|[How to: Register Consumption and Output](../how-to-register-consumption-and-output.md)|  
|Batch post material consumption for one or more released production orders.|Consumption Journal|  
  
## See Also  
 [Pick Items](../pick-items.md)   
 [Perform Material Requirements Planning](../perform-material-requirements-planning.md)   
 [Design Products](../design-products.md)   
 [Working with Product Name](../working-with-$-p_1-product-name-$-.md)