---
    title: About Calculating Standard Cost | Microsoft Docs
    description: A standard cost system determines inventory unit cost based on some reasonable historical or expected cost. Studies of past and estimated future cost data can then provide the basis for standard costs.
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
# About Calculating Standard Cost
Many manufacturing companies select a valuation base of standard cost. This also applies to companies that perform light manufacturing, such as assembly and kitting. A standard cost system determines inventory unit cost based on some reasonable historical or expected cost. Studies of past and estimated future cost data can then provide the basis for standard costs. These costs are frozen until a decision is made to change them. The actual cost to produce a product may differ from the estimated standard costs. For management control, the actual cost is compared to the standard cost for a specific item and differences, or *variances*, are identified and analyzed.  

Standard costs can be maintained for items that are replenished through purchase, assembly, and production. For each replenishment method, standard costs can consist of the following elements.  

|Replenishment System|Standard Cost Elements|  
|--------------------------|----------------------------|  
|**Purchase**|Direct material cost and overhead material cost if it is required.|  
|**Assembly**|Direct material cost, direct or fixed labor cost, and overhead cost.|  
|**Prod. Order**|Direct material cost, labor cost, subcontractor cost, and overhead cost.|  

## Setting Up Standard Costs  
Because the standard cost of a produced or assembled item can consist of multiple cost elements, including material, capacity (labor) and direct and overhead subcontractor costs, standard costs must be established for each of these elements.  

The accounting task for an item-processing company using standard costing is to:  

-   Estimate a standard cost of the finished item and set it up on the item card.  
-   Record and allocate the actual cost of the key cost elements and to account for variances.  

To determine the direct cost of a finished item, all component costs must be totaled. An assembled or produced item can include subassemblies, which also consist of multiple components.  

The following key cost elements make up the total direct cost of a finished processed item:  

-   Material costs.  
-   Capacity cost.  
-   Subcontracting costs for produced items only.  

### Material Costs  
 Material costs are costs that are associated with subassemblies and purchased raw material. Material unit cost can consist of direct and indirect cost elements.  

-   Direct material cost represents an invoiced amount for purchased raw materials or the processing cost of a subassembly.  
-   Indirect material cost, or *overhead*, can represent elements such as inventory carrying costs for the finished item after it is produced.  

The setup of the material cost for purchased items that affect direct and indirect cost depends on the costing method that you have selected for the specified item. You set up cost information for either costing method on the item card. For more information, see [Register New Items](inventory-how-register-new-items.md).

The cost of scrap (production only) is an additional factor to consider when you calculate the total material cost. When a certain amount of raw material is scrapped when you assemble or produce an item, it generally causes an increase in the quantity of components that are required to produce this item. This increases the material cost of the components that are consumed when producing a parent item. You set up scrap cost for materials on either the production BOM or routing.  

The material cost of a produced item can be represented in two ways that correspond to the following cost calculation bases.  

|Cost Calculation Basis|Material Cost Calculation|  
|----------------------------|-------------------------------|  
|Single level|Produced item is equal to the total cost of all purchased or subassembled items on that item's production BOM.|  
|Rolled-up level or multilevel|Produced item is the sum of the material cost for all subassemblies on that item's BOM and the cost of all purchased items on that item's production BOM.|  

### Capacity Costs  
Capacity costs are the costs that are associated with internal labor and machine costs. You must set up these costs for each resource (in assembly management) and work or machine center on the routing (in production). As with materials, you can identify both direct and indirect elements of capacity cost. For example, the direct cost for a work center may be the established shop rate to perform a specific function. The indirect cost for a work center may represent some general factory expenses, such as lighting, heating, and so on. As with material costs, you can express capacity overhead as an indirect cost percentage or a fixed overhead rate.  

The setup of the capacity costs of assembled items consists of the following elements:  

-   Direct and indirect unit cost of the resource.  
-   Fixed or direct resource usage type.  

The setup of the capacity costs of produced items consists of the following elements:  

-   Direct and indirect unit cost of the machine or work center.  
-   Time and lot size setup.  

To calculate standard capacity cost, you have to establish the standard time rates that are required to perform operations on machine and work centers. The total time to complete an operation typically consists of setup, run time, and wait and move time.  

You set up the rates for each time type for each machine or work center on an individual routing.  

> [!NOTE]  
>  While run time rates apply for each item unit that is produced, the setup time rates apply for each lot. Therefore, you must prorate the routing setup time for each operation over the lot size. You specify the lot size in the corresponding field on the **Ordering** FastTab of the item card.  

To specify setup time on the routing for planning but not include this expense in the standard cost calculation, clear the **Cost Incl. Setup** field on the **Manufacturing Setup** page.  

On a single-level basis, this is the labor cost that is required to produce the finished production item and is specified on the production item's routing. On a multi-level basis, this is the capacity cost that is specified for each individually produced item that is included in the parent item's BOM.  

### Subcontractor Costs  
Subcontractor costs are the costs that are associated with services that are provided by a company's outside vendors or subcontractors. Similar to material and capacity, subcontractor costs can consist of both direct and overhead amounts. Direct subcontractor cost represents the actual charge for each unit of services that is provided. For example, overhead subcontractor cost can represent freight and handling costs that are incurred by the company with a subcontracted order.  

Because subcontracting is an outsourced capacity, you set up the cost of both direct and indirect subcontracting services on the work center card that represents the subcontracting operation.  

## Updating Standard Costs  
To update or calculate the standard cost of assembly items, use the function from the item card.  

The process of updating or calculating standard costs typically consists of the following tasks:  

1.  Updating costs at the component and capacity levels. For more information, see the **Suggest Item Standard Cost** and **Suggest Capacity Standard Cost** batch jobs.  
2.  Consolidating and rolling up the component and capacity costs to calculate the total assembly or manufacturing cost of the items. For more information, see For more information, see [To calculate the standard cost of an assembly item](inventory-how-work-boms.md#to-calculate-the-standard-cost-of-an-assembly-item).  
3.  Implementing the standard costs that are entered when you run the previous batch jobs. The standard costs do not take effect until they are implemented. For more information, see the **Implement Standard Cost Changes** batch job.  
4.  Implementing the changes to update the **Unit Cost** field on the item card and perform inventory revaluation. For more information, see [Revalue Inventory](inventory-how-revalue-inventory.md).

## See Also  
 [Design Details: Costing Methods](design-details-costing-methods.md)   
 [Work with Bills of Material](inventory-how-work-BOMs.md)   
 [Update Standard Costs](finance-how-to-update-standard-costs.md)   
 [Design Details: Inventory Costing](design-details-inventory-costing.md)
