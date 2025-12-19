---
title: Scheduled test creation
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

# Scheduled inspection creation

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This article explains how to set up and use quality inspections that are created automatically and scheduled to run at regular intervals using job queues.

Scheduled inspections enable proactive quality management. They automatically generate quality inspections based on time intervals, rather than business transactions. This capability is ideal for:

- Routine inspections that involve regular sampling of your in-stock inventory.
- Shelf life monitoring where you periodically inspect items that are approaching expiration.
- Environmental compliance inspections to meet time-based requirements.
- Statistical quality control through systematic sampling programs.
- Preventive quality assurance supported by proactive inspection schedules.

## Prerequisites

- Configure quality inspection templates.
- Enable the job queue functionality is enabled.
- Configure inspection generation rules for creating scheduled tests.
- Make items available for scheduled testing.
- Give users the permissions they need for the job queue.

## Understand scheduled inspections

The following table illustrates the differences between scheduled and transaction-based inspections.

| Feature | Transaction-Based | Scheduled |
|---------|------------------|-----------|
| Trigger | Business transactions (receipts, output) | Time intervals |
| Frequency | Event-driven | Regular intervals |
| Purpose | Process validation | Proactive monitoring |
| Coverage | All processed items | Sampled items |
| Resource Planning | Reactive | Predictable |

### Business applications

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
- Continuously improve data collection.

## Set up scheduled inspections

The following sections provide high-level steps to set up scheduled inspections.

### Configure quality templates

Create templates specifically for scheduled inspections. The following are a few suggestions for things to think about when you do:

- For efficiency, use as simple a set of measurements as you can.
- Focus on critical quality parameters.
- Streamline the settings for regular runs.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Templates**, and choose the related link.
2. Create a template for scheduled inspections.
3. Configure measurements that are appropriate for routine testing.
4. Set pass and fail criteria for ongoing monitoring.

### Create inspection generation rules and set up a job queue entry

Configure rules specifically for time-based inspection creation.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Inspection Generation Rules**, and then choose the related link.
2. Create a new inspection generation rule for scheduled inspections.
3. Choose the **Schedule Group** field. You're prompted to create a job queue, followed by an option to view it. The next session describes the job queue settings.

### Configure a job queue entry

The following settings are important for scheduled inspections.

Enter the following settings that control when, and how often the job queue entry runs:

- **Earliest Start Date/Time**: Specify when to begin scheduled inspections.
- **Run on <\day of the week>**: Schedule the job queue entry to run on a specific day.
- **Starting Time**: Specify the time of day to start.
- **Ending Time**: Specify the time of day to stop.

Enter the following settings that control **Execution Parameters**:

- **Maximum No. of Attempts**: Retry logic for failures.
- **Rerun Delay**: Wait time between retry attempts.
- **Status**: Use the **Set Status to Ready** action to update the status to **Ready** and enable the job queue entry.

## Troubleshooting scheduled inspections

The following sections describe typical issues and suggest solutions.

### The job queue entry isn't running

- Verify that the job queue service is running.
- Double-check the status of the job queue entry.
- Verify that users have the permissions they need.

### No inspections are created

- Verify the settings for your inspection generation rule.
- Double-check your item filters and availability.
- Review the codeunit parameters.

### Too many inspections are created

- Adjust your sampling percentages.
- Refine your item filters.
- Review the selection logic.

## Best Practices

There are several things to think about when you determine your strategy for scheduling. Use a balanced approach, and combine scheduled and transaction-based inspections. Focus your scheduled inspections on high-risk areas, and maintain statistical validity.

Consider the capacity of your inspectors, and coordinate with operational schedules.

Regularly evaluate the effectiveness of your scheduled inspections. Adjust frequencies and optimize resource allocation based on your findings.

Use the data from your tests to drive decisions about process improvements. Identify quality trends and patterns that support vendor quality discussions.

## Related information

[Manual Inspection Creation](qms-manual-test-creation.md)  
[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Setting Up Inspection Generation Rules](qms-test-generation-rules.md)  
[Quality Management Setup and Configuration](qms-setup.md)  
[Quality Management Overview](qms-overview.md)