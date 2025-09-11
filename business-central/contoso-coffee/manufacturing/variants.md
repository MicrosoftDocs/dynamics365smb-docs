---
title: Variants
description: Learn how to update a demand forecast for each variant of a product in Business Central. 
ms.date: 09/11/2025
ms.topic: article
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Walkthrough: Variants

This article describes how to use the Contoso Coffee demo data to learn about variants.

## Scenario

You're the production planner at Contoso Coffee, and you must update the demand forecast for each variant of item SP-SCM1006, AutoDripLite. Because each variant has a different color, you must make sure that you use the correct bill of materials (BOM) for them. To calculate supply, run the planning worksheet.  

## Steps

1. Set up the stockkeeping units (SKUs) for item SP-SCM1006, AutoDripLite. Assign a BOM to a SKU with the variants RED and WHITE.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter *items*, and then choose the related link.  
    2. Open the item **SP-SCM1006, AutoDripLite**.
    3. Choose the **Create Stockkeeping Unit** action.  
    4. Set the **Create Per** field to **Location & Variant**.
    5. Set a filter for the **MAIN** location, and then choose **OK**.
    6. Choose the **Stockkeeping Units** action.  
    7. Update the production BOMs for the following stockkeeping units:

        1. For RED on MAIN, set **SP-SCM1006-RED**.  
        2. For WHITE on MAIN, set **SP-SCM1006-WHITE**.  
        3. Leave the **Production BOM No.** field empty for BLACK on MAIN.  

2. Update your inventory setup to respect demand forecast on locations and variants.  

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.  
    2. Turn on the **Use forecast on location** toggle.
    3. Turn on the **Use forecast on variant** toggle.
    4. Close the **Inventory Setup** page.

3. Create a new monthly demand forecast named **AUTODRIP**. Filter the forecast by the item **SP-SCM1006** and location **MAIN**. Set the demand for May for each variant.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Demand Forecast**, and then select the related link.
    2. Create a new demand forecast named **AUTODRIP**.
    3. Choose the **Edit Demand Forecast** action.
    4. In the **View by** field, select **Month**.
    5. In the **Item Filter** field, select **SP-SCM1006**
    6. Turn on the **Use forecast on location** toggle.
    7. In the **Location Filter** field, select **MAIN**.
    8. Turn on the **Use forecast on variant** toggle.
    9. For each line, update the values in the May column, as follows:

        1. For RED on MAIN, set **100**.
        2. For WHITE on MAIN, set **200**.
        3. For BLACK on MAIN, set **300**.

    10. Close the **Demand Forecast** page.

4. Run MPS planning in May for the demand forecasts. Review the components to ensure that item paint (color) is correct for each variant.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Planning Worksheets**, and then choose the related link.
    2. Choose the **Calculate Regenerative Plan** action.
    3. Turn on the **MPS** toggle.
    4. Turn off the **MRP** toggle.
    5. In the **Starting Date** field, select **May 1**.
    6. In the **Ending Date** field, select **May 31**.
    7. In the **Use Forecast** field, select **AUTODRIP**.
    8. Choose **OK**.
    9. For each created line, choose the **Components** action and review which paint is used.  

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  
