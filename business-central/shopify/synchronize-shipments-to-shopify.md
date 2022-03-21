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

# Synchronize Shipments to Shopify

When a sales order that is created from a Shopify Order, is shipped, you can synchronize the shipments to Shopify.

The customer will automatically receive a shipment notice email.
When a Shipping Agent and a Tracking Code is specified on the shipment, the tracking information will be included in the email.

![](media/image102.png)

## By batch task

You can synchronize the shipment by executing the task "Synchronize Shipments To Shopify".

This task can be found by using the search function on the Role Center.

![](media/image103.png)

![](media/image104.png)

## By job queue

You can also schedule a job to synchronize shipments to Shopify orders that runs for example every few minutes.

You can find the job queue entries by using the search function from the Role Center:

![](media/image84.png)

Define the recurrence of the job queue 'Sync Shipments to Shopify' and start the job queue.

![](media/image105.png)


