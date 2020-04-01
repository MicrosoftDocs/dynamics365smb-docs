---
title: Set Up Opportunity Sales Cycles and Cycle Stages| Microsoft Docs
description: Describes how to define sales stages, from initial contact to closing, to create a sales cycle and assign it to opportunities in Business Central.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect
ms.date: 04/01/2020
ms.author: jswymer

---
# Set Up Opportunity Sales Cycles and Cycle Stages
Before you can start using sales opportunities, you must set up sales cycles and sales cycle stages. A sales cycle is made up of a series of stages that go from the initial contact to the closing of a sale. Each stage can have certain requirements that must be met, such as requiring a sales quote, before an opportunity can go to the next stage. You can also specify whether a stage can be skipped. You can setup as many sales cycles as you need, and you can set up as many sales cycle stages as necessary within a sales cycle.

Implementing opportunity sales cycles involves setting up the sales cycle, defining the different stages of the cycle, and then assigning the cycle to opportunities. Assigning the relevant activity or tasks to the opportunity may also be part of setting up a sales cycle.

This topic also describes how to set up tasks and activities, and how to assign tasks to activities. For more information, see [To set up activities with tasks](marketing-how-setup-opportunity-sales-cycles-stages.md#to-set-up-activities-with-tasks).

## To set up opportunity sales cycle codes
1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Cycles**, and then choose the related link. The **Sales Cycles** page opens, and lists all the existing sales cycles.
2. Choose the **New** action, and fill in the fields as necessary. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Repeat these steps to set up as many sales cycles as you want. After you have set up opportunity sales cycles, you may want to set up the different stages within each cycle.

## To define opportunity sales cycle stages
1. On the **Sales Cycles** page, select the opportunity sales cycle for which you want to set up stages, and then choose the **Stages** action. The **Sales Cycle Stages** page opens.
2. Choose the **New** action to enter a new stage in the sales cycle.

Repeat these steps to set up as many stages as you want within the sales cycle.

## To assign stage cycles to opportunities
After you add the opportunities stage cycle, you can start to add sales opportunities, and then assign the stage cycle to opportunities by setting the **Sales Cycle Code** field. For more information, see [Create Sales Opportunities](marketing-how-create-opportunities.md).

## To set up activities with tasks
You can combine multiple task, for example tasks that each represent a step, in activities. Activity tasks are related to each other by a date formula. You can assign activities to opportunities, salespeople, or contacts.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Activities**, and then choose the related link.
2. Choose the **New** action, and fill in the fields as necessary.
3. On the **Lines** FastTab, fill in the fields as necessary to define one or more tasks in the activity.

## To assign tasks or activities of tasks to opportunities
When you have set up a task, you can assign it to a sales opportunity and thereby assign the activity that the task belongs to.

> [!NOTE]  
>   This procedure describes how to assign activity tasks to opportunities. the steps are similar when you assign tasks to salespeople and contacts.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Opportunities**, and then choose the related link.
2. Select an opportunity, and then choose the **Tasks** action.
3. On the **Task List** page, choose the **Create Task** action.
4.  The **Create Task** page, fill in the fields as necessary.

    Notice in the **Opportunity** field, that it is automatically assigned to the opportunity in question.
5. Choose the **OK** button.
6. On the **Task List** page, select the new task, and then choose the **Assign Activities** action.
7. On the **Assign Activity** page, fill in the fields as necessary, and then choose the **OK** button.

## See Also
[Processing Sales Opportunities](marketing-processing-sales-opportunities.md)  
[Sales](sales-manage-sales.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
