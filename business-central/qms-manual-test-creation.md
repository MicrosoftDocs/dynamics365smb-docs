---
title: Work with quality inspections
description: Learn how to create, assign, complete, print, reopen, and repeat quality inspections in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20406, 20407, 20408
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Work with quality inspections

Quality inspections collect measurements and observations for items, documents, and business processes. This article explains how to create an inspection, perform the tests, finish and print the inspection, and create a reinspection when more testing is needed.

## Before you create an inspection

You need a quality inspection template and an enabled inspection generation rule. The rule connects the template to a source, such as a purchase line or production order routing line. It also defines whether inspections can be created manually, automatically, or both. For more information, see [Create quality inspection templates](qms-quality-templates.md) and [Set up quality inspection generation rules](qms-test-generation-rules.md).

Users who perform inspections need the **Quality Inspector** permission set. Users who configure quality management or manage other users' inspections need the **Quality Admin & Supervisor** permission set.

Automatic creation also requires the user who runs the source transaction to have effective access to the quality management integration objects. Transaction posting permission alone doesn't guarantee that an inspection is created. The **Quality Inspection - Create** permission set provides the minimum quality management integration permissions. Depending on the user's license and assigned permission sets, this access might already be included.

## Create an inspection

You can create inspections from a template, from source records, through automatic triggers, through a workflow, or on a schedule.

### Create an inspection from a template

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Templates**, and then select the related link.
2. Choose the template, and then select **Create Inspection**.
3. In the **Source** field, choose the type of record to inspect.
4. In the **Choose Record** field, choose the record. The lookup applies the table filter configured for the source.
5. Enter item, lot, serial, package, and source quantity information as needed, and then choose **OK**.

The inspection uses the selected template and retains a link to the source record.

### Create inspections from source records

Source pages offer actions when a matching generation rule allows manual creation. Depending on the source, you can create inspections from purchase, purchase return, sales, and sales return lines; production routing lines; output and consumption journals; warehouse entries; and item-tracking lines.

For example, on a purchase order line, select **Quality Management**, and then select **Create Quality Inspection**. The action creates an inspection for the current line. The same menu provides **Show Quality Inspections for Item and Document** and **Show Quality Inspections for Item** options.

On the **Item Tracking Lines** page, select one or more tracking lines, choose **Quality Management**, and then choose **Create Quality Inspections**. [!INCLUDE [prod_short](includes/prod_short.md)] creates an inspection for each selected tracking line that matches a rule. Use **Show Quality Inspections for Item with Tracking Specification** to review related inspections.

### Create inspections automatically, through workflows, or on a schedule

Automatic triggers on generation rules can create inspections when you release or post source documents. Examples include purchase and transfer receipts, warehouse receipts, production and assembly output, sales returns, and registered warehouse movements.

To learn more about automatic triggers and rule configuration, go to [Set up quality inspection generation rules](qms-test-generation-rules.md).

Workflows can create inspections in response to workflow events. Learn more in [Quality management workflows](qms-quality-workflows.md).

For periodic inspections, assign a **Schedule Group** to one or more rules and configure the job queue entry that [!INCLUDE [prod_short](includes/prod_short.md)] creates. Learn more in [Create scheduled quality inspections](qms-scheduled-test-creation.md).

## How generation rules are selected for source actions and automatic triggers

When you create an inspection from a source record or use an automatic trigger, [!INCLUDE [prod_short](includes/prod_short.md)] evaluates enabled generation rules in ascending **Sort Order**. It checks the source table and condition filter, followed by item and attribute filters when an item is available. The first matching rule supplies the template for that creation attempt. Other matching rules aren't used.

Use lower sort-order values for specific rules and higher values for general fallback rules. Avoid overlapping rules unless the priority is intentional.

For source actions and automatic triggers, the **Activation Trigger** field controls how a rule can be used:

- **Manual or Automatic** allows both creation methods.
- **Manual only** allows actions that users run.
- **Automatic only** allows configured automatic triggers.
- **Disabled** prevents the rule from creating inspections.

Scheduled processing is an exception. A schedule can process any rule that isn't **Disabled**, regardless of whether the rule is manual or automatic.

## Assign and perform an inspection

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspections**, and then select the related link.
2. On the **Quality Inspections** list, choose an unassigned inspection, and then choose **Take ownership**. To return an inspection assigned to you to the unassigned state, choose **Unassign**.
3. Open the inspection.
4. Review the source, item, quantity, and item-tracking information.
5. Enter a **Test Value** for each test that requires input. [!INCLUDE [prod_short](includes/prod_short.md)] evaluates line results and dependent expressions as values change.
6. Add a **Note** to a test line when more explanation is needed.
7. Use **Attachments** to add supporting documents. In the picture FactBox, use **Take** or **Import** to add a picture of the inspected item.
8. Review the inspection result.

The **Quality Admin & Supervisor** permission set is required to change another user's assignment, change quantity fields, reopen a finished inspection, or delete a finished inspection.

## Finish an inspection

Choose **Finish** when testing is complete. For a tracked item, [!INCLUDE [prod_short](includes/prod_short.md)] verifies the lot, serial, or package information according to the **Item Tracking Before Finishing** setting. It also verifies that the inspection result allows finishing. To learn more about the item-tracking options, go to [Quality management setup and configuration](qms-setup.md#set-up-quality-management).

Finishing records the user and date and prevents normal editing of the inspection and its lines.

The result category determines how quantities are updated:

- **Acceptable** enters the inspected quantity in **Passed Quantity**.
- **Not acceptable** or a blank category enters the inspected quantity in **Failed Quantity**.

The inspected quantity is the **Sample Size** when that value is greater than zero. Otherwise, [!INCLUDE [prod_short](includes/prod_short.md)] uses **Quantity (Base)**.

## Print inspection reports

Use the **Report** menu on an inspection to print one of the following reports:

| Report | Purpose |
| --- | --- |
| **Certificate of Analysis** | Certifies test values and results for a customer, lot, or batch. |
| **Inspection Report** | Provides a general record of the inspection, tests, values, results, notes, and source information. |
| **Non Conformance Report** | Documents test results and source information for an inspection that didn't meet requirements. |

You can filter each report by **Source Item No.**, **Source Variant Code**, **Source Lot No.**, **Source Serial No.**, **Source Package No.**, **Source Document No.**, inspection number, reinspection number, **Template Code**, and **Test Code**. The reports use Word layouts that you can customize. For more information, see [Manage report and document layouts](ui-manage-report-layouts.md).

## Reopen an inspection

A user with the **Quality Admin & Supervisor** permission set can choose **Reopen** on a finished inspection when it doesn't have a later reinspection. Reopening makes the inspection editable and clears the calculated passed and failed quantities. It keeps the result, test values, finishing information, notes, and pictures. Finish the inspection again after making the required changes.

## Create a reinspection

Choose the **Create Re-inspection** action when you need a new inspection in the same sequence. If the current inspection is open, [!INCLUDE [prod_short](includes/prod_short.md)] finishes it first and applies the normal finish checks.

The reinspection is a new open revision. It keeps the inspection number and gets the next **Re-inspection No.** It copies source, item, quantity, assignment, and other header information. Test lines are rebuilt from the current template, and entered test values aren't copied.

If inspection results control whether tracked inventory can be used, review the **Quality Inspection Selection Criteria** setting. **Only the newest inspection/reinspection** lets the newest inspection in the sequence determine the restriction.

## Handle items that don't pass inspection

From a failed inspection, you can move inventory, create an internal put-away or transfer order, make a negative adjustment, change item tracking, or create a purchase return order. Workflows can also perform actions when an inspection is created or finished. Learn more in [Process items that failed a quality inspection](qms-non-compliant-processing.md) and [Block or unblock lots](qms-lot-blocking-unblocking.md).

## Related information

[Quality management overview](qms-overview.md)  
[Quality management setup and configuration](qms-setup.md)  
[Configure quality inspection results](qms-configuring-grades.md)  
[Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]