---
title: Plan Production for Item Variants
description: Learn how to use Contoso Coffee demo data to assign variant-specific production BOMs and plan supply from demand forecasts in Business Central.
ms.date: 11/12/2026
ms.topic: how-to
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
ai-usage: ai-assisted
---

# Plan production for item variants

This article describes how to use the Contoso Coffee demo data to learn about variants.

## Scenario for forecasting AutoDripLite variants

You're the production planner at Contoso Coffee, and you must update the demand forecast for each variant of item SP-SCM1006, AutoDripLite. Because each variant has a different color, you must make sure that you use the correct bill of materials (BOM) for them. To calculate supply, run the planning worksheet.  

## Assign variant BOMs and plan supply

1. Set up the stockkeeping units (SKUs) for item SP-SCM1006, AutoDripLite. Assign a BOM to a SKU with the variants RED and WHITE.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **items**, and then choose the related link.
    1. Open the item **SP-SCM1006, AutoDripLite**.
    1. Choose the **Create Stockkeeping Unit** action.
    1. Set the **Create Per** field to **Location & Variant**.
    1. Set a filter for the **MAIN** location, and then choose **OK**.
    1. Choose the **Stockkeeping Units** action.
    1. Update the production BOMs for the following stockkeeping units:

        1. For RED on MAIN, set **SP-SCM1006-RED**.  
        1. For WHITE on MAIN, set **SP-SCM1006-WHITE**.
        1. Leave the **Production BOM No.** field empty for BLACK on MAIN.

1. Update your inventory setup to respect demand forecast on locations and variants.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Inventory Setup**, and then choose the related link.
    1. Turn on the **Use forecast on location** toggle.
    1. Turn on the **Use forecast on variant** toggle.
    1. Close the **Inventory Setup** page.

1. Create a new monthly demand forecast named **AUTODRIP**. Filter the forecast by the item **SP-SCM1006** and location **MAIN**. Set the demand for May for each variant.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Demand Forecast**, and then select the related link.
    1. Create a new demand forecast named **AUTODRIP**.
    1. Choose the **Edit Demand Forecast** action.
    1. In the **View by** field, select **Month**.
    1. In the **Item Filter** field, select **SP-SCM1006**
    1. Turn on the **Use forecast on location** toggle.
    1. In the **Location Filter** field, select **MAIN**.
    1. Turn on the **Use forecast on variant** toggle.
    1. For each line, update the values in the May column, as follows:

        1. For RED on MAIN, set **100**.
        1. For WHITE on MAIN, set **200**.
        1. For BLACK on MAIN, set **300**.

    1. Close the **Demand Forecast** page.

1. Run MPS planning in May for the demand forecasts. Review the components to ensure that item paint (color) is correct for each variant.

    1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Planning Worksheets**, and then choose the related link.
    1. Choose the **Calculate Regenerative Plan** action.
    1. Turn on the **MPS** toggle.
    1. Turn off the **MRP** toggle.
    1. In the **Starting Date** field, select **May 1**.
    1. In the **Ending Date** field, select **May 31**.
    1. In the **Use Forecast** field, select **AUTODRIP**.
    1. Choose **OK**.
    1. For each created line, choose the **Components** action and review which paint is used.

The demo BOMs contain the following paint items. Each color BOM also includes **SP-SCM1006-BASE** as a production BOM component.

| Variant | Production BOM | Paint item |
|---------|----------------|------------|
| RED | SP-SCM1006-RED | SP-BOM3002, Paint, red |
| WHITE | SP-SCM1006-WHITE | SP-BOM3003, Paint, white |
| BLACK | SP-SCM1006-BLACK | SP-BOM3001, Paint, black |

The item card for **SP-SCM1006** uses **SP-SCM1006-BLACK** as its production BOM.

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
