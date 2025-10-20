# Non-Compliant Processing

This guide explains how to deal with items that don't pass quality inspection tests, including automatic workflows and manual actions for blocking items, moving inventory, and deciding what to do with failed items.

## Overview

When quality inspection tests fail, Quality Management provides several automatic and manual options for handling non-compliant items:

- **Block Items**: Prevent use of failed lots
- **Move Items**: Relocate items to quarantine areas
- **Remove from Inventory**: Take unusable inventory out of the system
- **Transfer Items**: Move items to different locations
- **Return to Vendor**: Send defective items back to suppliers

## Prerequisites

- Quality inspection templates with pass/fail criteria
- Test generation rules set up
- Workflows enabled (for automatic processing)
- Appropriate locations and bins for quarantine

## Automatic Processing When Tests Fail

### Workflow-Based Actions

Quality Management workflows can automatically respond to test failures:

**Available Automatic Responses**:
- Block the lot in the test
- Create negative adjustment
- Create transfer order
- Move inventory to different bin
- Create purchase return
- Create retest
- Send notifications

### Setting Up Automatic Blocking When Tests Fail

1. **Create Blocking Workflow**:
   - Navigate to **Workflows**
   - Create new workflow: "Block Lot on Failure"
   - **Category**: Quality Examples

2. **Configure When Event**:
   - **Event**: When a Quality Inspection Test is Finished
   - **Condition**: Grade Code equals "FAIL" (or other failing grades)

3. **Configure Response**:
   - **Response**: Block the lot in the test
   - **Result**: Failed lots automatically get blocked from use

4. **Grade-Specific Conditions**:
   - Create separate workflows for different failing grades
   - Use grade priorities to determine appropriate responses
   - Configure different actions based on failure severity

### Setting Up Automatic Inventory Movement

1. **Create Workflow**: "Move Failed Items to Quarantine"
2. **When Event**: Quality Inspection Test is Finished
3. **Condition**: Grade Code equals "FAIL"  
4. **Response**: Move inventory to different bin
5. **Configuration**: Specify quarantine bin code

## Manual Processing When Tests Fail

### Immediate Actions After Test Failure

When a quality test fails, consider these immediate actions:

1. **Quarantine**: Physically separate non-compliant items
2. **Investigation**: Determine root cause of failure
3. **Documentation**: Record failure details and actions taken
4. **Notification**: Inform relevant stakeholders

### Deciding What to Do With Failed Items

**Common Options**:

**Use As-Is**: 
- Customer accepts with concession
- Reduced price or different application
- Document deviation approval

**Rework**:
- Items can be corrected or repaired
- Retest after rework completion
- Track rework costs and time

**Return to Vendor**:
- Vendor defect or specification issue
- Use purchase return process with reports from Quality Inspection Test
- Document vendor quality issues

**Scrap/Disposal**:
- Items cannot be corrected economically
- Create negative adjustments using reports from Quality Inspection Test
- Environmental disposal considerations
- Record disposal costs and reasons

### Using Quality Inspection Test Reports for Manual Actions

**How to Access Actions**:
- Navigate to **Quality Inspection Test** page for the failed test
- Use **Actions** menu to access helpful reports and functions
- Execute actions directly from test results for proper record keeping

**Available Actions from Quality Inspection Test**:

**Create Negative Adjustment**:
- Access via Quality Inspection Test Actions menu
- Automatically fills in item, lot, and quantity information

**Move Inventory**:
- Execute inventory movement directly from test results
- Pre-filled with failed lot details
- Specify destination bin (quarantine, rework, disposal areas)
- Maintains connection between movement and quality failure

**Create Transfer Order**:
- Generate transfer orders from Quality Inspection Test actions
- Automatically includes failed lot information
- Specify destination location for further processing
- Links transfer to original quality test for tracking

**Create Purchase Return**:
- Start vendor returns directly from test results
- Pre-fills purchase order and receipt details
- Includes quality test failure information for vendor communication
- Streamlines return process with proper documentation

**Benefits of Using Test-Based Actions**:
- Automatic filling of item, lot, and quantity details
- Built-in tracking between actions and test failures
- Reduced data entry errors
- Consistent documentation and audit trail
- Integration with quality workflow processes

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

## See Also

- [Lot Blocking and Unblocking](3.1-lot-blocking-unblocking.md)
- [Configuring Workflows](1.6-quality-workflows.md)
- [Inventory Movement Between Bins](./inventory-movement-bins.md)
- [Purchase Receipt Testing Without Warehouse Tracking](2.1-purchase-receipt-testing-simple.md)
- [Quality Management Overview](0.0-Quality-Management-Overview.md)