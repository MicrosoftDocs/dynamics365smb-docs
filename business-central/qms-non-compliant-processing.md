---
title: Handle items that failed a quality test
description: Learn how to handle noncompliant items, including workflows, inventory movements, and actions for failed quality tests.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Process items that failed a quality test

This article explains how to deal with items that don't pass quality inspection tests. It covers automatic workflows and manual actions for blocking items, moving inventory, and deciding what to do with the items that failed a test.

When quality inspection tests fail, you have several automatic and manual options for handling noncompliant items:

- Block items to prevent the use of failed lots.
- Move items to quarantine areas.
- Remove unusable inventory from of the system.
- Transfer items to different locations.
- Send defective items back to your suppliers.

## Prerequisites

- You must have quality inspection templates with pass and fail criteria.
- You must set up test generation rules.
- You have set up and enabled quality management workflows to automatically process failures and passes.
- You must have locations and bins for quarantine.

## Automatic processing when items fail a test

### Workflow-based actions

Quality Management workflows can automatically respond to test failures. The following automatic responses are available:

- Block the lot in the test
- Create negative adjustment
- Create transfer order
- Move inventory to different bin
- Create purchase return
- Create retest
- Send notifications

### Set up automatic blocking when tests fail

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Workflows**, and then choose the related link.
1. Create a new workflow. For example, name it "Block Lot on Failure."
1. In the **Category** field, choose **Quality Examples**.
1. Configure the **When Event** as follows:
   - **Event**: When a Quality Inspection Test is Finished
   - **Condition**: Grade Code equals "FAIL" (or other failing grades)
1. Configure the **Response** as follows:
   - **Response**: Block the lot in the test
   - **Result**: Failed lots automatically get blocked from use
4. Specify grade-specific conditions, as follows:
   - Create separate workflows for different failing grades.
   - Use grade priorities to determine appropriate responses.
   - Configure different actions based on failure severity.

### Set up automatic inventory movement

1. Create a workflow. For example, name it "Move Failed Items to Quarantine."
2. For the **When Event**, choose **Quality Inspection Test is Finished**.
3. For the **Condition**, specify that Grade Code equals "FAIL."  
4. For the **Response**, choose **Move inventory to different bin**
5. For the **Configuration**, specify a quarantine bin code.

## Manual processing when tests fail

The following sections describe ways to manually process items when they fail a test.

### Immediate actions after a test failure

When a quality test fails, consider these immediate actions:

1. **Quarantine**: Physically separate the noncompliant items.
2. **Investigation**: Determine the root cause of the failure.
3. **Documentation**: Record details about the failure and the actions taken.
4. **Notification**: Inform the relevant stakeholders.

### Decide what to do with the failed items

This section describes some typical ways to handle items that failed a test.

Use the failed items as-is:

- The customer accepts with a concession.
- Offer a reduced price or a different application.
- Document that the deviation is approved.

Rework the failed items:

- Correct or repair the failed items.
- Retest the items after you complete the rework.
- Track the costs and time spent on the rework.

Return the defective items to the vendor:

- Record a vendor defect or specification issue.
- Use the purchase return process and report the results from the quality inspection test.
- Document the vendor quality issues.

Treat the items as scrap or disposal:

- Use this method when you can't rework the items. For example, when rework isn't economically feasible.
- Create negative adjustments using reports from the quality inspection test.
- Consider environmental disposal implications.
- Record the costs and reasons for the disposal.

### Use quality inspection test reports for manual actions

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Inspection Test**, and then choose the related link.
1. Open the failed test.
1. Use the **Actions** menu to access helpful reports and actions.
1. Run the actions directly from test results for proper record keeping

The following actions are available from the **Actions** menu on the **Quality Inspection Test** page:

- **Create Negative Adjustment** - Automatically fills in item, lot, and quantity information
- **Move Inventory**:
   - Run an inventory movement directly from test results. The movement is prefilled with details about the failed lot, and maintains the connection between movement and quality failure.
   - Specify the destination bin, such as quarantine, rework, or disposal.
- **Create Transfer Order**:
   - Generate a transfer orders that automatically includes failed lot information and links transfer to original quality test for tracking
   - Specify a destination location for further processing.
- **Create Purchase Return**:
   - Start vendor returns directly from test results. The return contains purchase order and receipt details, and includes quality test failure information for vendor communication.

The following are benefits of using test-based actions:

- Automatically get item, lot, and quantity details.
- Built-in tracking between actions and test failures.
- Reduced data entry errors.
- Consistent documentation and audit trail.
- Integration with quality workflow processes.

### Step-by-Step Process Using Quality Inspection Test Actions

**Process Using Quality Inspection Test Actions**:

1. **Review Test Results**:
   - Navigate to failed Quality Inspection Test
   - Analyze failure details and measurements
   - Determine appropriate action

2. **Execute Action**:
   - Select appropriate action from Quality Inspection Test Actions menu
   - Review pre-filled information for accuracy
   - Add additional details as required (destination, reason codes)
   - Execute the action to create necessary documents

3. **Complete Processing**:
   - Process created documents (adjustments, transfers, returns)
   - Update physical inventory locations as needed
   - Document resolution and lessons learned

4. **Verify Completion**:
   - Confirm all actions are properly recorded
   - Verify inventory movements and adjustments are posted
   - Update test status if required for tracking

## Grade-Based Controls for Failed Items

### Automatic Grade Assignment for Failed Tests

Quality Management uses grade-based controls to automatically manage non-compliant items based on test results:

**Grade-Based Business Rules**:

- Grade priorities determine which controls take precedence
- Higher priority grades override lower priority grades
- Failed grades typically restrict business transactions while allowing handling activities
- Grade conditions can automatically promote or demote based on business rules

**Implementation**:

- Test templates assign grades based on measurement results
- Grade inheritance flows from Default → Field → Template → Test levels
- Workflows can trigger additional actions based on grade assignment
- Transaction controls apply immediately when grade is assigned

## Moving Items After Test Failures

### Automatic Movement to Quarantine

**Workflow Configuration**:

1. **Response**: Move inventory to different bin
2. **Bin Configuration**: Specify quarantine bin
3. **Automatic Execution**: Movement occurs on test failure

**Business Process**:

- Failed items automatically moved to quarantine area
- Physical separation from good inventory
- Clear identification of problem items

### Manual Movement Process

**Using Quality Management Reports from Quality Inspection Test**:

**Move Inventory Report**:

- Access via Quality Inspection Test Actions menu
- **Purpose**: Move inventory between bins or locations for quarantine or handling
- **Quantity Options**: Entire lot/serial/package, specific quantity, sample quantity, passed/failed quantity
- **Movement Methods**: Reclassification journal or movement worksheet/internal movement
- **Source Filters**: Optional location and bin filters to limit movement source
- **Destination**: Specify target location and bin for quarantine or disposal
- **Posting Options**: Post immediately or create entries for later processing

**Create Internal Put-away Report**:

- Access via Quality Inspection Test Actions menu
- **Purpose**: Create internal put-away documents for warehouse locations
- **Quantity Options**: Entire lot/serial/package, specific quantity, sample quantity, passed/failed quantity
- **Source Filters**: Optional location and bin filters
- **Release Options**: Release immediately, create warehouse put-away, or keep open for review
- **Usage**: Ideal for directed put-away and pick locations

**Manual Movement Process**:

1. **Select Failed Test**: Navigate to Quality Inspection Test with failed results
2. **Choose Movement Report**: Select "Move Inventory" or "Create Internal Put-away" from Actions
3. **Configure Movement**: Specify destination (quarantine, rework, disposal areas)
4. **Execute**: Run report to create movement documents with proper tracking

## Removing Items from Inventory

### Automatic Removal

**Workflow Response**: Create negative adjustment
- Automatically removes failed inventory
- Records disposal in item ledger
- Updates inventory quantities

**Configuration Considerations**:

- Ensure proper posting setup
- Consider cost implications
- Maintain audit trail

### Manual Removal Process

**Using Create Negative Adjustment Report from Quality Inspection Test**:

**Report Features**:

- **Purpose**: Decrease inventory quantity for disposal, destructive testing, or write-offs
- **Quantity Options**: 
  - Entire lot/serial/package quantity
  - Specific quantity with manual entry
  - Sample quantity (uses test sample size)
  - Passed quantity (samples that passed all measurements)
  - Failed quantity (samples with at least one failed measurement)
- **Source Filters**: Optional location and bin filters to limit adjustment source
- **Reason Codes**: Optional reason code for audit trail
- **Posting Behavior**: Create journal entries only or post immediately

**Manual Removal Process**:

1. **Access Report**: From failed Quality Inspection Test, select "Create Negative Adjustment" from Actions
2. **Select Quantity**: Choose appropriate quantity method (often "Failed Quantity" for non-compliant items)
3. **Add Reason**: Specify reason code (disposal, destructive testing, damage, etc.)
4. **Configure Source**: Add location/bin filters if needed to limit scope
5. **Execute**: Choose to create entries for review or post immediately
6. **Verify**: Confirm inventory reduction and proper cost accounting

## Returning Items to Vendors

### Automatic Return Processing

**Workflow Configuration**:

- **Response**: Create purchase return
- **Automatic Execution**: Return order created on test failure
- **Vendor Notification**: Include quality failure details

### Manual Return Process

**Using Create Purchase Return Report from Quality Inspection Test**:

**Report Features**:

- **Purpose**: Create purchase return orders for vendor-related defects
- **Quantity Options**:
  - Entire lot/serial/package quantity
  - Specific quantity with manual entry
  - Sample quantity (uses test sample size)
  - Passed quantity (if partial return needed)
  - Failed quantity (most common for defects)
- **Return Reason**: Optional return reason code for vendor communication
- **Source Filters**: Optional location and bin filters
- **Credit Memo**: Optional vendor credit memo number field

**Manual Return Process**:

1. **Document Failure**: Compile test results and evidence from Quality Inspection Test
2. **Access Report**: Select "Create Purchase Return" from Quality Inspection Test Actions
3. **Configure Return**: 
   - Choose "Failed Quantity" for defective items
   - Add return reason code
   - Include vendor credit memo number if available
4. **Execute Report**: Create purchase return order with pre-filled test information
5. **Process Return**: Follow standard return procedures with linked quality documentation
6. **Vendor Communication**: Include quality test failure details in return notification

## Transferring Items to Other Locations

### Manual Transfer Process

**Using Create Transfer Order Report from Quality Inspection Test**:

**Report Features**:

- **Purpose**: Transfer items to another location for external processing, lab analysis, or disposal
- **Quantity Options**:
  - Entire lot/serial/package quantity
  - Specific quantity with manual entry
  - Sample quantity (uses test sample size)
  - Passed quantity (for approved items)
  - Failed quantity (for non-compliant items)
- **Source Filters**: Optional location and bin filters to limit transfer source
- **Destination**: Target location for transfer
- **Transfer Details**: Support for direct transfer or in-transit locations

**Manual Transfer Process**:

1. **Access Report**: From Quality Inspection Test, select "Create Transfer Order" from Actions
2. **Select Quantity**: Choose appropriate quantity method based on what you want to do
3. **Configure Source**: Add location/bin filters if test covers multiple locations
4. **Set Destination**: Specify target location (external lab, disposal facility, rework center)
5. **Transfer Options**: Choose direct transfer or specify in-transit location
6. **Execute**: Create transfer order with quality test tracking

## Changing Item Information

### Manual Item Information Updates

**Using Change Item Tracking Report from Quality Inspection Test**:

**Report Features**:

- **Purpose**: Update item tracking information such as lot numbers, serial numbers, package numbers, or expiration dates
- **Quantity Options**:
  - Entire lot/serial/package quantity
  - Specific quantity with manual entry
  - Sample quantity (uses test sample size)
  - Passed quantity (for approved samples)
  - Failed quantity (for non-compliant samples)
- **Tracking Changes**: Update lot no., serial no., package no., expiration date
- **Source Filters**: Optional location and bin filters
- **Posting Options**: Post immediately or create journal entries for review

**Manual Item Tracking Process**:

1. **Access Report**: From Quality Inspection Test, select "Change Item Tracking" from Actions
2. **Select Quantity**: Choose appropriate quantity method for tracking update
3. **Specify Changes**: Enter new lot number, serial number, package number, or expiration date
4. **Configure Source**: Add location/bin filters if needed
5. **Execute**: Create reclassification journal with updated tracking information
6. **Post Changes**: Process journal to update item tracking records

## Corrective Action Integration

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

- Create additional test generation rules
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
- Supplier quality agreements

## Related information

[Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)  
[Configuring Workflows](qms-quality-workflows.md)  
[Purchase Receipt Testing Without Warehouse Tracking](qms-purchase-receipt-testing-simple.md)  
[Quality Management Overview](qms-overview.md)