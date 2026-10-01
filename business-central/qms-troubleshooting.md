---
title: Troubleshoot quality management features
description: Learn how to troubleshoot common issues in quality management, from setup to workflows, and resolve problems with inspections, templates, and lot blocking.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 20400, 20408, 20404, 20402, 20416,
ms.date: 09/04/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Troubleshoot quality management features

This article can help you diagnose and resolve common issues with quality management in [!INCLUDE [prod_short](includes/prod_short.md)]. It groups typical symptoms by feature area, and suggests things to consider and ways to get unblocked.

## Troubleshoot setup issues

The following sections list typical issues with your general setup and suggest solutions.

### Quality inspections aren't created automatically

- Verify the trigger settings on the **Quality Management Setup** page.
- Double-check that you correctly configured your inspection generation rules.
- Ensure that templates are assigned to your inspection generation rules.

### Workflow events aren't available

- Check that users are assigned the appropriate permissions.
- Verify that the Quality Management extension is installed and enabled.

## Troubleshoot test generation rules

The following sections list typical issues with test generation rules and suggest solutions.

### No inspections are created

- Double-check your filter configuration.
- Verify your trigger settings.
- Confirm that you assigned the correct template.

### Too many inspections are created

- Look for rules that overlap.
- Make your filters more specific.
- Double-check the order of your rules.

### The wrong template is applied

- Verify the template assignment in the rule.
- Double-check your rule priority and order.
- Review your filter logic.

## Troubleshoot scheduled inspections

The following sections list typical problems with scheduled inspections and suggest solutions.

### The job queue entry isn't running

- Verify that the job queue service is running.
- Double-check the status of the job queue entry.
- Verify that users have the permissions they need.

### No inspections are created

- Verify the settings for your inspection generation rule.
- Double-check your item filters and availability.
- Review the filters and request-page parameters for report **20412** in the job queue entry.

### Too many inspections are created

- Adjust your sampling percentages.
- Refine your item filters.
- Review the selection logic.

## Troubleshoot quality management workflows

The following sections list typical issues with quality management workflows and suggest solutions.

### The workflow doesn't trigger

- Verify that your workflow is active.
- Review the event conditions.
- Confirm that users have the correct permissions.

### Incorrect actions are running

- Review your workflow conditions and logic.
- Check whether multiple workflows are conflicting.
- Verify your result code configuration.
- Review the order in which your workflow steps run.

### There are problems with performance

- Monitor how often your workflow runs.
- Review your settings for the related batch.
- Consider the timing of the automated actions.
- Evaluate the effect on your system resources.

### Workflow events for quality management aren't available

- Verify that the Quality Management extension is installed and enabled.
- Verify that your workflows are active.
- Confirm that your users have the correct permissions.

## Actions aren't running

- Review your workflow conditions.
- Review your settings for the journal batch.
- Verify that the values match your result code.

### I'm getting unexpected blocking behavior

- If you have multiple workflows, review their interactions.
- Check your result-based transaction controls.
- Verify your workflow priorities and sequence.

## Troubleshoot templates

The following sections list typical issues with quality inspection templates and suggest solutions.

### Tests aren't creating

- Verify that your test generation rules reference the template.
- Double-check that your template configuration is complete.
- Ensure that your field definitions are correct.

### My pass/fail results are incorrect

- Review your pass value ranges.
- Verify that your allowed value ranges include pass values.
- Double-check your field type configuration.

### There are problems with performance

- Minimize the number of complex fields.
- Optimize your field calculations.
- Consider whether you can simplify your template.

## Troubleshoot inspections

The following sections list typical issues with inspections and suggest solutions.

### No inspections are created

- Verify that the **Require Receive** toggle is turned on for the location.
- Double-check that the inspection generation rule applies to the item.
- Ensure that the warehouse receipt is posted.

### I'm getting the wrong number of inspections

- Review your item tracking configuration.
- Check for lot consolidation in the warehouse receipt.
- Verify the logic in your test generation rule.

### Inspections are missing lot information

- Confirm that you correctly configured item tracking.
- Check whether lot numbers transfer to warehouse documents.
- Verify that your item tracking code is set up.

## Troubleshoot warehouse receipt inspections

The following sections list typical issues with warehouse receipt inspections and suggest solutions.

### Inspections aren't created automatically

- Verify that you correctly configured your inspection generation rule.
- Double-check that your item filter matches the purchased item.
- Ensure that you set up the **Warehouse Receipt Trigger** correctly.
- Confirm that the template is assigned to the rule.

### Inspections are created for the wrong items

- Review the item filters in your inspection generation rules.
- Check whether rules overlap.
- Verify your rule priority and ordering.

### Inspections are missing data

- Confirm that you correctly configured item tracking.
- Verify that lot numbers are assigned before posting.
- Check the bin assignments, if the location requires bins.

## Troubleshoot production output inspections

The following sections list typical issues with production output inspections and suggest solutions.

### Inspections aren't being created

- Verify that the **Production Order Trigger** field is set to **When Production Output is posted**.
- Double-check your inspection generation rule filters.
- Ensure that the correct template is assigned.
- Confirm that output is posted.

## Troubleshoot manual inspection creation

The following sections list typical issues when you manually create inspections and suggest solutions.

### The Create Quality Inspection action isn't available

- Configure manual-enabled inspection generation rules.
- Verify your template assignments.
- Verify that you assigned the right permissions to your users.

### I'm missing template options

- Verify that you have templates and that they're properly configured.
- Double-check your inspection generation rule filters.
- Ensure that you filled in the required fields on your templates.

### I'm having problems with item selection

- Confirm that the item exists and is properly configured for quality management.
- Check whether your item tracking setup uses lot or serial numbers.
- Verify your item permissions.

### I'm missing source document details in my inspection information

- Create the inspection from the appropriate source document.
- Manually enter source information, if needed.
- Verify the document posting status.

### I'm having issues related to item tracking

- Confirm that you have lot or serial numbers.
- Double-check your item tracking code configuration.
- Verify the quantity allocations.

## Troubleshoot lot blocking

This section lists some typical issues with blocking lots and describes how to get unblocked.

### A quality inspection blocks a transaction

When a supported transaction is blocked by a quality inspection, the error identifies the responsible inspection. Select **Show Quality Inspection** in the error to open it. Review or complete the inspection, and then try the transaction again.

If the inspection result should allow the transaction, review the transaction controls for that result. Also check whether another matching inspection still blocks the item tracking number.

### My workflow doesn't start

- The workflow isn't active. Activate the workflow.
- There's an incorrect event or condition in your workflow configuration. Review the settings in your workflow.

### I get unexpected blocking behavior

There might be a problem with your result control:

- Review your result configuration for transaction types.
- Check your inspection result assignments.
- Verify your result inheritance rules.

There might be conflicts with your workflow:

- Check whether multiple workflows conflict.
- Review workflow priorities.
- Consider disabling conflicting workflows.

### My lots aren't unblocked

The pass result might cause problems:

- Verify that the inspection passes.
- Check your workflow conditions for unblocking.
- Review your result transition rules.

You might need to manually intervene:

- Manually unblock lots on the **Lot No. Information Card** page.
- Review and correct your workflow configuration.
- Consider using result-based controls instead.

## Troubleshoot quality inspection results

The following sections list typical problems with quality inspection results and suggest solutions.

### Inspections don't calculate the expected results

- Review result condition syntax.
- Check the order of priority.
- Verify the condition inheritance from fields to the template.

### Results aren't available in inspection templates

- Check the **Copy Behavior** field on the quality inspection result.
- To make the result available automatically, set **Copy Behavior** to **Automatically copy the result**. If it's set to **Do not automatically copy**, add the result to the template manually.
- Manually add the result to the template, if needed.

### My workflow doesn't start

- Confirm that the workflow condition matches the result code.
- Check the result code spelling and case sensitivity.
- Review the workflow activation status.

## Related information

[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Create an inspection manually from item tracking](qms-purchase-receipt-testing-simple.md)  
[Create a sampled inspection automatically from production output](qms-production-output-testing.md)  
[Work with quality inspections](qms-manual-test-creation.md)  
[Quality Management Overview](qms-overview.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]