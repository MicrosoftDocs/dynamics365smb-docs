---
title: Assisted setup guide for quality management
description: Learn how to use the Quality Management assisted setup guide to configure quality inspections, automate inspection creation, and align workflows with your business processes.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Assisted setup guide for quality management

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

The Quality Management assisted setup guide can help you configure quality management features in [!INCLUDE [prod_short](includes/prod_short.md)]. The guide covers the initial configuration required to do quality inspections, and sets up automatic inspection creation based on business scenarios.

## Start the guide

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Assisted Setup**, and then choose the related link.
2. Choose **Set Up Quality Management** to start the assisted setup guide.

## What to do in each step

The following sections describe each step in the guide.

### Welcome and Terms

This step introduces the guide. To proceed with the setup, agree to the terms and conditions.

### Getting Started Data

Choose whether to apply demonstration and sample data:

- **Apply Getting Started Data**: Downloads and applies basic setup data with useful examples and demonstration data. Getting started data helps you get going quickly or, if you're just exploring, evaluate whether the application fits your needs.
- **Do Not Apply Configuration**: Skips sample data installation. However, some basic setup data for common integration scenarios is applied.

> [!NOTE]
> The guide automatically suggests **Do Not Apply Configuration** if it looks like quality management is already configured or is in use.

### Usage Scenarios

Specify where you plan to use quality inspections:

- **Production**: Create inspections when you record production output. Typical scenarios are when inventory is posted from the output journal, but could also be for intermediate steps or other triggers.
- **Receiving**: Create inspections when you receive inventory from purchase orders, transfer orders, warehouse receipts, or sales returns.
- **Something Else**: Use quality inspection to create manual tests for other areas in [!INCLUDE [prod_short](includes/prod_short.md)], or if you want to manually configure them later.

> [!TIP]
> The steps in the guide differ, based on your selection.

### Production inspection configuration

> [!NOTE]
> This step shows only if you chose **Production** in the previous step.

Specify how to create production inspections:

- **Create inspections automatically**: [!INCLUDE [prod_short](includes/prod_short.md)] creates inspections automatically when you record output. Use this option when inspections must exist when production output occurs.
- **Manual inspection creation**: You manually create inspections. Use this option when your process requires a person to create inspections, or for ad-hoc inspection scenarios like nonconformance reports or tracking rework.

### Receipt inspection configuration  

> [!NOTE]
> This step shows only if you chose **Receiving** in the previous step.

Configure automatic inspection creation for receiving scenarios:

- **Purchase Receipts**: Automatically create inspections when you receive goods via purchase orders.
- **Transfer Receipts**: Automatically create inspections when you receive goods via transfer orders.
- **Warehouse Receipts**: Automatically create inspections when you receive goods via warehouse receipts.
- **Sales Return Receipts**: Automatically create inspections when you receive goods via sales returns.
- **Manual only option**: Choose this option if you only want people to manually create inspections. For example, this option is useful for ad-hoc inspections or tracking damage for received goods.

### Inspection display behavior

> [!NOTE]
> The options in this step vary, based on whether you set up automatic inspection creation.

Specify when to display inspections to users:

- **Show automatic and manually created inspections**: Inspections show immediately when created. Use this option when the person doing the activity (like posting) is also the person who collects the inspection results.
- **Show only manually created tests**: Inspections created automatically don't show immediately, but manually created inspections do. Use this option when different people handle posting versus data collection.
- **Never show immediately**: Inspections are always created in the background. Use this option when the person who creates inspections shouldn't be able to edit them. This option ensures separation of inspection creation and completion.
- **Business Consideration**: Events that trigger inspections without direct interaction (background posting, pr web service integrations like Power Automate) create inspections but doesn't immediately show them.

<!--

We don't usually describe the outcome.

### Completion

When you choose **Finish**, the guide:

- Finalizes all configuration choices and applies them to the setup.
- Marks the assisted setup guide as completed.
- Enables quality management features.

## Configuration Results

The guide configures the **Qlty. Management Setup** table based on your choices:

### Production Settings

- Manual tests disable the production trigger.
- Automatic tests enable the trigger on production output posting.

### Receiving Settings

- You can turn on or turn off each receiving type. For example, purchases, transfers, warehouse, and sales return.
- Manual-only option disables all automatic triggers.

### Display Behavior

- Controls when to automatically show tests.
- Aligns with business roles and workflow separation.

### System Activation

- Sets visibility to **Show** to enable quality management features.
- Refreshes the **Experience** tier settings for the current company on the **Company Information** page.

## Technical integrations

The guide integrates with several [!INCLUDE [prod_short](includes/prod_short.md)] systems:

- **Guided Experience**: Tracks setup completion status and prevents you from rerunning the assisted setup guide unnecessarily.
- **Application Area Management**: Updates feature visibility and user experience settings.
- **Telemetry**: Logs completion events including environment name, company, and user for monitoring and support.
- **Auto Configuration**: Handles basic setup requirements and sample data deployment through configuration packages. -->

<!--

These seem pretty obvious.

## Best practices

This section lists recommendations

### For administrators

- Assign the **Quality Inspection** permission sets to users before you run the guide.
- Consider your business processes when you choose whether to create tests automatically or manually.
- Align display behavior with organizational roles. Separate posting from inspection duties when that's appropriate.

### For implementation

1. Test the guide in a sandbox environment first to validate configuration choices.
2. Document your selected settings for future reference and training.
3. Plan user training based on the resulting test creation and display behaviors.

### Examples of typical scenarios

- **Manufacturing Focus**: Enable production testing with appropriate display behavior for your workflow separation needs.
- **Distribution Focus**: Enable receiving testing for relevant document types (typically purchase receipts).
- **Comprehensive Quality**: Enable both production and receiving with **Show only manually created tests** to maintain workflow separation.
- **Evaluation/Demo**: Enable all features with immediate display for training and demonstration purposes.

## Troubleshooting

- **Insufficient Permissions**: The guide checks for permissions, and displays an error message that instructs users to request permissions from their administrator.
- **Previous Configuration**: The guide finds an existing configuration and preserves the previous settings. However, it allows updates.
- **Getting Started Data**: Sample data installation only occurs if you chose that option and quality management isn't already configured, preventing duplicate or conflicting data. -->

## Related information

[Quality management setup and configuration](qms-setup.md)  
[Configure quality inspection results](qms-configuring-grades.md)
