---
title: Configure production processes
description: To convert material into produced end items, production resources, such as bills of material, routings, machine operators, and machinery must be set up in the system.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.form: 99000768, 99000779, 99000780, 99000866
ms.date: 09/11/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Setting up manufacturing

To convert material into produced end items, you must set up production resources, such as bills of material, routings, machine operators, and machinery.

In [!INCLUDE [prod_short](includes/prod_short.md)], machine centers represent operators and machines. You can organize machine centers in work centers and work center groups. When these resources are established, you can load them with operations according to the item's defined material (BOM) and process (routing) structure, and according to the capacity of the machine or work center. You can also set the production capacity of each resource. The work time available in the machine and work centers define capacity, governed by calendars for each level. A work center calendar specifies the working days or hours, shifts, holidays, and absence that determine the work center's gross available capacity (typically measured in minutes). The efficiency and capacity values you define determine all of this.  

After you set up manufacturing, you can plan and fulfill production orders. To learn more, go to [Planning](production-planning.md) and [Manufacturing](production-manage-manufacturing.md).  

The following table describes a sequence of tasks, with links to the articles that describe them.

|**To**|**Go to**|  
|------------|-------------|  
|Configure the manufacturing features, such as defining shop floor work hours and cost calculation parameters.|The **Manufacturing Setup** page.|
|On the **Planning** tab on the **Inventory Setup** page, set global planning parameters that override parameters set on individual item cards.|[Design Details: Planning Parameters](design-details-planning-parameters.md)|
|Define a standard working week in the manufacturing department in terms of starting and ending times of each work day and related work shift.|[Create Shop Calendars](production-how-to-create-work-center-calendars.md)|  
|Organize fixed values and requirements of production resources as work centers or machine centers to govern their output of production performed.|[Set Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md)|
|Organize production operations in the required order and assign them to work or machine centers with the required work times.|[Create Routings](production-how-to-create-routings.md)|
|Organize production components or subassemblies under a produced parent item and certify the BOM for execution at work centers.|[Create Production BOMs](production-how-to-create-production-boms.md)|
|Make sure that the right component quantity is available when produced items are stocked in one unit of measure but produced in another.|[Work With Manufacturing Batch Units of Measure](production-how-to-use-the-manufacturing-batch-unit-of-measure.md)|  
|Define families of production items with similar manufacturing processes to save consumption. For example, four pieces of the same item can be produced from one sheet and 10 pieces of another, different, item at the same time.|[Work With Production Families](production-how-work-family.md)|
|Use standard tasks to simplify the creation of routings by quickly attaching extra information to recurring operations.|[Set Up Standard Routing Lines](production-how-set-up-standard-routing-lines.md)|  
|Prepare work centers and routings to represent subcontracted production operations.|[Subcontract Manufacturing](production-how-to-subcontract-manufacturing.md)|  

## Related information

[Manufacturing](production-manage-manufacturing.md)  
[Planning](production-planning.md)  
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
