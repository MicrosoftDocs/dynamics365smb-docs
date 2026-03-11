---
title: Handle items that failed a quality test
description: Learn how to handle noncompliant items, including workflows, inventory movements, and actions for failed quality inspections.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 20408,
ms.date: 03/11/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Process items that failed a quality inspection

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

This article explains how to deal with items that don't pass quality inspection. When goods fail a quality inspection, there are options to manually or automatically handle the noncompliant items:

- Block items to prevent the use of failed lots.
- Move items to quarantine areas.
- Remove unusable inventory.
- Transfer items to different locations.
- Return defective items to suppliers.

<!--## Prerequisites

- Quality inspection templates with pass and fail criteria.
- Inspection generation rules.
- Quality management workflows to automatically process failures and passes.
- Locations and bins for quarantine.-->

## Automatic processing when items fail an inspection

### Workflow-based actions

Quality Management workflows can automatically respond to failed inspection. The following automatic responses are available:

- Block the lot in the inspection
- Create negative adjustment
- Create transfer order
- Move inventory to different bin
- Create purchase return
- Create reinspection
- Send notifications

### Set up automatic blocking when inspections fail

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Workflows**, and then choose the related link.
1. Create a new workflow. For example, name it "Block Lot on Failure."
1. In the **Category** field, choose **Quality Examples**.
1. Configure the **When Event** as follows:
   - **Event**: When a Quality Inspection is Finished
   - **Condition**: **Result Code** equals **FAIL**, or other failing result.
1. Configure the **Response** as follows:
   - **Response**: Block the lot in the inspection.
   - **Result**: Failed lots automatically get blocked from use
4. Specify result-specific conditions, as follows:
   - Create separate workflows for different failing results.
   - Use result priorities to determine appropriate responses.
   - Configure different actions based on the severity of the failure.

### Set up automatic inventory movement

1. Create a workflow. For example, name it something like **Move Failed Items to Quarantine**.
2. For the **When Event**, choose **Quality Inspection is Finished**.
3. For the **On Condition**, specify that **Result Code** is **FAIL**.  
4. For the **Then Response**, choose **Move inventory from inspection**.
5. Configure the options for the response. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## Manual processing when inspections fail

The following sections describe some actions you can take when an item fails an inspection.

### Use manual actions on quality inspections

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection**, and then choose the related link.
1. Open the failed inspection.
1. Use the options on the **Actions** menu to run actions directly from the inspection results. Learn more at [Manual movement process](#manual-movement-process).

### Step-by-step process using quality inspection actions

**Process Using Quality Inspection Actions**:

1. **Review Inspection Results**:
   - Go to the failed quality inspection.
   - Analyze the failure details and measurements.
   - Determine the appropriate action.

2. **Execute Action**:
   - Select the appropriate action from the **Actions** menu on the **Quality Inspection** page.
   - Review the prefilled information for accuracy.
   - Add more details as required. For example, a destination or reason code.
   - Run the action to create the necessary documents.

3. **Complete Processing**:
   - Process the created documents. For example, adjustments, transfers, or returns.
   - Update the physical inventory locations as needed.
   - Document the resolution and lessons learned.

4. **Verify Completion**:
   - Confirm that all actions are properly recorded.
   - Verify that inventory movements and adjustments are posted.
   - Update the test status if necessary for tracking

## Result-based controls for failed items

Quality Management uses result-based controls to automatically manage noncompliant items based on inspection results.

**Result-Based Business Rules**:

- Result priorities determine which controls take precedence.
- Higher priority results override lower priority results.
- Failed results typically restrict business transactions while allowing handling activities.
- Result conditions can automatically promote or demote based on business rules.

**Implementation**:

- Quality inspection templates assign results based on measurements.
- Result inheritance flows from Default → Field → Template → Test levels.
- Workflows can trigger more actions based on results.
- Transaction controls apply immediately when you assign a result.

## Moving items after inspection failures

The following sections describe how to set up a quality management workflow to automatically or manually move a defective inventory to quarantine.

### Automatic movement to quarantine

You can set up a quality management workflow that automatically moves items to your quarantine area if they fail an inspection. The movement physically separates the defective items from your good inventory.

Set up a quality management workflow, as follows:

1. **Response**: Move inventory to different bin.
2. **Bin Configuration**: Specify quarantine bin.
3. **Automatic Execution**: Movement occurs on test failure.

### Manual movement process

To manually move defective inventory, you can use the options on the **Actions** menu on the **Quality Inspection** page. This section describes the actions.

**Move Inventory**:

Run an inventory movement directly from the inspection results. The movement is prefilled with details about the failed lot, and maintains the connection between movement and quality failure.

- **Quantity Options**: Entire lot/serial/package, specific quantity, sample quantity, passed/failed quantity.
- **Movement Methods**: Reclassification journal or movement worksheet/internal movement.
- **Source Filters**: Optional location and bin filters to limit movement source.
- **Destination**: Specify a target location and bin for quarantine or disposal.
- **Posting Options**: Post immediately, or create entries for later processing.

**Create Internal Put-away**:

Create internal put-away documents for warehouse locations.

- **Quantity Options**: Entire lot/serial/package, specific quantity, sample quantity, passed/failed quantity.
- **Source Filters**: Optional location and bin filters.
- **Release Options**: Release immediately, create warehouse put-away, or keep open for review.
- **Usage**: Ideal for directed put-away and pick locations.

**Create Transfer Order**:

Generate a transfer orders that automatically includes failed lot information and links transfer to original quality test for tracking.

- Specify a destination location for further processing.

**Create Negative Adjustment**:

- Automatically fills in item, lot, and quantity information.

<!--**Change Item Tracking**:-->

- **Create Purchase Return Order**:

- Start vendor returns directly from the inspection results. The return contains purchase order and receipt details, and includes quality inspection failure information for vendor communication.

## Removing items from inventory

You can remove items from inventory automatically, or manually. The following sections describe how.

### Automatic removal

Set up a quality management workflow with the **Then Response** set to **Create negative adjustment**. This response does the following:

- Automatically removes failed inventory.
- Records the disposal in the item ledger.
- Updates inventory quantities.

The following are a few things to consider about your configuration:

- Ensure that you have a suitable posting setup.
- Consider the effect on cost.
- Maintain an audit trail.

### Manual removal process

The manual removal process involves using the **Create Negative Adjustment** option from the **Actions** menu on the **Quality Inspection** page.

The action decreases inventory quantity for disposal, destructive testing, or write-offs.

- **Quantity Options**:
  - Entire lot/serial/package quantity
  - Specific quantity with manual entry
  - Sample quantity (uses inspection sample size)
  - Passed quantity (samples that passed all measurements)
  - Failed quantity (samples with at least one failed measurement)
- **Source Filters**: Optional location and bin filters to limit adjustment source
- **Reason Codes**: Optional reason code for audit trail
- **Posting Behavior**: Create journal entries only or post immediately

The following steps give an overview of the manual removal process:

1. From the failed quality inspection, choose **Create Negative Adjustment** from the **Actions** menu.
2. **Select Quantity**: Choose the appropriate quantity method. For example, this selection is often **Failed Quantity** for noncompliant items.
3. **Add Reason**: Specify a reason code. For example, disposal, destructive inspections, damage, and so on.
4. **Configure Source**: Add location/bin filters if you need to limit the scope.
5. **Execute**: Create entries for review, or post immediately.
6. **Verify**: Confirm the inventory reduction and that cost accounting is correct.

## Return items to vendors

You can return items to vendors automatically, or manually. The following sections describe how.

### Automatic return processing

Set up a quality management workflow with the **Then Response** set to **Create purchase return**. This response does the following:

- **Automatic Execution**: Return order created on inspection failure.
- **Vendor Notification**: Include details about the quality failure.

### Manual return process

The manual return process involves using the **Create Purchase Return** option from the **Actions** menu on the **Quality Inspection** page.

The action creates purchase return orders for vendor-related defects.

- **Quantity Options**:
  - Entire lot/serial/package quantity
  - Specific quantity with manual entry
  - Sample quantity (uses inspection sample size)
  - Passed quantity (if partial return needed)
  - Failed quantity (most common for defects)
- **Return Reason**: Optional return reason code for vendor communication
- **Source Filters**: Optional location and bin filters
- **Credit Memo**: Optional vendor credit memo number field

The following steps give an overview of the manual return process:

1. **Document the failure**: Compile the inspection results and evidence from the quality inspection.
2. Choose **Create Purchase Return** from the **Actions** menu on the **Quality Inspection** page.
3. **Configure the return**:
   - Choose **Failed Quantity** for defective items.
   - Add a return reason code.
   - Include the vendor credit memo number, if it's available.
4. **Run the action**: Create a purchase return order with prefilled inspection information.
5. **Process the return**: Follow your standard return procedures with links to the quality documentation.
6. **Vendor communication**: Include details about the quality inspection failure in a return notification.

## Transfer items to other locations

This section describes how to manually transfer items to other locations.

### Manual transfer process

The manual transfer process involves using the **Create Transfer Order** option from the **Actions** menu on the **Quality Inspection** page:

The action transfers items to another location for external processing, lab analysis, or disposal.

- **Quantity Options**:
  - Entire lot/serial/package quantity
  - Specific quantity with manual entry
  - Sample quantity (uses inspection sample size)
  - Passed quantity (for approved items)
  - Failed quantity (for noncompliant items)
- **Source Filters**: Optional location and bin filters to limit transfer source
- **Destination**: Target location for transfer
- **Transfer Details**: Support for direct transfer or in-transit locations

The following steps give an overview of the manual transfer process:

1. **Use the action**: From the quality inspection, choose **Create Transfer Order** from the **Actions** menu on the **Quality Inspection** page.
2. **Select the quantity**: Choose the appropriate quantity method based on what you want to do.
3. **Configure the source**: Add location/bin filters if the inspection covers multiple locations.
4. **Set a destination**: Specify the target location. For example, an external lab, disposal facility, or rework center.
5. **Transfer options**: Choose a direct transfer, or specify in-transit location.
6. **Execute**: Create a transfer order with quality inspection tracking.

## Change item tracking information

This section describes how to manually update information about items. Updating item information involves using the **Change Item Tracking** option from the **Actions** menu on the **Quality Inspection** page.

The action updates item tracking information such as lot numbers, serial numbers, package numbers, or expiration dates.

- **Quantity Options**:
  - Entire lot/serial/package quantity
  - Specific quantity with manual entry
  - Sample quantity (uses inspection sample size)
  - Passed quantity (for approved samples)
  - Failed quantity (for noncompliant samples)
- **Tracking Changes**: Update the lot, serial, or package numbers, and the expiration date.
- **Source Filters**: Optional filters for locations and bins.
- **Posting Options**: Post immediately, or create journal entries for review.

The following steps give an overview of how to manually track items:

1. Use the **Change Item Tracking** option from the **Actions** menu on the **Quality Inspection** page.
2. Choose the appropriate quantity method for tracking updates.
3. Enter a new lot, serial, or package number, or a new expiration date.
4. To configure the source, add filters for locations or bins, if needed.
5. Create a reclassification journal with updated tracking information.
6. Post the journal to update the item tracking records.

<!--## Corrective Action Integration

### Root Cause Analysis

**Quality Failure Investigation**:

- Review test data and trends
- Identify process or supplier issues
- Document findings and recommendations

**Process Improvement**:

- Update specifications or procedures
- Enhance incoming inspection criteria
- Improve vendor quality agreements

### Preventive Actions

**Enhanced Testing**:

- Create more test generation rules
- Implement more comprehensive templates
- Increase sampling frequencies

**Supplier Development**:

- Work with vendors on quality improvement
- Provide feedback on failure patterns
- Establish quality agreements and scorecards

## Retesting Procedures

### Automatic Retest Creation

**Workflow Response**: Create retest
- New quality test generated after rework
- Same template and criteria applied
- Links to original failed test

### Manual Retest Process

**After Rework or Investigation**:

1. **Complete Corrective Action**: Address root cause
2. **Create New Test**: Use manual test creation
3. **Reference Original Test**: Maintain tracking
4. **Document Resolution**: Record corrective actions taken

## Example: Complete Process for Failed Items

### Scenario: Failed Purchase Receipt Test

1. **Test Failure**:
   - Purchase receipt quality test fails measurement criteria
   - Grade automatically set to "FAIL"

2. **Automatic Workflow Actions**:
   - Lot automatically blocked (prevents further use)
   - Inventory moved to quarantine bin
   - Notification sent to quality manager

3. **Investigation**:
   - Quality team reviews failure details
   - Root cause identified as vendor process issue
   - Decision made to return to vendor

4. **Action Taken**:
   - Purchase return order created
   - Vendor notified of quality issue
   - Items returned and credit processed

5. **Follow-up**:
   - Vendor corrective action requested
   - Enhanced inspection implemented temporarily
   - Process documented for future reference

## Monitoring and Reporting

### Quality Metrics

**Track Failure Rates**:

- Test failure percentages by vendor
- Failure trends by item or category
- Cost of quality issues

**Action Tracking**:

- Time to resolution
- Action method effectiveness
- Recurring quality issues

### Continuous Improvement

**Process Enhancement**:

- Regular review of failure patterns
- Update templates and criteria as needed
- Improve workflow automation

**Vendor Management**:

- Quality scorecards based on test results
- Vendor development programs
- Supplier quality agreements -->

## Related information

[Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)  
[Configuring Workflows](qms-quality-workflows.md)  
[Purchase Receipt Inspections without Warehouse Handling](qms-purchase-receipt-testing-simple.md)  
[Quality Management Overview](qms-overview.md)