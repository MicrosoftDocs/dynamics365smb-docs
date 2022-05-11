---
title: Run tasks the in background 
description: Configure synchronization of data between Business Central and Shopify in background.
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---

# Run Tasks in the Background

You can perform some tasks in the background. Two modes are supported:

- Manually triggered task is scheduled immediately via **Job Queue Entries**
- Recurring tasks are scheduled in **Job Queue Entries**

## Run tasks in the background for a specific shop

1. Choose the search ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter the name of **Shopify Shop** and then choose the shop name from the list.
2. Select the Shop for which you want to synchronize items to open **Shopify Shop Card** page.
3. Enable **Allow Background Syncs** toggle.

Now, when the sync action is triggered, instead of a task running in the foreground, it will ask you to wait. When it's completed, you can proceed to the next action. The task is created as **Job Queue Entry** and starts instantly in a non-blocking manner.

## To schedule recurring tasks

You can schedule the following recurring activities to be performed in an automated manner. For more information about scheduling tasks, see [Job Queue](../admin-job-queues-schedule-tasks.md).

|Task|Object|
|------|------------|
|**Sync orders from Shopify**|Report 30104 Sync Orders From Shopify|
|**Process Shopify orders**|Report 30103 Shopify Create Sales Orders|
|**Sync shipments to Shopify**|Report 30109 Sync Shipment to Shopify|
|**Sync products and/or prices**|Report 30108 Shopify Sync Products|
|**Sync inventory**|Report 30102 Sync Stock to Shopify|
|**Sync images**|Report 30107 Shopify Sync Images|
|**Sync customers**|Report 30100 Shopify Sync Customers|
|**Sync payments**|Report 30105 Shopify Sync Payments|

## See Also
