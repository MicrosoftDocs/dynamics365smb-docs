---
title: About Calculating Standard Cost
description: A standard cost system determines inventory unit cost based on reasonable historical or expected cost.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 5841
ms.author: bholtorf
ms.date: 10/10/2023
---
# About Calculating Standard Cost

Many manufacturing companies select a valuation base of standard cost. This also applies to companies that perform light manufacturing, such as assembly and kitting. A standard cost system determines inventory unit cost based on some reasonable historical or expected cost. Studies of past and estimated future cost data can then provide the basis for standard costs. These costs are frozen until a decision is made to change them. The actual cost to produce a product can differ from the estimated standard costs. For management control, the actual cost is compared to the standard cost for a specific item and differences, or *variances*, are identified and analyzed.  

Standard costs can be maintained for items that are replenished through purchase, assembly, and production. For each replenishment method, standard costs can consist of the following elements.  

|Replenishment System|Standard Cost Elements|  
|--------------------------|----------------------------|  
|**Purchase**|Direct material cost and overhead material cost if it's required.|  
|**Assembly**|Direct material cost, direct or fixed labor cost, and overhead cost.|  
|**Prod. Order**|Direct material cost, labor cost, subcontractor cost, and overhead cost.|  

## Setting Up standard costs

Because the standard cost of a produced or assembled item can consist of multiple cost elements, including material, capacity (labor) and direct and overhead subcontractor costs, standard costs must be established for each of these elements.  

The accounting task for an item-processing company using standard costing is to:  

- Estimate a standard cost of the finished item and set it up on the item card.  
- Record and allocate the actual cost of the key cost elements and to account for variances.  

To determine the direct cost of a finished item, all component costs must be totaled. An assembled or produced item can include subassemblies, which also consist of multiple components.  

The following key cost elements make up the total direct cost of a finished processed item:  

- Material costs.  
- Capacity cost.  
- Subcontracting costs for produced items only.  

### Material costs

Material costs are costs that are associated with subassemblies and purchased raw material. Material unit cost can consist of direct and indirect cost elements.  

- Direct material cost represents an invoiced amount for purchased raw materials or the processing cost of a subassembly.  
- Indirect material cost, or *overhead*, can represent elements such as inventory carrying costs for the finished item after it's produced.  

The setup of the material cost for purchased items that affect direct and indirect cost depends on the costing method that you have selected for the specified item. You set up cost information for either costing method on the item card. For more information, see [Register New Items](inventory-how-register-new-items.md).

The cost of scrap (production only) is another factor to consider when you calculate the total material cost. When a certain amount of raw material is scrapped when you assemble or produce an item, it generally causes an increase in the quantity of components that are required to produce this item. This increases the material cost of the components that are consumed when producing a parent item. You set up scrap cost for materials on either the production BOM or routing.  

The material cost of a produced item can be represented in two ways that correspond to the following cost calculation bases.  

|Cost Calculation Basis|Material Cost Calculation|  
|----------------------------|-------------------------------|  
|Single level|Produced item is equal to the total cost of all purchased or subassembled items on that item's production BOM.|  
|Rolled-up level or multilevel|Produced item is the sum of the material cost for all subassemblies on that item's BOM and the cost of all purchased items on that item's production BOM.|  

### Capacity costs

Capacity costs are the costs that are associated with internal labor and machine costs. You must set up these costs for each resource (in assembly management) and work or machine center on the routing (in production). As with materials, you can identify both direct and indirect elements of capacity cost. For example, the direct cost for a work center can be the established shop rate to perform a specific function. The indirect cost for a work center can represent some general factory expenses, such as lighting, heating, and so on. As with material costs, you can express capacity overhead as an indirect cost percentage or a fixed overhead rate.  

The setup of the capacity costs of assembled items consists of the following elements:  

- Direct and indirect unit cost of the resource.  
- Fixed or direct resource usage type.  

The setup of the capacity costs of produced items consists of the following elements:  

- Direct and indirect unit cost of the machine or work center.  
- Time and lot size setup.  

To calculate standard capacity cost, you have to establish the standard time rates that are required to perform operations on machine and work centers. The total time to complete an operation typically consists of setup, run time, and wait and move time.  

You set up the rates for each time type for each machine or work center on an individual routing.  

> [!NOTE]  
>  While run time rates apply for each item unit that is produced, the setup time rates apply for each lot. Therefore, you must prorate the routing setup time for each operation over the lot size. You specify the lot size in the corresponding field on the **Replenishment** FastTab of the **Item Card** page.  

To specify setup time on the routing for planning but not include this expense in the standard cost calculation, clear the **Cost Incl. Setup** field on the **Manufacturing Setup** page.  

On a single-level basis, this is the labor cost that is required to produce the finished production item and is specified on the production item's routing. On a multi-level basis, this is the capacity cost that is specified for each individually produced item that is included in the parent item's BOM.  

### Subcontractor costs

Subcontractor costs are the costs that are associated with services that are provided by a company's outside vendors or subcontractors. Similar to material and capacity, subcontractor costs can consist of both direct and overhead amounts. Direct subcontractor cost represents the actual charge for each unit of services that is provided. For example, overhead subcontractor cost can represent freight and handling costs that the company incurs with a subcontracted order.  

Because subcontracting is an outsourced capacity, you set up the cost of both direct and indirect subcontracting services on the work center card that represents the subcontracting operation.  

## Updating standard costs

To update or calculate the standard cost of assembly items, use the function from the item card.  

The process of updating or calculating standard costs typically consists of the following tasks:  

1.  Updating costs at the component and capacity levels. For more information, see the **Suggest Item Standard Cost** and **Suggest Capacity Standard Cost** batch jobs.  
2.  Consolidating and rolling up the component and capacity costs to calculate the total assembly or manufacturing cost of the items. For more information, see For more information, see [To calculate the standard cost of an assembly item](assembly-how-work-assembly-boms.md#to-calculate-the-standard-cost-of-an-assembly-item).  
3.  Implementing the standard costs that are entered when you run the previous batch jobs. The standard costs don't take effect until they're implemented. Use the **Implement Standard Cost Changes** batch job, which updates the changes in the standard cost on items with the ones in the Standard Cost Worksheet table.  
4.  Implementing the changes to update the **Unit Cost** field on the item card and perform inventory revaluation. For more information, see [Revalue Inventory](inventory-how-revalue-inventory.md).

## Use batch jobs to update standard costs
The following sections describe the batch jobs that you can use to update standard costs.
### Suggest Item Standard Cost

 Creates suggestions for changing the costs and cost shares of standard costs on item cards. When the batch job has completed, you can see the result in the Standard Cost Worksheet window.

> [!NOTE]  
> This batch job is intended for purchased items only. If you want to update an item with a production BOM or assembly BOM, then you must first fill in the worksheet with all the components and then run the Roll Up Standard Cost batch job.

This batch job only creates suggestions. It doesn't implement the suggested changes. If you're satisfied with the suggestions and want to implement them, that is update them on the item cards and insert them in the Revaluation Journal, then select Implement Standard Cost Changes in the Standard Cost Worksheet window.
#### Options

**Standard Cost**: Enter the adjustment factor you want to use to update the standard cost. You can also select a rounding method for the new standard cost. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

**Indirect Cost %**: Enter the adjustment factor you want to use to update the indirect cost %. You can also select a rounding method for the new indirect cost %. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

**Overhead Rate**: Enter the adjustment factor you want to use to update the overhead rate. You can also select a rounding method for the new overhead rate. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

### Suggest Work/Mach Ctr Std Cost

Creates suggestions for changing the costs and cost shares of standard costs on work center, machine center, or resource cards. When the batch job has completed, you can see the result in the **Standard Cost Worksheet** window.

This batch job only creates suggestions. It doesn't implement the suggested changes. If you're satisfied with the suggestions and want to implement them, that is update them on the work/machine center and resource cards and insert them in the Revaluation Journal window, then select **Implement Standard Cost Changes** in the **Standard Cost Worksheet** window.

When you have run the batch job and want to see the impact on your production or assembly departments, then you run the **Roll Up Standard Cost** batch job to update standard costs on work centers, machine centers, assembly resources, production BOMs, and assembly BOMs.
#### Options
**Standard Cost**: Enter the adjustment factor you want to use to update the standard cost. You can also select a **rounding method** for the new standard cost. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

**Indirect Cost %**: Enter the adjustment factor you want to use to update the indirect cost %. You can also select a rounding method for the new indirect cost %. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

**Overhead Rate**: Enter the adjustment factor you want to use to update the overhead rate. You can also select a rounding method for the new overhead rate. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

### Post Inventory Cost to G/L

 Records the quantity and value changes to the inventory in the item ledger entries and the value entries when you post inventory transactions, such as sales shipments or purchase receipts.

Unless you have selected the **Automatic Cost Posting** check box in the **Inventory Setup** window, inventory costs aren't recorded dynamically in the general ledger, and COGS isn't calculated with a sale. Therefore, you must post to the general ledger manually by running the **Post Inventory Cost to G/L** batch job to update the general ledger and potentially print a report of the value entries that are posted.

The batch job uses value entries as its basis. To calculate the value to post, it uses the difference between the **Cost Amount (Actual)** field and the **Cost Posted to G/L** field in the value entries. If you have selected the **Expected Cost Posting to G/L** check box in the **Inventory Setup** window, then the batch job also posts the difference between the **Cost Amount (Expected)** field and the **Exp. Cost Posted to G/L** field to interim accounts in the general ledger.

> [!NOTE]
> If you have not selected the **Expected Cost Posting to G/L** check box in the **Inventory Setup** window, then the last section of the report will list value entries that are skipped because they represent expected costs.

> [!NOTE] 
> If the batch job encounters an error involving dimensions or dimension setup, then the batch job overrides the error and posts the entry to the general ledger using the dimensions of the value entry.

If you want to make sure that the batch job doesn't encounter any errors, you can run the **Post Invt. Cost to G/L - Test** report to see all errors that could be encountered. You can then fix the errors, and run the **Post Inventory Cost to G/L** batch job, knowing that it processes all entries.
 
> [!IMPORTANT]  
> Before you use this batch job, you should run the **Adjust Cost - Item Entries** batch job. This ensures that, when you run this batch job, the costs that will be posted to the general ledger are up to date.
#### Options

|Option  |Description  |
|--------------|---------|
|**Posting Method**|The batch job can either post inventory value to the general ledger per posting group or per posted entry. If you post per entry, you achieve a detailed specification of how the inventory affects the general ledger, but you also get numerous G/L entries. If you post per posting group, the batch job creates a general ledger entry per posting date per posting group combination. This means that a general ledger entry is created for each combination of posting date, general business posting group, general product posting group, inventory posting group, and location code. In addition, the batch job creates separate general ledger entries for costs with different signs.|
|**Document No.**|In this field, you can enter a document number if you have chosen the Post per Inventory Posting Group option. The document number appears on posted entries.|
|**Post**|Select this field if you want the batch job to post to the general ledger automatically. If you don't choose to post the inventory cost to G/L, the batch job will only print a test report showing the values that can be posted to the general ledger, and on the report will appear: **Test Report (not posted)**.|

### Roll Up Standard Cost

Rolls up the standard costs of assembled and manufactured items. These are influenced by the change in standard costs of components suggested by the **Suggest Item Standard Cost** batch job. In addition, they're influenced by the change in standard cost of production capacity and assembly resources suggested by the **Suggest Work/Mach Ctr Std Cost** batch job.

Once you have run either or both of these batch jobs and you do the roll-up, then all changes to the standard costs in the worksheet are introduced in the associated production or assembly BOMs, and the costs are applied at each BOM level.

> [!NOTE] 
> This function only rolls up the standard cost on the item cards, not on the SKU cards.

This batch job only creates suggestions. It doesn't implement the suggested changes. If you're satisfied with the suggestions and want to implement them, that is update them on the item cards and insert them in the **Revaluation Journal** window, then you can use the **Implement Standard Cost Change** batch job. You access this batch job from the **Standard Cost Worksheet** window.
#### Options

**Calculation Date**: Enter the date that applies to the production BOM version you want to do the roll-up for.
 
### Implement Standard Cost Change

Updates the changes in the standard cost in the **Item** table with the ones in the **Standard Cost Worksheet** table. The standard cost change suggestions can be created with the **Suggest Item Standard Cost** and/or the **Suggest Work/Mach Ctr Std Cost** batch job, and they can also be modified. The contents of all the fields in the standard cost change suggestions are transferred. When you implement suggestions of changes to standard costs, you can see them on the item card and/or on the work/machine center cards. A revaluation journal is also created for you to update the value of existing stock.
#### Options

**Posting Date**: Enter the date that the revaluation should take place.

**Document No.**:Enter the number of the revaluation journal lines. If there's a number series set up on the item journal batch name, the document number follows the ledger entries made by the posting of the revaluation journal. Otherwise, you can manually enter a number.

**Item Journal Template**: Enter the name of the revaluation journal template.

**Item Journal Batch Name**: Enter the name of the actual revaluation journal

Select **OK** to start the batch job. If you don't want to run the batch job now, select **Cancel** to close the window.

## See also

[Design Details: Costing Methods](design-details-costing-methods.md)  
[Update Standard Costs](finance-how-to-update-standard-costs.md)  
[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Create Production BOMs](production-how-to-create-production-boms.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
