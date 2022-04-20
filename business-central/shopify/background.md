---
title: Execute tasks in background 
description: Configure synchronization of data between Business Central and Shopify in background.
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---

# Execute tasks in background

Extension allows perform some tasks in background. Two modes are supported:
- Manually triggered task will be immediately scheduled via **Job Queue Entries**
- Recurring tasks scheduled in **Job Queue* Entries*

## To enable execution of tasks in background for specific shop

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Enable **Allow Background Syncs** toggle. 

Now when you trigger sync action, instead of execution in foreground, that forces you to wait when it's completed before you can do next action, the task will be created as **Job Queue Entry** and will be executed as soon as possible in non-blocking manner. 

## To schedule recurring tasks 

You can schedule following of recurring activities to be executed in non-attended manner. For more information about scheduling tasks, see [Job Queue](../admin-job-queues-schedule-tasks.md).

|Task|Object|
|------|------------|
|**Sync Orders from Shopify**|Report 30104 Sync Orders From Shopify|
|**Process Shopify Orders**|Report 30103 Shopify Create Sales Orders|
|**Sync Shipments to Shopify**|Report 30109 Sync Shipment to Shopify|
|Sync products|TBD|
|Sync inventory|TBD|
|Sync prices|TBD|
|Sync customers|TBD|

