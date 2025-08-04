---
title: Job queue
description: You can use job queue entries in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Job queue

Businesses often use the job queue to automate recurring tasks in [!INCLUDE [prod_short](../../includes/prod_short.md)]. To learn more about the job queue, go to [Use job queues to schedule tasks](../../admin-job-queues-schedule-tasks.md).

For subscription billing, the following entry is created in the job queue:

* **Update Service Dates** (codeunit 70920758): Automatically updates date fields in service commitments daily at 1:00 AM. To learn more, go to [Termination of contract components](../working-with-contracts/service-commitment-cancellation.md).

## Related information

[General setup](general.md)
