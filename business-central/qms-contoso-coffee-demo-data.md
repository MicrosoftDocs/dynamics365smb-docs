---
title: Set up Contoso Coffee demo data for quality management
description: Install and generate Contoso Coffee demo data to explore quality inspections in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 20400, 5194
ms.date: 09/09/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Set up Contoso Coffee demo data for quality management

The Contoso Coffee demo data provides quality tests, templates, results, lookup values, and inspection generation rules that you can use to explore quality management. The quality module provides configuration but doesn't create inspections or business documents. The demo articles guide you through the transactions that create inspections.

> [!NOTE]
> The **Install Demo Data** action is available only in the online version of [!INCLUDE [prod_short](includes/prod_short.md)].

## Install the demo data extension

You need permission to install extensions and the **Quality Admin & Supervisor** permission set.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Quality Management Setup**, and then choose the related link.
2. Choose **Install Demo Data**.
3. If prompted, install the **Quality Management Contoso Coffee Demo Dataset** extension from Microsoft Marketplace.
4. After the extension is installed, return to **Quality Management Setup**, and then choose **Install Demo Data** again.

The action opens the **Contoso Demo Tool** page.

## Generate data for a demo

1. On the **Contoso Demo Tool** page, select **Quality Management**.
2. Choose the additional module required by the demo:

   - **Warehouse** for the manual item-tracking and warehouse-receipt demos. This module creates the lot-tracked item that the demos use.
   - **Manufacturing** for a production output inspection.

3. Choose **Generate**, and then choose **Generate** again. 

   > [!NOTE]
   > Don't choose **Generate Setup Data**, because setup data alone doesn't create the quality tests, templates, and rules used by the demos.

The tool generates data for the current company. After you generate all data for a module, you can't generate that module again in the same company or reset it from the tool. Use a demonstration company where changing sample records won't affect production data.

## Explore the quality configuration

The **Quality Management** module creates sample results, tests, templates, and two generation rules. The demo articles use the following records:

| Record | Value | Use |
| --- | --- | --- |
| Template | **RECEIVE** | Manual and purchase receipt inspections. |
| Template | **PRODUCTION** | Empty starting template for production inspections. Add tests that match the production process before you run the production demo. |
| Generation rule | Sort order **40**, template **RECEIVE** | Purchase line inspections. |
| Generation rule | Sort order **50**, template **PRODUCTION** | Production routing line inspections. |
| Results | **INPROGRESS**, **FAIL**, **PASS** | Inspection outcomes. |

The generated rules allow manual or automatic creation, but their automatic trigger fields are set to **Never**. Each demo tells you which trigger to enable.

## Scenarios

The Contoso Coffee quality management demo data supports the following scenarios for testing and training:

- [Create an inspection manually from item tracking](qms-purchase-receipt-testing-simple.md)
- [Create an inspection automatically from a warehouse receipt and reinspect the lot](qms-purchase-receipt-testing-warehouse.md)
- [Create a sampled inspection automatically from production output](qms-production-output-testing.md)

## Related information

[Work with quality inspections](qms-manual-test-creation.md)  

[!INCLUDE [footer-banner](includes/footer-banner.md)]
