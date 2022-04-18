---
title: 
description: 
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---

# Execute tasks in background

App allows perform some tasks in background. Two modes are supported:
- Manually triggered task will be immidiately scheduled via **Job Queue Entries**
- Reccuring tasks sceduled in **Job Queue* Entries*

## To enable execution of tasks in background for specific shop

-   Select 'Allow Background Syncs' if you want to run the synchronization in background.    //TBD: to be moved to "other, part trouleshouting. 
1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and then choose the related link.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Enable **Allow Background Syncs** toggle. 

Now when you trigger sync action, instead of execution in foreground, that force you to wait when it is completed before you can do next action, the task will be created as **Job Queue Entry** and will be executed as soon as possible in non-blocking manner. 

## To schedule recurring tasks 
You can schedule following of reccuring activities to be executed in non-attended manner. For more information about scheduling tasks, see [Job Queue](TBD).

|Task|Object|
|------|------------|
|**Sync Orders from Shopify**|Report TBD Sync Orders From Shopify|
|**Process Shopify Orders**|Reprot TBD Shopify Create Sales Orders|
|**Sync Shipments to Shopify**|Report TBD Sync Shipment to Shopify|
|Sync products|TBD|
|Sync inventory|TBD|
|Sync prices|TBD|
|Sync customers|TBD|

