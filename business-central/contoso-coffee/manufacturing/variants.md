---
title: Variants
description: Walkthrough to learn how to update demand forecast for each variant of a product in Business Central. 
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
---

# Walkthrough: Variants

In this article, we take you through the steps to use the Contoso Coffee demo data to learn about variants.

## Scenario

You are the production planner at Contoso Coffee. You must update the demand forecast for each variant of item SP-SCM1006, AutoDripLite. Since they have different colors, you must make sure that the right bill of material (BOM) is used for each variant. Run the planning worksheet to calculate supply.  

## Steps

1. Set up the stockkeeping units for item SP-SCM1006, AutoDripLite. Assign a BOM for SKU with the variants RED and WHITE.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter *items*, and then choose the related link.  

    2. Open the item **SP-SCM1006, AutoDripLite**.

    3. Choose the **Create Stockkeeping Unit** action.  

    4. Set the **Create Per** field to *Location & Variant*.

    5. Set a filter for location to *MAIN*, and then choose the **OK** button.

    6. Choose the **Stockkeeping Units** action.  

    7. Update the production BOMs for the following stockkeeping units:

        1. RED on MAIN, set SP-SCM1006-RED  

        2. WHITE on MAIN, set SP-SCM1006-WHITE  

        3. Keep Production BOM No. empty for BLACK on MAIN  

2. Update Manufacturing Setup and respect demand forecast on locations and variants.  

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter *manufacturing setup*, and then choose the related link.  

    2. Switch on the **Use forecast on location** field.

    3. Switch on the **Use forecast on variant** field.

    4. Close the **Manufacturing Setup** window.

3. Create a new monthly demand forecast, *AUTODRIP*. Filter it by the item SP-SCM1006 and location MAIN. Set demand for May for each variant. 

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter *demand forecast*, and then select the related link.

    2. Create a new demand forecast with the name *AUTODRIP*.

    3. Choose the **Edit Demand Forecast** action.

    4. In the **View by** field, select *Month*.

    5. In the **Item Filter** field select *SP-SCM1006*

    6. Switch on the **Use forecast on location** field.

    7. In the **Location Filter** field, select *MAIN*.

    8. Switch on the **Use forecast on variant** field.

    9. For each line updated values in the May column

        1. RED on MAIN, set 100

        2. WHITE on MAIN, set 200

        3. BLACK on MAIN, set 300

    10. Close Demand Forecast windows

4. Run MPS plan in May for created demand forecasts. Review components to see that item paint correlates to variant.

    1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter *planning worksheet*, and then choose the related link.

    2. Choose the **Calculate Regenerative Plan** action.

    3. Switch on the **MPS** field.

    4. Switch off the **MPS** field.

    5. In the **Starting Date** field, select *May,1*

    6. In the **Ending Date** field, select *May, 31*

    7. In the **Use Forecast** field, select *AUTODRIP*

    8. Choose the **OK** action.

    9. For each created line, choose the **Components** action and review which paint is used.  

## Related information

[Introduction to Contoso Coffee Demo Data](../contoso-coffee-intro.md)  
