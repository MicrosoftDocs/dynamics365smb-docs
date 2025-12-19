---
title: Quality management overview
description: Learn how to use quality management to ensure product quality through automated and manual inspections, lot results, and workflow integration.
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

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

Quality Management is a quality inspection application for [!INCLUDE [prod_short](includes/prod_short.md)]. The app provides comprehensive quality control capabilities throughout your business operations. This app enables automated and manual quality inspections for purchase receipts, production and assembly output, and warehouse operations.

Quality Management helps you maintain product quality standards by creating inspections at key points in your business processes. The app integrates seamlessly with purchasing, production, assembly, and warehouse management in [!INCLUDE [prod_short](includes/prod_short.md)] to embed quality control in your daily operations.

### Key capabilities

The Quality Management app offers a range of benefits.

- **Automated Inspection Creation**: Automatically generate quality inspections when you receive purchase orders, post production and assembly output, or process warehouse movements.
- **Manual Inspection Creation**: Create quality inspections on-demand for reactive scenarios.
- **Scheduled Inspection Creation**: Create periodic quality inspections using job queues.
- **Template-Based Inspections**: Use predefined quality inspection templates with customizable measurements and pass/fail criteria.
- **Lot Blocking and Results**: Automatically block inventory lots based on quality inspection results.
- **Workflow Integration**: Configure automated responses to inspection results using workflows for quality management.
- **Handle Noncompliant Items**: Comprehensive features for processing noncompliant items. For example, you can do automatic movements to quarantine bins, make negative adjustments for disposal, transfer orders to different locations, and create purchase returns to vendors.
- **Warehouse Integration**: Full support for locations with and without warehouse handling.

## Getting started

Setting up Quality Management involves configuring quality inspection templates, inspection generation rules, and integration with your [!INCLUDE [prod_short](includes/prod_short.md)] processes. To learn more, go to:

- [Initial Setup and Configuration](qms-setup.md)
- [Assisted Setup Guide](qms-assisted-setup.md)
- [Configuring Quality Inspection Results](qms-configuring-grades.md)
- [Creating Quality Inspection Templates](qms-quality-templates.md)
- [Setting Up Inspection Generation Rules](qms-test-generation-rules.md)
- [Configuring Workflows](qms-quality-workflows.md)

## Typical use cases

After you configure the app, Quality Management gives you several ways to create and manage quality inspections.

### Purchase receipt inspections

- [Purchase Receipt Inspections without Warehouse Handling](qms-purchase-receipt-testing-simple.md)
- [Purchase Receipt Inspections with Warehouse Handling](qms-purchase-receipt-testing-warehouse.md)

### Production inspections

- [Production Output Quality Inspections](qms-production-output-testing.md)

### Manual and scheduled inspections

- [Manual Inspection Creation](qms-manual-test-creation.md)
- [Scheduled Inspection Creation](qms-scheduled-test-creation.md)

### Quality control actions

- [Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)
- [Processing Non-Compliant Items](qms-non-compliant-processing.md)

## Prerequisites

- Microsoft Dynamics 365 Business Central (on-premises or cloud)
- Premium experience tier (required for production order functionality)

   > [!NOTE]
   > The Premium experience is required for production capabilities. If you don't need those, you can use the Essential experience.

- Quality Management app is installed and configured.

## Related information

[Quality management setup and configuration](qms-setup.md)  
[Configure quality inspection results](qms-configuring-grades.md)