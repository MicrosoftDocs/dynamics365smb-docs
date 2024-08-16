---
title: Job queue
description: You can use job queue entries in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Job queue

For recurring tasks, in Business Central the Job Queue is used. For details on how the Job Queue works and how to configure it, please refer to <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/admin-job-queues-schedule-tasks" title="Job Queue">this</a> part of the Microsoft documentation.

When **Subscription & Recurring Billing** is installed, the following entries are automatically created in the Job Queue:
* **Update Service Dates** (codeunit 70920758) <br/>
This task is used to automatically update the date fields in Service Commitments. Please refer to [Termination of contract components](../working-with-contracts/service-commitment-cancellation.md) for the details of this functionality. The task is executed daily at 1 AM.