---
title: Job Queue
hide_title: true
sidebar_label: Job Queue
slug: /srb/setup/job-queue
---

# Job Queue
For recurring tasks, in Business Central the Job Queue is used. For details on how the Job Queue works and how to configure it, please refer to <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/admin-job-queues-schedule-tasks" title="Job Queue">this</a> part of the Microsoft documentation.

When **DYCE Subscription & Recurring Billing** is installed, the following entries are automatically created in the Job Queue:
* **Update Service Dates** (codeunit 70920758) <br/>
This task is used to automatically update the date fields in Service Commitments. Please refer to [this](/docs/srb/working-with-contracts/service-commitment-cancellation.md) documentation for the details of this functionality. The task is executed daily at 1am.