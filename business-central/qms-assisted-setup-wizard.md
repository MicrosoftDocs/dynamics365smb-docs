# Assisted Setup Wizard

## Overview

The Quality Management Setup Wizard is an assisted setup guide that helps users configure the Quality Management system in Business Central. This wizard walks users through the initial configuration required to perform quality inspections and sets up automatic test creation based on business scenarios.

## Running the Setup Wizard

### Starting the Wizard

1. Navigate to **Assisted Setup** in Business Central
2. Locate **Setup Quality Management** in the list
3. Click to start the wizard

## Wizard Steps

### Step 1: Welcome and Terms

Users must agree to the terms and conditions to proceed with the setup. This step introduces the wizard and explains it will guide you through the initial setup required to perform quality inspections.

### Step 2: Getting Started Data

Choose whether to apply demonstration and sample data:

**Apply Getting Started Data**: Downloads and applies basic setup data with useful examples and demonstration data. This helps you get running quickly or evaluate if the application fits your needs.

**Do Not Apply Configuration**: Skips sample data installation. Very basic setup data for common integration scenarios will still be applied.

**Recommendation**: The wizard automatically suggests "Do Not Apply" if the system appears already configured or used previously.

### Step 3: Permission Awareness

This informational step reminds administrators about permission requirements. You'll need to add the "Quality Inspection" permission set to users who will be making quality inspection tests.

### Step 4: Usage Scenarios

Determine where you plan to use Quality Inspection Tests:

**Production**: Create tests when recording production output. Most common scenarios are when inventory is posted from the output journal, but could also be for intermediate steps or other triggers.

**Receiving**: Create tests when receiving inventory from purchase orders, transfer orders, warehouse receipts, or sales returns.

**Something Else**: Use Quality Inspection to create manual tests for other areas in Business Central or configure manually later.

The wizard will skip irrelevant configuration steps based on your selections.

### Step 5: Production Test Configuration

*Only shown if production testing was selected*

Configure how production tests are created:

**Create tests automatically**: Tests are created automatically when output is recorded. Use this when tests must exist when production output occurs.

**Manual test creation**: A person manually creates tests by clicking a button. Use this when your process requires a person to create tests, or for ad-hoc testing scenarios like non-conformance reports or tracking re-work.

### Step 6: Receiving Test Configuration  

*Only shown if receiving testing was selected*

Configure automatic test creation for receiving scenarios:

- **Purchase Receipts**: Automatically create tests when receiving via purchase orders
- **Transfer Receipts**: Automatically create tests when receiving via transfer orders
- **Warehouse Receipts**: Automatically create tests when receiving via warehouse receipts
- **Sales Return Receipts**: Automatically create tests when receiving via sales returns

**Manual only option**: Choose this if you only want people to manually create tests by clicking a button, useful for ad-hoc testing or tracking damage for received goods.

### Step 7: Test Display Behavior

*Content varies based on whether automatic test creation was configured*

Configure when tests should be displayed to users:

**Show automatic and manually created tests**: Tests appear immediately when created. Use this when the person doing the activity (like posting) is also the person collecting test results.

**Show only manually created tests**: Tests created automatically don't show immediately, but manually created tests do. Use this when different people handle posting versus data collection.

**Never show immediately**: Tests are always created in the background. Use this when the person creating tests should not be editing them, ensuring complete separation of test creation and completion.

**Business Consideration**: Activities that trigger tests without direct interaction (background posting, web service integrations like Power Automate) will create tests but won't immediately show them regardless of this setting.

### Step 8: Completion

The wizard finalizes all configuration choices, applies them to the setup record, marks the assisted setup as complete, and enables Quality Management features.

## Configuration Results

The wizard configures the "Qlty. Management Setup" table based on your choices:

### Production Settings
- Manual tests disable the production trigger
- Automatic tests enable the trigger on production output posting

### Receiving Settings
- Each receiving type (purchase, transfer, warehouse, sales return) can be individually enabled or disabled
- Manual-only option disables all automatic triggers

### Display Behavior
- Controls when tests automatically appear to users
- Aligns with business roles and workflow separation

### System Activation
- Sets visibility to "Show" to enable Quality Management features
- Refreshes experience tier settings for the current company

## Technical Integration

The wizard integrates with several Business Central systems:

**Guided Experience**: Tracks setup completion status and prevents re-running unnecessarily.

**Application Area Management**: Updates feature visibility and user experience settings.

**Telemetry**: Logs completion events including environment name, company, and user for monitoring and support.

**Auto Configuration**: Handles basic setup requirements and sample data deployment through configuration packages.

## Best Practices

### For Administrators
1. Assign "Quality Inspection" permission sets before running the wizard
2. Consider your business processes when choosing automatic versus manual test creation
3. Align display behavior with organizational roles - separate posting from inspection duties when appropriate

### For Implementation
1. Test the wizard in a sandbox environment first to validate configuration choices
2. Document your selected settings for future reference and training
3. Plan user training based on the resulting test creation and display behaviors

### Common Scenarios

**Manufacturing Focus**: Enable production testing with appropriate display behavior for your workflow separation needs.

**Distribution Focus**: Enable receiving testing for relevant document types (typically purchase receipts).

**Comprehensive Quality**: Enable both production and receiving with "show only manual" to maintain workflow separation.

**Evaluation/Demo**: Enable all features with immediate display for training and demonstration purposes.

## Troubleshooting

**Insufficient Permissions**: The wizard checks for adequate permissions and will display an error message guiding users to request additional permissions from their administrator.

**Previous Configuration**: The wizard detects existing configuration and preserves previous settings while allowing updates.

**Getting Started Data**: Sample data installation only occurs if selected and the system isn't already configured, preventing duplicate or conflicting data.
