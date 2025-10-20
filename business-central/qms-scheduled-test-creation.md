# Scheduled Test Creation

This guide explains how to set up and use scheduled quality inspection tests that are created automatically at regular intervals using Business Central job queues.

## Overview

Scheduled test creation enables proactive quality management by automatically generating quality inspection tests based on time intervals rather than business transactions. This capability is ideal for:

- **Routine Inspections**: Regular sampling of inventory in stock
- **Shelf Life Monitoring**: Periodic testing of items approaching expiration
- **Environmental Compliance**: Time-based testing requirements
- **Statistical Quality Control**: Systematic sampling programs
- **Preventive Quality Assurance**: Proactive testing schedules

## Prerequisites

- Quality inspection templates configured
- Job queue functionality enabled in Business Central
- Test generation rules configured for scheduled creation
- Items available for scheduled testing
- Appropriate user permissions for job queue management

## Understanding Scheduled Testing

### Scheduled vs. Transaction-Based Testing

| Feature | Transaction-Based | Scheduled |
|---------|------------------|-----------|
| Trigger | Business transactions (receipts, output) | Time intervals |
| Frequency | Event-driven | Regular intervals |
| Purpose | Process validation | Proactive monitoring |
| Coverage | All processed items | Sampled items |
| Resource Planning | Reactive | Predictable |

### Business Applications

**Routine Inventory Sampling**:
- Random testing of items in stock
- Verification of storage conditions
- Quality drift monitoring

**Compliance Testing**:
- Regulatory requirement fulfillment
- Industry standard compliance
- Customer audit preparation

**Preventive Quality Control**:
- Early detection of quality issues
- Trend analysis and monitoring
- Continuous improvement data collection

## Setting Up Scheduled Tests

### Step 1: Configure Quality Templates

Create templates specifically for scheduled testing:

1. Navigate to **Quality Inspection Templates**
2. Create template for scheduled inspections
3. Configure measurements appropriate for routine testing
4. Set pass/fail criteria for ongoing monitoring

**Example Template: "ROUTINE-INSPECTION"**
- Simplified measurement set for efficiency
- Focus on critical quality parameters
- Streamlined for regular execution

### Step 2: Create Scheduled Test Generation Rules and Set Up Job Queue Entry

Configure rules specifically for time-based test creation:

1. Navigate to **Test Generation Rules**
2. Create new rule for scheduled testing
3. Drill down the **Schedule Group** field.
4. You'll first be prompted to create a job queue, followed by an option to view it.

### Step 4: Configure Job Queue Parameters

Set up execution parameters:

**Frequency Settings**:
- **Starting Date/Time**: When to begin scheduled testing
- **Ending Date/Time**: When to stop (optional)
- **Run on Mondays/Tuesday/etc.**: Day-specific scheduling
- **Starting Time**: Time of day for execution

**Execution Parameters**:
- **Maximum No. of Attempts**: Retry logic for failures
- **Rerun Delay**: Wait time between retry attempts
- **Status**: Set to Ready to enable execution

## Troubleshooting Scheduled Tests

### Common Issues

**Job Queue Not Executing**:
- Verify job queue service is running
- Check job queue entry status
- Review user permissions

**No Tests Created**:
- Verify test generation rule configuration
- Check item filters and availability
- Review codeunit parameters

**Too Many Tests Created**:
- Adjust sampling percentages
- Refine item filters
- Review selection logic

### Monitoring and Alerts

**Automated Monitoring**:
- Set up alerts for job queue failures
- Monitor test creation volumes
- Track completion rates

**Quality Metrics**:
- Measure scheduled test effectiveness
- Track quality trend improvements
- Calculate return on investment

## Best Practices

### Scheduling Strategy

**Balanced Approach**:
- Combine scheduled and transaction-based testing
- Focus scheduled tests on high-risk areas
- Maintain statistical validity

**Resource Planning**:
- Plan quality inspector capacity
- Coordinate with operational schedules
- Balance proactive vs. reactive testing

### Continuous Improvement

**Regular Review**:
- Evaluate scheduled test effectiveness
- Adjust frequencies based on findings
- Optimize resource allocation

**Data-Driven Decisions**:
- Use scheduled test data for process improvement
- Identify quality trends and patterns
- Support vendor quality discussions

## See Also

- [Manual Test Creation](2.4-manual-test-creation.md)
- [Creating Quality Inspection Templates](1.4-quality-templates.md)
- [Setting Up Test Generation Rules](1.5-test-generation-rules.md)
- [Quality Management Setup and Configuration](1.1-quality-management-setup.md)
- [Quality Management Overview](0.0-Quality-Management-Overview.md)