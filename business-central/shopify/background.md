---
title: Run tasks in the background and recurrently
description: Configure synchronization of data between Business Central and Shopify in the background.
ms.date: 01/09/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
author: brentholtorf
ms.author: bholtorf
ms.custom: bap-template
---

# Run tasks in the background

It's efficient to run some tasks simultaneously and in an automated manner. You can perform such tasks in the background and can also set a schedule when you want those tasks to run automatically. To run tasks in the background, two modes are supported:

- Manually triggered tasks are scheduled immediately via **Job Queue Entries**.
- Recurring tasks are scheduled in **Job Queue Entries**.

## Run tasks in the background for a specific shop

1. Choose the ![Lightbulb that opens the Tell Me feature.](../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Shopify Shop**, and choose the related link.
2. Select the shop for which you want to run synchronization in the background to open the **Shopify Shop Card** page.
3. Turn on the **Allow Background Syncs** toggle.

Now, when the sync action starts, instead of running a task in the foreground it asks you to wait. When it completes, you can proceed to the next action. The task is created as a **Job Queue Entry** and starts immediately.

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
|**Sync companies**|Report 30114 Shopify sync companies (B2B)|
|**Sync payouts and payment transactions**|Report 30105 Shopify sync payouts|
|**Sync disputes**|Report 30120 Shopify sync disputes|
|**Sync catalogs**|Report 30115 Shopify sync catalogs|
|**Sync catalog prices**|Report 30116 Shopify sync catalog prices|

> [!NOTE]
> Several tasks might update some elements. For example, when you import orders, depending on the setting on the **Shopify Shop Card** page, [!INCLUDE [prod_short](../includes/prod_short.md)] might also import and update customer and/or product data. To avoid conflicts, remember to use the same job queue category.
>
> Use the **Report Request Page** action to define filters and parameters. For example, you can specify that you import orders only when their status is **Fully Paid**, or turn on the **Only Sync Prices** toggle to ensure that product synchronization only updates prices, but not products.

Other tasks that can be helpful to automate further processing of sales documents:

- Report 297 Batch Post Sales Invoices
- Report 296 Batch Post Sales Orders

You can use the **Shopify Order No.** field to identify sales documents that were imported from Shopify.

To learn more about posting sales orders in a batch, go to [To create a job queue entry for batch posting of sales orders](../ui-batch-posting.md#to-create-a-job-queue-entry-for-batch-posting-of-sales-orders).

## To check the status of synchronization

On the **Business Manager** Role Center, the **Shopify Activities** part offers several cues that can help you quickly identify whether there are issues with Shopify Connector.

- **Unmapped Customers**: Shopify customer is imported, but isn't linked to a corresponding customer entry in [!INCLUDE [prod_short](../includes/prod_short.md)].
- **Unmapped Companies**: Shopify company (B2B) is imported, but isn't linked to a corresponding customer entry in [!INCLUDE [prod_short](../includes/prod_short.md)].
- **Unmapped Products** - Shopify product is imported, but isn't linked to a corresponding item entry in [!INCLUDE [prod_short](../includes/prod_short.md)].
- **Unprocessed Orders**: Shopify orders are imported, but sales documents in [!INCLUDE [prod_short](../includes/prod_short.md)] weren't created, often because of unmapped products or customers.
- **Unprocessed Shipments**: Posted sales shipments originated from Shopify orders aren't synchronized with Shopify.
- **Shipments Errors**: Shopify Connector couldn't synchronize posted sales shipments with Shopify.
- **Synchronization Errors**: There are failed job queue entries related to synchronization with Shopify.
- **Unprocessed Order Updates**: There are Shopify orders that were already processed in [!INCLUDE [prod_short](../includes/prod_short.md)], but a new edition was received from Shopify. Because changes weren't synchronized to the processed order in [!INCLUDE [prod_short](../includes/prod_short.md)], you must update the processed documents to match the received data from Shopify. To learn more, go to [Effect of order editing](synchronize-orders.md#effect-of-order-editing).

> [!Tip]
> Use the **Set up cues** action in the **Shopify Activities** part to define thresholds for cue styles. By default, the cue displays in yellow if the count is between one and five, and in red if count is five or higher.

## Related information

[Shopify Connector overview](shopify-connector-overview.md)  
[FAQ for the Shopify connector](shopify-faq.md)  
[Troubleshoot the Shopify Connector](troubleshoot.md)  
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)  
