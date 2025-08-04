---
title: About calculating standard cost
description: A standard cost system determines inventory unit cost based on reasonable historical or expected cost.
author: brentholtorf
ms.topic: concept-article
ms.search.form: 5841,
ms.author: bholtorf
ms.date: 07/01/2025
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# About calculating standard cost

Many manufacturing companies select a valuation base of standard cost. This choice also applies to companies that do light manufacturing, such as assembly and kitting. A standard cost system determines inventory unit cost based on some reasonable historical or expected cost. Studies of past and estimated future cost data can provide the basis for standard costs. These costs are frozen until a decision is made to change them. The actual cost to produce a product can differ from the estimated standard costs. For management control, the actual cost is compared to the standard cost for a specific item and differences, or *variances*, are identified and analyzed.  

Standard costs can be maintained for items that are replenished through purchase, assembly, and production. For each replenishment method, standard costs can consist of the elements listed in the following table.  

|Replenishment system|Standard cost elements|  
|--------------------------|----------------------------|  
|**Purchase**|Direct material cost and overhead material cost if necessary.|  
|**Assembly**|Direct material cost, direct or fixed labor cost, and overhead cost.|  
|**Prod. Order**|Direct material cost, material noninventory cost, labor cost, subcontractor cost, and overhead cost.|  

## Set up standard costs

Because the standard cost of a produced or assembled item can consist of multiple cost elements, including material, capacity (labor) and direct and overhead subcontractor costs, you must establish standard costs for each of these elements.  

The accounting tasks for an item-processing company using standard costing are to:  

- Estimate a standard cost of the finished item and set it up on the item card.  
- Record and allocate the actual cost of the key cost elements and to account for variances.  

To determine the direct cost of a finished item, total all component costs. An assembled or produced item can include subassemblies that also consist of multiple components.  

The following key cost elements make up the total direct cost of a finished processed item:  

- Material costs.  
- Capacity cost.  
- Subcontracting costs for produced items only.  

### Material costs

Material costs are costs that are associated with subassemblies and purchased raw material. Material unit cost can consist of direct and indirect cost elements.  

- Direct material cost represents an invoiced amount for purchased raw materials or the processing cost of a subassembly.  
- Indirect material cost, or *overhead*, can represent elements such as inventory carrying costs for the finished item.  

The setup of the material cost for purchased items that affect direct and indirect cost depends on the costing method that you selected for the specified item. You set up cost information for either costing method on the item card. To learn more, go to [Register New Items](inventory-how-register-new-items.md).

The cost of scrap (production only) is another factor to consider when you calculate the total material cost. Scrapping raw materials when you assemble or produce an item often causes an increase in the quantity of components that are required to produce the item. In turn, this increases the material cost of the components that you consume when you produce a parent item. You set up scrap cost for materials on either the production BOM or routing.  

The material cost of a produced item can be represented in two ways that correspond to the following cost calculation bases.  

|Cost Calculation Basis|Material Cost Calculation|  
|----------------------------|-------------------------------|  
|Single level|The produced item is equal to the total cost of all purchased or subassembled items on that item's production BOM.|  
|Rolled-up level or multilevel|The produced item is the sum of:<br /><br />* The material cost for all subassemblies on the item's BOM. <br />* The cost of all purchased items on the item's production BOM.|  

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
> While run time rates apply for each item unit that is produced, the setup time rates apply for each lot. Therefore, you must prorate the routing setup time for each operation over the lot size. You specify the lot size in the corresponding field on the **Replenishment** FastTab of the **Item Card** page.  

To specify setup time on the routing for planning but exclude this expense in the standard cost calculation, clear the **Cost Incl. Setup** field on the **Manufacturing Setup** page.  

On a single-level basis, this value is the labor cost that is required to produce the finished production item and is specified on the production item's routing. On a multi-level basis, this value is the capacity cost that is specified for each individually produced item that is included in the parent item's BOM.  

### Subcontractor costs

Subcontractor costs are the costs that are associated with services that are provided by a company's outside vendors or subcontractors. Similar to material and capacity, subcontractor costs can consist of both direct and overhead amounts. Direct subcontractor cost represents the actual charge for each unit of services that is provided. For example, overhead subcontractor cost can represent freight and handling costs that the company incurs with a subcontracted order.  

Because subcontracting is an outsourced capacity, you set up the cost of both direct and indirect subcontracting services on the work center card that represents the subcontracting operation.  

## Populate standard cost

You can set standard cost manually or you can calculate the item's standard cost from the **Item card** page. Choose the **Production** group, then choose the **Calc. Production Std Cost** action to update cost of production items or choose the **Assembly** group, then choose the **Calc. Assembly Std. Cost** action to update cost of assembly item. The actions consolidate and roll up the component and capacity costs to calculate the total assembly or manufacturing cost of the items.

To calculate the unit cost of an assembly or production BOM, the parent item and its component items must use the Standard costing method. Resources in the BOM roll-up if they have a unit cost defined on the item, resource, or workcenter. Resources don't use cost defined on stockkeeping unit (SKU).

You can define a production BOM or routing in the SKU, which can be useful if the SKU represents a variant that requires a different set of components or different location. For example, where different production equipment is available. These changes might affect standard cost. You can use the **Calc. Production Std. Cost** action on the **Stockkeeping Unit Card** page to calculate standard cost. Subassemblies use information from items, and not the cost defined on stockkeeping unit. To enable this feature, go to the **Manufacturing Setup** page and turn on the **Load SKU Cost on Manufacturing** toggle.

If you have open entries, after you make a change in the **Standard Cost** field on the item, remember to revaluate inventory. To learn more, go to [Revalue Inventory](inventory-how-revalue-inventory.md).

## Updating standard costs with the Standard Cost Worksheet

The **Standard Cost Worksheet** is intended as a tool for purchasers, production or assembly managers, and internal controllers when they have to review and update standard costs.

Use the **Standard Cost Worksheet** page to do the following:

- Prepare the changes in advance of the date when they have to take effect.
- Simulate the effect on the cost of the manufactured or assembled item if the standard cost for consumption, production capacity usage, or assembly resource usage is changed.
- Execute the changes at a given date and let them take effect immediately.

[!INCLUDE [edit-in-excel](includes/edit-in-excel.md)]

Purchasers use the [**Suggest Item Standard Cost**](#suggest-item-standard-cost) batch job to update and work with the costs of purchased items in one worksheet. When the result is satisfactory, the worksheet is given to the internal controller.

Production or assembly managers use the [**Suggest Work/Mach Ctr Std Cost**](#suggest-workmach-ctr-std-cost) batch job to update and work with the production capacity costs and assembly resource costs of processed items in another worksheet. This worksheet is also given to the internal controller.

Internal controllers use the [**Copy Standard Cost Worksheet**](#copy-standard-cost-worksheet) batch job to consolidate the worksheets into one worksheet. Use the [**Roll Up Standard Cost**](#roll-up-standard-cost) batch job to make a roll-up of the costs from the purchaser and the production or assembly manager. The roll-up determines the standard costs of manufactured and assembled items. Controllers can preview cost changes before and after the roll-up to identify unacceptable deviations. When the updates are acceptable, the controller implements the changes to take effect on a given date.

Use the [**Implement Standard Cost Change**](#implement-standard-cost-change) batch job to implement the standard cost changes. The batch job updates the standard costs of the items that are included in the worksheet. It also creates revaluation journal lines so that you can update the items in stock with the new standard cost.

> [!NOTE]
> Standard cost worksheets don't support stockkeeping units.

### To update standard costs

1. Run the **Adjust Cost-Item Entries** batch job. To start the batch job, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Adjust Cost-Item Entries**, and then choose the related link. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] Review the results and make changes as necessary.  
2. Run the **Post Inventory Cost to G/L** batch job. To start the batch job, choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Post Inventory Cost to G/L**, and then choose the related link. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] Review the results and make changes as necessary.  
3. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Standard Cost Worksheet**, and then use one or more of the following actions:
    1. Run the **Suggest Item Standard Cost** batch job.  
    2. Review the results and make changes as necessary.  
    3. Run the **Suggest Capacity Standard Cost** batch job.  
    4. Review the results and make changes as necessary.
    5. Run the **Roll Up Standard Cost** batch job.
    6. Review the results and make changes as necessary.
    7. Run the **Implement Standard Cost Changes** batch job.  
4. Review and post the **Revaluation Journal** page, which was populated with entries from the previous steps in this process.  

### Suggest item standard cost

Creates suggestions for changing the costs and cost shares of standard costs on item cards. When the batch job completes, the results are available in the **Standard Cost Worksheet** page.

> [!NOTE]  
> This batch job is intended for purchased items only. If you want to update an item with a production BOM or assembly BOM, then you must first fill in the worksheet with all the components and then run the **Roll Up Standard Cost** batch job.

This batch job only creates suggestions. It doesn't implement the suggested changes. If you're satisfied with the suggestions and want to implement them,  then select **Implement Standard Cost Changes** in the **Standard Cost Worksheet** page.

#### Options

**Standard Cost**: Enter the adjustment factor you want to use to update the standard cost. You can also select a rounding method for the new standard cost. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

**Indirect Cost %**: Enter the adjustment factor you want to use to update the indirect cost %. You can also select a rounding method for the new indirect cost %. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

**Overhead Rate**: Enter the adjustment factor you want to use to update the overhead rate. You can also select a rounding method for the new overhead rate. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

### Suggest Work/Mach Ctr Std Cost

Creates suggestions for changing the costs and cost shares of standard costs on work center, machine center, or resource cards. When the batch job completes, the results are available on the **Standard Cost Worksheet** page.

This batch job only creates suggestions. It doesn't implement the suggested changes. If you're satisfied with the suggestions and want to implement them,  then select **Implement Standard Cost Changes** in the **Standard Cost Worksheet** page.

After you run the batch job and want to review the effect on your production or assembly departments, run the **Roll Up Standard Cost** batch job to update standard costs on:

- Work centers
- Machine centers
- Assembly resources
- Production BOMs
- Assembly BOMs

#### Options

**Standard Cost**: Enter the adjustment factor you want to use to update the standard cost. You can also select a rounding method for the new standard cost. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

**Indirect Cost %**: Enter the adjustment factor you want to use to update the indirect cost %. You can also select a rounding method for the new indirect cost %. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

**Overhead Rate**: Enter the adjustment factor you want to use to update the overhead rate. You can also select a rounding method for the new overhead rate. You have to fill in the field using a decimal for the percentage increase, for example 1.1.

### Copy Standard Cost Worksheet

Copies standard cost worksheets from several sources into the **Standard Cost Worksheet** page.

You can only copy one worksheet at a time. The lines from the copied worksheets are placed below each other in the consolidated worksheet. Item lines are listed first, then work/machine center lines are listed, and resource lines are listed last.

### Roll up standard cost

Rolls up the standard costs of assembled and manufactured items. These values are influenced by the change in standard costs of components suggested by the **Suggest Item Standard Cost** batch job. In addition, they're influenced by the change in standard cost of production capacity and assembly resources suggested by the **Suggest Work/Mach Ctr Std Cost** batch job.

After you run either or both of these batch jobs and you do the roll-up, changes to the standard costs in the worksheet apply to the related production or assembly BOMs. The costs are applied at each BOM level.

> [!NOTE] 
> This function only rolls up the standard cost on the item cards, not on the SKU cards.

This batch job only creates suggestions. It doesn't implement the suggested changes. If you're satisfied with the suggestions and want to implement them, then you can use the **Implement Standard Cost Change** batch job. 

#### Options

**Calculation Date**: Enter the date that applies to the production BOM version you want to do the roll-up for.
 
### Implement standard cost change

Updates the changes in the standard cost in the **Item** table with the ones in the **Standard Cost Worksheet** page. The standard cost change suggestions can be created with the **Suggest Item Standard Cost** and/or the **Suggest Work/Mach Ctr Std Cost** batch job, and they can also be modified. The contents of all the fields in the standard cost change suggestions are transferred. When you implement suggestions of changes to standard costs, you can see them on the item card and/or on the work/machine center cards. A revaluation journal is also created for you to update the value of existing stock.

#### Options

**Posting Date**: Enter the date that the revaluation should take place.

**Document No.**: Enter the number of the revaluation journal lines. If there's a number series set up on the item journal batch name, the document number follows the ledger entries made by the posting of the revaluation journal. Otherwise, you can manually enter a number.

**Item Journal Template**: Enter the name of the revaluation journal template.

**Item Journal Batch Name**: Enter the name of the actual revaluation journal

Select **OK** to start the batch job. If you don't want to run the batch job now, select **Cancel** to close the window.

Review and post the **Revaluation Journal** page, which was populated with entries from the previous steps in this process.

## Related information

[Design Details: Costing Methods](design-details-costing-methods.md)  
[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Work with Assembly BOMs](assembly-how-work-assembly-boms.md)  
[Create Production BOMs](production-how-to-create-production-boms.md)  
[Work with Bills of Material](inventory-how-work-BOMs.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
