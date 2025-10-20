---
title: Quality management overview
description: Learn how to use quality management to ensure product quality through automated and manual testing, lot grading, and workflow integration.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 
ms.date: 10/20/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Quality management overview

Quality Management is a foundational quality inspection application for Microsoft Dynamics 365 Business Central that provides comprehensive quality control capabilities throughout your business operations. This application enables automated and manual quality testing for purchase receipts, production and assembly output, and warehouse operations.

## What is Quality Management?

Quality Management helps you maintain product quality standards by creating inspection tests at key points in your business processes. The application integrates seamlessly with Business Central's purchasing, production, assembly, and warehouse management modules to ensure quality control is embedded in your daily operations.

### Key Capabilities

- **Automated Test Creation**: Automatically generate quality inspection tests when receiving purchase orders, posting production and assembly output, or processing warehouse movements.
- **Manual Test Creation**: Create quality tests on-demand for reactive testing scenarios.
- **Scheduled Test Creation**: Create quality tests periodically using job queues for routine inspections.
- **Template-Based Testing**: Use predefined quality inspection templates with customizable measurements and pass/fail criteria.
- **Lot Blocking and Grading**: Automatically block or grade inventory lots based on test results.
- **Workflow Integration**: Configure automated responses to test results using Business Central workflows.
- **Inventory Movement**: Comprehensive non-compliant item processing including automatic movement to quarantine bins, negative adjustments for disposal, transfer orders to different locations, and purchase returns to vendors.
- **Warehouse Integration**: Full support for locations with and without warehouse handling.

## How to Set Up

Setting up Quality Management involves configuring templates, test generation rules, and integration with your Business Central processes:

- [Initial Setup and Configuration](1.1-quality-management-setup.md)
- [Assisted Setup Wizard](1.2-assisted-setup-wizard.md)
- [Configuring Quality Inspection Grades](1.3-configuring-grades.md)
- [Creating Quality Inspection Templates](1.4-quality-templates.md)
- [Setting Up Test Generation Rules](1.5-test-generation-rules.md)
- [Configuring Workflows](1.6-quality-workflows.md)

## How to Use

Once configured, Quality Management provides several ways to create and manage quality tests:

### Purchase Receipt Testing
- [Purchase Receipt Testing Without Warehouse Tracking](2.1-purchase-receipt-testing-simple.md)
- [Purchase Receipt Testing With Warehouse Tracking](2.2-purchase-receipt-testing-warehouse.md)

### Production Testing
- [Production Output Quality Testing](2.3-production-output-testing.md)

### Manual and Scheduled Testing
- [Manual Test Creation](2.4-manual-test-creation.md)
- [Scheduled Test Creation](2.5-scheduled-test-creation.md)

### Quality Control Actions
- [Lot Blocking and Unblocking](3.1-lot-blocking-unblocking.md)
- [Processing Non-Compliant Items](3.2-non-compliant-processing.md)

## Prerequisites

- Microsoft Dynamics 365 Business Central (on-premises or cloud)
- Premium experience tier (required for production order functionality)
- Quality Management app installed and configured

## See Also

- [Microsoft Dynamics 365 Business Central Documentation](https://learn.microsoft.com/en-us/dynamics365/business-central/)