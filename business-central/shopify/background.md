---
title: Run Tasks in the Background and Recurrently
description: Configure synchronization of data between Business Central and Shopify in background.
ms.date: 05/11/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.reviewer: solsen
author: brentholtorf
ms.author: bholtorf
---

# Run Tasks in the Background

It's efficient to run some tasks simultaneously and in an automated manner. You can perform such tasks in the background and can also set a schedule when you want those tasks to run automatically. To run tasks in the background, two modes are supported:

- Manually triggered tasks are scheduled immediately via **Job Queue Entries**.
- Recurring tasks are scheduled in **Job Queue Entries**.

## Run tasks in the background for a specific shop

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the shop for which you want to run synchronization in background to open the **Shopify Shop Card** page.
3. Turn on the **Allow Background Syncs** toggle.

Now, when the sync action is triggered, instead of a task running in the foreground, it will ask you to wait. When it's completed, you can proceed to the next action. The task is created as a **Job Queue Entry** and starts immediately.

## To schedule recurring tasks

You can schedule the following recurring activities to be performed in an automated manner. Learn more about scheduling tasks at [Job Queue](../admin-job-queues-schedule-tasks.md).

|Task|Object|
|------|------------|
|**Sync orders from Shopify**|Report 30104 Sync orders from Shopify|
|**Process Shopify orders**|Report 30103 Shopify create sales orders|
|**Sync shipments to Shopify**|Report 30109 Sync shipment to Shopify|
|**Sync products and/or prices**|Report 30108 Shopify sync products|
|**Sync inventory**|Report 30102 Sync stock to Shopify|
|**Sync images**|Report 30107 Shopify sync images|
|**Sync customers**|Report 30100 Shopify sync customers|
|**Sync payments**|Report 30105 Shopify sync payments|

> [!NOTE]
> Some elements might be updated by several tasks, for example when you import orders, depending on the setting in the **Shopify Shop Card**, the system may also import and update customer and/or product data. Remember to use the same job queue category to avoid conflicts.

Other tasks that can be helpful to automate further processing of sales documents:

- report 297 Batch Post Sales Invoices
- report 296 Batch Post Sales Orders

You can use the **Shopify Order No.** field to identify sales documents that were imported from Shopify.

To learn more about posting sales orders in a batch, go to [To create a job queue entry for batch posting of sales orders](../ui-batch-posting.md#to-create-a-job-queue-entry-for-batch-posting-of-sales-orders).

## See also

[Get Started with the Connector for Shopify](get-started.md)  
