---
title: Running tasks in background 
description: Configure synchronization of data between Business Central and Shopify in background.
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---

# Running tasks in background

Extension will grant the ability to perform some tasks in the background. Two modes are supported:

- Manually triggered task will be immediately scheduled via **Job Queue Entries**
- Recurring tasks will be scheduled in **Job Queue Entries**

## Running tasks in background for specific shop

1. Choose the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter the name of **Shopify Shop** and choose the shop name from the list.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Enable **Allow Background Syncs** toggle.

Now when you trigger sync action, instead of task running in the foreground, it asks you to wait. When it is completed, you can proceed to the next action. The task will be created as **Job Queue Entry** and will start instantly in a non-blocking manner.

## To schedule recurring tasks

You can schedule the following recurring activities to be performed in a automated manner. For more information about scheduling tasks, see [Job Queue](../admin-job-queues-schedule-tasks.md).

|Task|Object|
|------|------------|
|**Sync Orders from Shopify**|Report 30104 Sync Orders From Shopify|
|**Process Shopify Orders**|Report 30103 Shopify Create Sales Orders|
|**Sync Shipments to Shopify**|Report 30109 Sync Shipment to Shopify|
|**Sync products and or prices**|Report 30108 Shopify Sync Products|
|**Sync inventory**|Report 30102 Sync Stock to Shopify|
|**Sync Images**|Report 30107 Shopify Sync Images|
|**Sync Customers**|Report 30100 Shopify Sync Customers|
|**Sync Payments**|Report 30105 Shopify Sync Payments|
