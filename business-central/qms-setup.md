---
title: Quality management setup and configuration 
description: Learn how to set up and configure quality management features, including prerequisites, initial setup steps, and common scenarios.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Quality management setup and configuration

This article takes you through the initial setup and configuration of quality management features.

## Prerequisites

Before setting up Quality Management, ensure you have:

- Microsoft Dynamics 365 Business Central
- Quality Management app installed
- Administrative permissions in Business Central
- Understanding of your quality control requirements

## Initial Setup Steps

### 1. Run the Assisted Setup Wizard

The Quality Management app includes an assisted setup wizard to help configure basic settings:

1. Navigate to **Assisted Setup**
2. Find and run **Set up Quality Management**
3. Follow the wizard steps (see [Assisted Setup Wizard](1.2-assisted-setup-wizard.md) for details)

### 2. Configure Base Data

Ensure you have the following base data configured in Business Central:

#### Locations

- Configure locations where quality testing will occur
- Set up warehouse handling if required (receipts, put-aways, etc.)
- Define bins for quality testing areas

#### Items

- Configure item tracking codes for lots, serials, or packages as needed
- Set up lot number series for automatic lot assignment
- Ensure items have appropriate inventory posting groups

#### Vendors and Customers

- Configure vendors for purchase receipt testing
- Set up customers if quality testing affects sales processes

### 3. Quality Management Setup

Navigate to **Quality Management Setup** to configure global settings:

#### General Settings

**Quality Inspection Nos.**: The default number series used for quality inspection documents when there is not a no. series defined on a Quality Inspection Template. When a no. series is defined on a template, that takes precedence.

**Create Test Behavior**: Dictates the behavior of when to create a new Quality Inspection Test when existing tests occur.

- *Always create new test*: Creates a new test every time
- *Create retest if matching test is finished*: Creates a retest only if an existing matching test has been completed
- *Always create retest*: Always creates a retest when tests already exist
- *Use existing open test if available*: Reuses an existing open test if one exists
- *Use any existing test if available*: Reuses any existing test regardless of status

**Find Existing Behavior**: What criteria the system looks for when searching for existing tests.

- *By Standard Source Fields*: Uses standard source fields to find existing tests
- *By Source Record*: Finds tests based on the source record
- *By Item Tracking*: Uses item tracking information (lot/serial numbers)
- *By Document and Item only*: Searches only by document and item, ignoring other criteria

**Conditional Lot Find Behavior**: Which test(s) are considered when evaluating if a document-specific transaction is blocked.

- *Any test that matches*: Considers any test
- *Only the most recently modified test*: Uses the most recently modified test
- *Only the newest test/re-test*: Uses the test with the highest retest number
- *Any finished test that matches*: Considers any finished test
- *Only the most recently modified finished test*: Uses the most recently modified finished test
- *Only the newest finished test/re-test*: Uses the finished test with the highest retest number

**COA Contact No.**: Contact details that will appear on the Certificate of Analysis report when supplied.

**Maximum Rows To Fetch on Field Lookups**: The maximum number of rows to fetch on data lookups. Keeping the number as low as possible will increase usability and performance.

**Show Test Behavior**: Whether to show the Quality Inspection Test page after a test has been made.

- *Automatic and manually created tests*: Shows tests created both automatically and manually
- *Only manually created tests*: Shows only tests created manually with a button
- *Do not show created tests*: Never shows created tests automatically

**Picture Upload Behavior**: What to do with a picture after it has been taken.

- *Do nothing*: No action taken with pictures
- *Attach document*: Attaches the picture as a document
- *Attach and upload to OneDrive*: Attaches the picture and uploads it to OneDrive

**Workflow Integration Enabled**: When enabled, provides events and responses for working with Business Central workflows and approvals.

#### Receiving Settings

**Warehouse Receipts**: Default warehouse receipt trigger value for Test Generation Rules.

- *Never*: No automatic test creation
- *When Whse. Receipt is created*: Creates test when warehouse receipt is created
- *When Whse. Receipt is posted*: Creates test when warehouse receipt is posted

**Purchase Orders**: Default purchase trigger value for Test Generation Rules.

- *Never*: No automatic test creation
- *When Purchase Order is received*: Creates test when purchase order receive is posted
- *When Purchase Order is posted*: Creates test when purchase order is released

**Sales Returns**: Default sales return trigger value for Test Generation Rules.

- *Never*: No automatic test creation
- *When Sales Return is received*: Creates test when sales return order receive is posted

**Transfer Orders**: Default transfer trigger value for Test Generation Rules.

- *Never*: No automatic test creation
- *When Transfer Order is received*: Creates test when transfer order receive is posted

#### Production Settings

**Production - Create Test**: Default production-related trigger value for Test Generation Rules.

- *Never*: No automatic test creation
- *When Output is posted*: Creates test when production output is posted
- *When Order is released*: Creates test when production order is released
- *When a released order is refreshed*: Creates test when released order is refreshed

**Auto Output Configuration**: Granular options for when a test should be created automatically during the production process.

- *Any Output Entry*: Creates test on any output
- *Any Quantity Output*: Creates test on any quantity posting
- *Only with Quantity*: Creates test only when quantity is posted
- *Only with Scrap*: Creates test only when scrap is posted

**Assembly - Create Test**: Default assembly-related trigger value for Test Generation Rules.

- *Never*: No automatic test creation
- *When Output is posted*: Creates test when assembly output is posted

#### Inventory and Warehousing Settings

**Create Test**: Default warehousing related trigger value for Test Generation Rules.

- *Never*: No automatic test creation
- *Movement into Bin*: Creates test when warehouse movement is registered

**Batch Name (Bin Movements)**: The batch to use for bin movements and reclassifications for non-directed pick and put-away locations.

**Whse. Batch Name (Bin Movements)**: The batch to use for bin movements and reclassifications for directed pick and put-away locations.

**Whse. Worksheet Name**: The worksheet used for warehouse movements for directed pick and put-away locations.

**Batch Name (Inventory Adjustments)**: The batch to use for negative inventory adjustment item journals.

**Whse. Batch Name (Inventory Adjustments)**: The batch to use for negative inventory adjustment warehouse item journals.

#### Item Tracking Settings

**Tracking Before Finishing**: Whether to require item tracking before finishing a test.

- *Allow missing item tracking*: Permits tests without lot/serial numbers
- *Posted Item Tracking only*: Requires lot/serial numbers to be posted in the system
- *Reservation or posted*: Allows lot/serial numbers that exist in the system but may not be posted yet
- *Any non-empty value*: Permits any non-empty lot/serial value, even if not in inventory

## Next Steps

After completing initial setup:

1. [Create Quality Inspection Templates](1.4-quality-templates.md)
2. [Set Up Test Generation Rules](1.5-test-generation-rules.md)
3. [Configure Workflows (Optional)](1.6-quality-workflows.md)
4. [Test Your Configuration](./testing-configuration.md)

## Common Setup Scenarios

### Scenario 1: Purchase Receipt Testing Only

- Focus on purchase trigger configuration
- Create templates for incoming goods inspection
- Set up rules for vendor-specific or item-specific testing

### Scenario 2: Production Output Testing Only

- Focus on production trigger configuration
- Create templates for finished goods inspection
- Set up rules for routing-specific or work center-specific testing

### Scenario 3: Comprehensive Quality System

- Configure both purchase and production triggers
- Create multiple templates for different inspection types
- Set up workflows for automated lot blocking/unblocking

## Troubleshooting Setup Issues

### Quality Tests Not Creating Automatically

- Verify trigger settings in Quality Management Setup
- Check test generation rules are properly configured
- Ensure templates are assigned to generation rules

### Workflow Events Not Available

- Verify **Enable Workflow Integration** is enabled in Quality Management Setup
- Check that appropriate permissions are assigned

## Related information

[Assisted Setup Wizard](qms-assisted-setup-wizard.md)  
[Creating Quality Inspection Templates](qms-quality-templates.md)  
[Setting Up Test Generation Rules](qms-test-generation-rules.md)  
[Quality Management Overview](qms-overview.md)