---
title: Create scheduled quality inspections
description: Learn how to set up and use scheduled quality inspection tests to ensure proactive quality management through automated, time-based test creation.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Create scheduled quality inspections

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This article explains how to set up and use quality inspections that are created automatically and scheduled to run at regular intervals using job queue entries.

Scheduled inspections enable proactive quality management. They automatically generate quality inspections based on time intervals, rather than business transactions. Using a scheduled inspection approach is ideal for:

- Routine inspections that involve regular sampling of your in-stock inventory.
- Shelf life monitoring where you periodically inspect items that are approaching expiration.
- Environmental compliance inspections to meet time-based requirements.
- Statistical quality control through systematic sampling programs.
- Preventive quality assurance supported by proactive inspection schedules.

<!--## Prerequisites

- Configure quality inspection templates.
- Enable the job queue functionality is enabled.
- Configure inspection generation rules for creating scheduled tests.
- Make items available for scheduled testing.
- Give users the permissions they need for the job queue. -->

## Understand scheduled inspections

The following table illustrates the differences between scheduled and transaction-based inspections.

| Feature | Transaction-Based | Scheduled |
|---------|------------------|-----------|
| Trigger | Business transactions (receipts, output) | Time intervals |
| Frequency | Event-driven | Regular intervals |
| Purpose | Process validation | Proactive monitoring |
| Coverage | All processed items | Sampled items |
| Resource Planning | Reactive | Predictable |

<!--### Business applications

This section describes the business benefits of various types of scheduled inspections.

They're good for routine inventory sampling:

- Randomly inspect the items you have in stock.
- Verify that your storage conditions are suitable.
- Quality drift monitoring.

Do compliance testing:

- Be sure that you meet regulatory requirements.
- Comply with industry standards.
- Prepare for customer audits.

Apply preventive quality control:

- Detect quality issues early.
- Analyze and monitor trends.
- Continuously improve data collection. -->

## Set up scheduled inspections

The following sections provide high-level steps to set up scheduled inspections.

### Configure quality templates

Create templates specifically for scheduled inspections. The following are a few suggestions for things to think about when you do:

- For efficiency, use as simple a set of measurements as you can.
- Focus on critical quality parameters.
- Streamline the settings for regular runs.

To learn more about quality inspection templates, go to [Create quality inspection templates](qms-quality-templates.md).

### Create inspection generation rules and set up a job queue entry

Configure rules specifically for time-based inspection creation.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Inspection Generation Rules**, and then choose the related link.
2. Create a new inspection generation rule for scheduled inspections.
3. Choose the **Schedule Group** field. You're prompted to create a job queue, followed by an option to view it. The next section describes the job queue settings.

### Configure a job queue entry

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Job queue entries**, and then select the related link.
1. In the **Object Type to Run** field, enter **20400**.
1. In the **Maximum No. of Attempts to Run** field, specify a number of retry attempts for failures.
1.  **Rerun Delay**: Specify how long to wait between retry attempts.
- **Status**: Use the **Set Status to Ready** action to update the status to **Ready** and enable the job queue entry.
1. In the **Earliest Start Date/Time** field, specify when to begin scheduled inspections.
1. To schedule the job queue entry to run on a specific day of the week, on the **Recurrence** FastTab, turn on the **Run on <\day of the week>** for the day.
   1. In the **Starting Time** field, specify the time of day to start the recurring job.
   1. In the **Ending Time** field, specify the time of day to stop the recurring job.

## Related information

[Manual Inspection Creation](qms-manual-test-creation.md)  
[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Setting Up Inspection Generation Rules](qms-test-generation-rules.md)  
[Quality Management Setup and Configuration](qms-setup.md)  
[Quality Management Overview](qms-overview.md)