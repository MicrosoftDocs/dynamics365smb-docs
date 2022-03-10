---
title: Variants
description: Walkthrough to learn how to update demand forecast for each variant of a product in Business Central. 
ms.date: 03/10/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# Walkthrough: Variants

Intro 

## Scenario

You are the production planner at CONTOSO. You need to update demand forecast for each variant of item SP-SCM1006, AutoDripLite. As they use different colors you need to make sure that correct BOM is used for each variant. Run planning worksheet to calculate supply.

## Steps

1. Set up the stockkeeping units for item SP-SCM1006, AutoDripLite. Assign BOM for SKU with Variants RED and WHITE.

    1. In the **Tell Me** window, type "items", and then select the related link.

    2. Select item SP-SCM1006, AutoDripLite.

    3. Choose Create Stockkeeping Unit action.

    4. In the **Create Per** field, select Location & Variant.

    5. Set filter by North location, and then click **OK** to start the batch job.

    6. Choose **Stockkeeping Units** action.

    7. Update Production BOMs for stockkeeping units:

        1. RED on NORTH, set SP-SCM1006-RED

        2. WHITE on NORTH, set SP-SCM1006-WHITE

        3. Keep Production BOM No. empty for BLACK on NORTH.

2. Update Manufacturing Setup and respect demand forecast on locations and variants.

    1. In the **Tell Me** window, type "manufacturing setup", and then select the related link.

    2. Activate **Use forecast on location** toggle.

    3. Activate **Use forecast on variant** toggle.

    4. Close the **Manufacturing Setup** window.

3. Create new monthly demand forecast AUTODRIP. Filter it by item SP-SCM1006 and location NORTH. Set demand for May for each variant.

    1. In the **Tell Me** window, type "demand forecast", and then select the related link.

    2. Create a new demand forecast, in the **Name** field, type AUTODRIP.

    3. Choose **Edit Demand Forecast** action.

    4. In the **View by** field, select Month

    5. In the **Item Filter** field select SP-SCM1006

    6. Activate **Use forecast on location** toggle.

    7. In the **Location Filter** field select NORTH.

    8. Activate **Use forecast on variant** toggle.

    9. For each line updated values in the May column

        1. RED on NORTH, set 100

        2. WHITE on NORTH, set 200

        3. BLACK on NORTH, set 300

    10. Close Demand Forecast windows

4. Run MPS plan in May for created demand forecasts. Review components to see that item paint correlates to variant.

    1. In the **Tell Me** window, type "planning worksheet", and then select the related link.

    2. Choose **Calculate Regenerative Plan** action.

    3. Activate **MPS** toggle.

    4. Disable **MPS** toggle.

    5. In the **Starting Date** field, select May,1

    6. In the **Ending Date** field, select May, 31

    7. In the **Use Forecast** field, select AUTODRIP

    8. Choose **OK**.

    9. For each created line choose **Components** action and review which paint is used.

