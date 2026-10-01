---
title: Quality management overview
description: Learn how to use quality management to ensure product quality through automated and manual inspections, lot results, and workflow integration.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.search.form: 20400, 20408, 20404, 20402, 20416
ms.date: 09/07/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

# Quality management overview

[!INCLUDE [introduced-in-2026rw1](includes/introduced-in-2026rw1.md)]

Quality management is a quality inspection application for [!INCLUDE [prod_short](includes/prod_short.md)]. Quality management features can help you maintain product quality standards by creating inspections at key points in your purchasing, production, assembly, and warehouse management processes. 

> [!NOTE]
> Quality Management is a Microsoft-published extension that installs automatically on new environments. For existing environments, you can install it from the **Extension Management** page or get it from [Microsoft Marketplace](https://go.microsoft.com/fwlink/?LinkId=2370677). Learn more in [Quality management setup and configuration](qms-setup.md#prerequisites).

## Key capabilities

Quality management features offer a range of benefits.

- **Create inspections automatically**: Automatically generate quality inspections when you receive purchase orders, post production and assembly output, or process warehouse movements.
- **Create inspections manually**: Create quality inspections on-demand for reactive scenarios.
- **Create inspections on a schedule**: Create periodic quality inspections using job queues.
- **Use templates for inspections**: Use predefined quality inspection templates with customizable measurements and pass/fail criteria.
- **Block noncompliant lots**: Automatically block inventory lots based on quality inspection results.
- **Integrate workflows**: Configure automated responses to inspection results using workflows.
- **Handle noncompliant items**: Use features for processing noncompliant items. For example, you can automatically move items to quarantine bins, make negative adjustments for disposal, transfer orders to different locations, and create purchase returns to vendors.
- **Integrate with inbound warehouse flows**: Create inspections from purchase receipts, inventory put-aways, or warehouse receipt lines, depending on the location's warehouse configuration.
- **Inspect warehouse movements**: Create inspections when registered movements place items in selected locations, zones, or bins.

## Get started

Setting up quality management involves configuring quality inspection templates, inspection generation rules, and integration with your [!INCLUDE [prod_short](includes/prod_short.md)] processes. To learn more, go to:

- [Initial Setup and Configuration](qms-setup.md)
- [Configuring Quality Inspection Results](qms-configuring-grades.md)
- [Creating Quality Inspection Templates](qms-quality-templates.md)
- [Setting Up Inspection Generation Rules](qms-test-generation-rules.md)
- [Configuring Workflows](qms-quality-workflows.md)

## Typical use cases

After you configure the app, Quality Management gives you several ways to create and manage quality inspections.

Start with [Work with quality inspections](qms-manual-test-creation.md) for the complete inspection lifecycle. To learn more about creating periodic inspections, go to [Create scheduled quality inspections](qms-scheduled-test-creation.md).

### Quality control actions

- [Lot Blocking and Unblocking](qms-lot-blocking-unblocking.md)
- [Processing Non-Compliant Items](qms-non-compliant-processing.md)

### Contoso Coffee demos

Install and generate the sample modules before using the demos. To learn more about the available scenarios, go to [Set up Contoso Coffee demo data for quality management](qms-contoso-coffee-demo-data.md).

## Related information

[Troubleshoot quality management features](qms-troubleshooting.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]
