# Creating Quality Inspection Templates

Quality inspection templates define the collection of measurements and attributes you want to collect during quality testing. Templates serve as the foundation for all quality tests in the system.

## Overview

A quality inspection template contains:
- **Template Code**: Unique identifier for the template
- **Description**: Descriptive name for the template
- **Fields/Measurements**: Individual quality measurements to collect
- **Pass/Fail Criteria**: Acceptable ranges for each measurement

## Creating a New Template

### Step 1: Create the Template Header

1. Navigate to **Quality Inspection Templates**
2. Click **New** to create a new template
3. Enter a **Template Code** (e.g., "EXAMPLE", "INCOMING-PARTS")
4. Enter a **Description** (e.g., "Example Template", "Incoming Parts Inspection")

### Step 2: Add Fields and Measurements

For each quality measurement you want to collect:

1. Click **Add Field(s) to this template** 
2. Configure the field properties:
   - **Description**: Name of the measurement (e.g., "Example Measurement", "Weight", "Dimension")
   - **Allowable Values**: Range of values that can be entered
   - **Default Value**: Default value to set on a test
   - **Pass Values**: Range of values that constitute a passing result

### Field Configuration Example

**Example Measurement Field**:
- **Description**: "Example Measurement"
- **Allowed Values**: 5 to 90 (system will accept any value in this range)
- **Pass Values**: 10..20 - values between 10 and 20 result in "Pass" grade

**Result Behavior**:
- No value entered: "In Progress" grade (default)
- Values 5-9: "Fail" grade (outside pass range but within allowed values)
- Values 10-20: "Pass" grade (meets pass criteria)  
- Values 21-90: "Fail" grade (outside pass range but within allowed values)
- Values outside 5-90: System will reject entry (outside allowed values)


## Template Design Best Practices

### Measurement Selection
- Include only essential quality characteristics
- Focus on critical-to-quality parameters
- Consider measurement time and complexity

### Template Organization
- Create specific templates for different inspection types
- Group related measurements together
- Use descriptive field names
- Document any template-specific grade overrides

## Common Template Scenarios

### Incoming Material Inspection
**Use Case**: Inspecting purchased materials
**Example Fields**:
- Dimension measurements
- Visual appearance checks
- Material compliance verification

### Production Output Inspection
**Use Case**: Testing finished goods
**Example Fields**:
- Functional performance tests
- Assembly quality checks
- Final dimension verification

### In-Process Inspection
**Use Case**: Quality checks during production
**Example Fields**:
- Intermediate measurements
- Process parameter verification
- Work-in-progress quality gates

## Managing Templates

### Copying Templates
Create new templates based on existing ones:
1. Select existing template
2. Use copy function to duplicate
3. Modify fields as needed for new application

### Template Activation
- Templates must be properly configured before use
- Test generation rules reference specific templates
- Verify template functionality before production use

## Integration with Test Generation Rules

Templates connect to automated test creation through test generation rules:

1. **Template Assignment**: Each test generation rule references a specific template
2. **Automatic Application**: When rules trigger, the associated template creates the test structure
3. **Data Collection**: Test users fill in the template fields during inspection


## Troubleshooting Templates

### Tests Not Creating
- Verify template is referenced in test generation rules
- Check template configuration is complete
- Ensure proper field definitions

### Incorrect Pass/Fail Results
- Review pass value ranges
- Verify allowed value ranges include pass values
- Check field type configuration

### Performance Issues
- Minimize number of complex fields
- Optimize field calculations
- Consider template simplification

## See Also

- [Configuring Quality Inspection Grades](1.3-configuring-grades.md)
- [Setting Up Test Generation Rules](1.5-test-generation-rules.md)
- [Manual Test Creation](2.4-manual-test-creation.md)
- [Quality Management Setup and Configuration](1.1-quality-management-setup.md)
- [Quality Management Overview](0.0-Quality-Management-Overview.md)