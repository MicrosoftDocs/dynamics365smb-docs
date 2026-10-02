---
title: About calculating standard cost
description: A standard cost system determines inventory unit cost based on reasonable historical or expected cost.
author: brentholtorf
ms.topic: concept-article
ms.search.form: 5841,
ms.author: bholtorf
ms.date: 10/01/2026
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# About calculating standard cost

Many manufacturing companies select a valuation base of standard cost. This choice also applies to companies that do light manufacturing, such as assembly and kitting. A standard cost system determines inventory unit cost based on some reasonable historical or expected cost. Studies of past and estimated future cost data can provide the basis for standard costs. These costs are frozen until a decision is made to change them. The actual cost to produce a product can differ from the estimated standard costs. For management control, the actual cost is compared to the standard cost for a specific item and differences, or *variances*, are identified and analyzed.  

Standard costs can be maintained for items that are replenished through purchase, assembly, and production. For each replenishment method, standard costs can consist of the elements listed in the following table.  

|Replenishment system|Standard cost elements|  
|--------------------------|----------------------------|  
|Purchase|Direct material cost and overhead material cost if necessary.|  
|Assembly|Direct material cost, direct or fixed labor cost, and overhead cost.|  
|Prod. Order|Direct material cost, material noninventory cost, labor cost, subcontractor cost, and overhead cost.|  

## Set up standard costs

Because the standard cost of a produced or assembled item can consist of multiple cost elements, including material, capacity (labor) and direct and overhead subcontractor costs, you must establish standard costs for each of these elements.  

The accounting tasks for an item-processing company using standard costing are to:  

- Estimate a standard cost of the finished item and set it up on the item.  
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

The setup of the material cost for purchased items that affect direct and indirect cost depends on the costing method that you selected for the specified item. You set up cost information for either costing method on the item. To learn more, go to [Register New Items](inventory-how-register-new-items.md).

The cost of scrap (production only) is another factor to consider when calculating the total material cost. Scrapping raw materials when you assemble or produce an item often increases the quantity of components required to produce the item. This increase raises the material cost of the components you consume when producing a parent item. You set up scrap cost for materials on either the production bill of materials (BOM) or routing.  

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

> To specify setup time on the routing for planning but exclude this expense in the standard cost calculation, turn off the **Cost Incl. Setup** toggle on the **Manufacturing Setup** page.

On a single-level basis, this value is the labor cost required to produce the finished production item and is specified on the production item's routing. On a multilevel basis, this value is the capacity cost for each individually produced item that's included in the parent item's BOM.

### Subcontractor costs

Subcontractor costs are the costs that are associated with services that are provided by a company's outside vendors or subcontractors. Similar to material and capacity, subcontractor costs can consist of both direct and overhead amounts. Direct subcontractor cost represents the actual charge for each unit of services that is provided. For example, overhead subcontractor cost can represent freight and handling costs that the company incurs with a subcontracted order.  

Because subcontracting is an outsourced capacity, you set up the cost of both direct and indirect subcontracting services on the work center that represents the subcontracting operation.  

### Noninventory item costs

Production BOMs can include noninventory items, such as consumables, services, or miscellaneous charges that are consumed during production but don't carry inventory. By default, [!INCLUDE [prod_short](includes/prod_short.md)] doesn't include the cost of noninventory items in the standard cost of the produced item.

To include noninventory item costs in manufacturing, go to the **Manufacturing Setup** page and turn on the **Include Non-Inventory Items to Produced Items** toggle. When the toggle is enabled:

- Noninventory item costs appear as extra value entries linked to the output item ledger entry.
- The value entry type is **Direct Cost - Non Inventory**.
- Variances between expected and actual noninventory costs post to a dedicated **Material Non-Inventory Variance Account** in the general ledger.
- The **BOM Cost Shares** page shows **Rolled-up Material Non-Inventory Cost** and **Single-level Material Non-Inventory Cost** fields so you can review how noninventory items contribute to the total cost.

To set up the general ledger accounts, go to the **General Posting Setup** page and fill in the **Direct Cost Non-Inventory Applied Account** and the **Material Non-Inventory Variance Account** fields for the relevant business and product posting group combinations.

> [!NOTE]
> Noninventory item costs don't apply to assembly orders, only production orders.

## Example: Calculate standard cost for a production item

The following example shows how material, noninventory material, capacity, subcontracting, capacity overhead, and manufacturing overhead contribute to the standard cost of a production item. It also shows how the item lot size distributes setup cost across the items in a production lot.

### Set up the example

On the **Manufacturing Setup** page, use the settings described in the following table:

| Field | Value |
|---|---:|
| **Cost Incl. Setup** | On |
| **Include Non-Inventory Items to Produced Items** | On |

Create the items described in the following table. The production item has an overhead percentage and a fixed overhead rate so that the example includes manufacturing overhead.

| Item | Type and replenishment | Cost setup |
|---|---|---|
| FINISHED | Inventory, replenished by production order | **Costing Method** = Standard; **Indirect Cost %** = 10; **Overhead Rate** = 3; **Lot Size** = 1, then 10 |
| INV-COMP | Inventory, replenished by purchase | **Unit Cost** = 10; no indirect cost or overhead rate |
| NONINV-COMP | Non-Inventory | **Unit Cost** = 4; no indirect cost or overhead rate |

Create and certify a production BOM for the FINISHED item with the following lines:

| Component | Quantity per |
|---|---:|
| INV-COMP | 2 |
| NONINV-COMP | 3 |

Create the following work centers. Use **MINUTES** as the unit of measure for capacity and routing times.

| Work center | Purpose | Unit Cost Calculation | Direct Unit Cost | Indirect Cost % | Overhead Rate |
|---|---|---|---:|---:|---|
| 100 | Internal operation charged by produced unit | Units | 5 | 20 | 1 |
| 200 | Internal operation charged by time | Time | 2 | 0 | 0 |
| 500 | Subcontracting operation charged by produced unit | Units | 7 | 0 | 0 |

Assign a subcontractor vendor to work center 500. Leave the work center's indirect cost and overhead rate at zero so that its direct unit cost appears entirely as subcontracted cost.

Create and certify a routing for the FINISHED item with the operations described in the following table:

| Operation | Work center | Setup Time | Run Time | Time unit |
|---|---|---:|---:|---|
| 10 | 100 | 0 | 1 | Minutes |
| 20 | 200 | 10 | 1 | Minutes |
| 30 | 500 | 0 | 1 | Minutes |

For a work center that uses **Units**, the produced quantity determines the cost quantity. Setup time and run time don't determine the cost quantity. For a work center that uses **Time**, run time applies to each produced unit, while setup time applies once to the production lot when you turn on the **Cost Incl. Setup** toggle.

### Review the result for lot size 1

On the FINISHED item, set the **Lot Size** field to **1**. On the **Item Card** page, choose the **Production** group, and then choose the **Calc. Production Std. Cost** action. Learn more in [Populate standard cost](#populate-standard-cost).

| Cost share | Amount | Explanation |
|---|---:|---|
| Material Cost | 20.00 | The INV-COMP item's unit cost of 10 multiplied by the BOM quantity of 2. |
| Material Non-Inventory Cost | 12.00 | The NONINV-COMP item's unit cost of 4 multiplied by the BOM quantity of 3. |
| Capacity Cost | 27.00 | Work center 100 contributes 5 for one produced unit. Work center 200 contributes 22, calculated as *(10 setup minutes + 1 run minute) × 2 per minute*. |
| Subcontracted Cost | 7.00 | The work center direct unit cost of 7 multiplied by one produced unit. |
| Capacity Overhead Cost | 2.00 | Work center 100 contributes as *5 direct cost × 20% + 1 overhead rate*. The other work centers don't have capacity overhead in this example. |
| Manufacturing Overhead Cost | 9.80 | The production item's overhead is calculated as *10% × (20 material + 12 noninventory material + 27 capacity + 7 subcontracting + 2 capacity overhead) + 3 overhead rate*. |
| Standard Cost | 77.80 | The sum of all cost shares, calculated as *20 + 12 + 27 + 7 + 2 + 9.80*. |

### Review the result for lot size 10

On the FINISHED item, change the value in the **Lot Size** field to **10**, and then calculate the production standard cost again.

| Cost share | Amount | Explanation |
|---|---:|---|
| Material Cost | 20.00 | The lot cost is calculated as *10 unit cost × 2 components × 10 finished items = 200*. The per-unit cost is calculated as *200 ÷ 10 = 20*. |
| Material Non-Inventory Cost | 12.00 | The lot cost is calculated as *4 unit cost × 3 components × 10 finished items = 120*. The per-unit cost is calculated as *120 ÷ 10 = 12*. |
| Capacity Cost | 9.00 | Work center 100 contributes 5 per item. Work center 200 contributes 4 per item, calculated as *(10 setup minutes + 1 run minute × 10 items) × 2 per minute ÷ 10 items*. |
| Subcontracted Cost | 7.00 | The lot cost is calculated as *7 work center direct unit cost × 10 items = 70*. The per-unit cost is calculated as *70 ÷ 10 = 7*. |
| Capacity Overhead Cost | 2.00 | Work center 100 contribution is calculated as *(5 direct cost × 20% + 1 overhead rate) × 10 items ÷ 10 items*. |
| Manufacturing Overhead Cost | 8.00 | The production item's overhead is calculated as *10% × (20 material + 12 noninventory material + 9 capacity + 7 subcontracting + 2 capacity overhead) + 3 overhead rate*. |
| Standard Cost | 58.00 | The sum of all cost shares, calculated as *20 + 12 + 9 + 7 + 2 + 8*. |

The larger lot size reduces only the setup cost per finished item in this example. Material quantities, unit-based operations, subcontracting, and fixed per-item overhead remain proportional to the number of finished items.

### Exclude setup cost

To compare the result when setup time is used only for planning, for the FINISHED item, set the **Lot Size** field to **1**. On the **Manufacturing Setup** page, turn off **Cost Incl. Setup** toggle. Calculate the production standard cost again.

| Cost share | Amount | Explanation |
|---|---:|---|
| Material Cost | 20.00 | The inventory component setup is unchanged. |
| Material Non-Inventory Cost | 12.00 | The noninventory component setup is unchanged. |
| Capacity Cost | 7.00 | Work center 100 contributes 5. Work center 200 contributes only *1 run minute × 2 per minute = 2*. The 10 setup minutes don't contribute to standard cost. |
| Subcontracted Cost | 7.00 | The subcontracting work center's direct unit cost is unchanged. |
| Capacity Overhead Cost | 2.00 | The overhead from work center 100 is unchanged. |
| Manufacturing Overhead Cost | 7.80 | The production item's overhead is calculated as *10% × (20 material + 12 noninventory material + 7 capacity + 7 subcontracting + 2 capacity overhead) + 3 overhead rate*. |
| **Standard Cost** | **55.80** | The sum of all cost shares is calculated as *20 + 12 + 7 + 7 + 2 + 7.80*. |

### Exclude noninventory item cost

To compare the result when noninventory components are excluded, turn on the **Cost Incl. Setup** toggle, keep the **Lot Size** field value at **1** for the FINISHED item, and turn off the **Include Non-Inventory Items to Produced Items** toggle. Calculate the production standard cost again.

| Cost share | Amount | Explanation |
|---|---:|---|
| Material Cost | 20.00 | The inventory component is still included. |
| Material Non-Inventory Cost | 0.00 | The setting excludes the noninventory component's cost from the production item's standard cost. |
| Capacity Cost | 27.00 | Both internal operations are included, including setup time for work center 200. |
| Subcontracted Cost | 7.00 | The subcontracting work center's direct unit cost is unchanged. |
| Capacity Overhead Cost | 2.00 | The overhead from work center 100 is unchanged. |
| Manufacturing Overhead Cost | 8.60 | The production item's overhead is calculated as *10% × (20 material + 27 capacity + 7 subcontracting + 2 capacity overhead) + 3 overhead rate*. The excluded noninventory amount isn't part of the percentage base. |
| Standard Cost | 64.60 | The sum of all included cost shares is calculated as *20 + 27 + 7 + 2 + 8.60*. |

## Populate standard cost

You can set the standard cost manually or calculate it on the **Item Card** page. To update the cost of production items, choose the **Production** group, and then choose the **Calc. Production Std. Cost** action. To update the cost of assembly items, choose the **Assembly** group, and then choose the **Calc. Assembly Std. Cost** action. The actions consolidate and roll up the component and capacity costs to calculate the total assembly or manufacturing cost of the items.

When you run **Calc. Production Std. Cost**, you choose one of the following calculation levels:

- **Single Level**: Calculate the cost of the finished item by summing up the direct costs of its components and capacity from the item's production BOM and routing. Use this level when component costs are already correct and you only need to update the parent item.
- **All Levels**: Recalculate costs for the entire BOM structure. Starts from the lowest-level purchased or produced items and rolls costs up through every intermediate subassembly to the top-level item. Use this level after changes to purchased item costs or to routing rates that affect multiple BOM levels.

The all-levels calculation processes items in bottom-up order. Purchased raw materials and lowest-level subassemblies are evaluated first, then their costs feed into the next BOM level, until the top-level finished item cost is complete. This process ensures that each level reflects the latest component and capacity costs.

To calculate the unit cost of an assembly or production BOM, the parent item and its component items must use the Standard costing method. Resources in the BOM roll-up if they have a unit cost defined on the item, resource, or work center. Resources don't use cost defined on stockkeeping unit (SKU).

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

1. Run the **Adjust Cost-Item Entries** batch job. To start the batch job, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Adjust Cost-Item Entries**, and then choose the related link. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] Review the results and make changes as necessary.  
2. Run the **Post Inventory Cost to G/L** batch job. To start the batch job, [!INCLUDE[open-search](includes/open-search-lowercase.md)], enter **Post Inventory Cost to G/L**, and then choose the related link. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] Review the results and make changes as necessary.  
3. [!INCLUDE[open-search](includes/open-search.md)], enter **Standard Cost Worksheet**, and then use one or more of the following actions:
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

Updates the changes in the standard cost in the **Item** table with the ones in the **Standard Cost Worksheet** page. The standard cost change suggestions can be created with the **Suggest Item Standard Cost** and/or the **Suggest Work/Mach Ctr Std Cost** batch job, and they can also be modified. The contents of all the fields in the standard cost change suggestions are transferred. When you implement suggestions of changes to standard costs, you can see them on the item and/or on the work/machine center cards. A revaluation journal is also created for you to update the value of existing stock.

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
