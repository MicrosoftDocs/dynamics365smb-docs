---
title: Quality management overview
description: Learn how to use quality management to ensure product quality through automated and manual inspections, lot results, and workflow integration.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 20400, 20408, 20404, 20402, 20416, 
ms.date: 03/10/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Quality management overview

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

Quality management is a quality inspection application for [!INCLUDE [prod_short](includes/prod_short.md)]. Quality management features can help you maintain product quality standards by creating inspections at key points in your purchasing, production, assembly, and warehouse management processes. 

## Key capabilities

Quality management features offer a range of benefits.

- **Create inspections automatically**: Automatically generate quality inspections when you receive purchase orders, post production and assembly output, or process warehouse movements.
- **Create inspections manually**: Create quality inspections on-demand for reactive scenarios.
- **Create inspections on a schedule**: Create periodic quality inspections using job queues.
- **Use templates for inspections**: Use predefined quality inspection templates with customizable measurements and pass/fail criteria.
- **Block noncompliant lots**: Automatically block inventory lots based on quality inspection results.
- **Integrate workflows**: Configure automated responses to inspection results using workflows.
- **Handle noncompliant items**: Use features for processing noncompliant items. For example, you can automatically move items to quarantine bins, make negative adjustments for disposal, transfer orders to different locations, and create purchase returns to vendors.
- **Integrate with your warehouse**: Full support for locations with and without warehouse handling.

## Get started

Setting up quality management involves configuring quality inspection templates, inspection generation rules, and integration with your [!INCLUDE [prod_short](includes/prod_short.md)] processes. To learn more, go to:

- [Initial Setup and Configuration](qms-setup.md)
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

## Related information

[Quality management setup and configuration](qms-setup.md)  
[Configure quality inspection results](qms-configuring-grades.md)