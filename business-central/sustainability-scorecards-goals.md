---
title: Sustainability scorecards and goals
description: Learn how to set up and use sustainability scorecards and goals.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, scorecard, goal, forecast, budget
ms.search.form: 
ms.date: 01/30/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Sustainability scorecards and goals overview

This article offers guidance on how to create scorecards and goals, and how to update the status of goals. Scorecards and goals allow organizations to curate sustainability metrics and track them against key business objectives. Goals can be created based on current and target values, so users can keep track of the progress of current gas emissions, or water/waste intensity, compared to previous periods.  

## Create a scorecard  

To create a sustainability scorecard, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Scorecards**, and then select the related link.
2. On the **Sustainability Scorecards** page, select **New** to create a new scorecard.  
3. Specify the **No.** and the **Name** fields on the **General** FastTab, and then add the **Owner**.

> [!NOTE]
> In the **Owner** field, you can only choose users who enabled the **Sustainability Manager** field on the **User Setup** page.

## Create goals  

To create a new sustainability goal, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Scorecards**, and then select the related link.
2. Choose the **Goals** action to create a new sustainability goal for the scorecard.  
3. Select **New** to start creating a goal.
4. The **Scorecard No.** is automatically added based on the value from the sustainability scorecard, and you can't edit this field. [!INCLUDE [prod_short](includes/prod_short.md)] also fills in the **Unit of Measure** field based on the **Emission Unit of Measure Code** on the **Sustainability Setup** page.  
5. Fill in **No.** and **Name** of the new sustainability goal. The **Owner** field is automatically filled in based on the value from the connected **Sustainability Scorecard**.
6. You can create a sustainability goal for the entire company, a specific country/region, or a facility. To create a specific goal, choose the country or region in the **Country/Region Code** field or the facility in the **Responsibility Center** field.  
7. Select the **Start Date** and **End Date** fields to set up a dedicated period for tracking current values. This configuration determines the values in the **Current Value for CO2**, **Current Value for CH4**, **Current Value for N2O**, **Current Value for Water Intensity**, and **Current Value for Waste Intensity** fields.  
8. Select the **Baseline Start Date** and **Baseline End Date** fields to set up a dedicated baseline period for comparing current values. This configuration determines the values in the **Baseline for CO2**, **Baseline for CH4**, **Baseline for N2O**, **Baseline for Water Intensity**, and **Baseline for Waste Intensity** fields.  
9. You can also add target values in the selected **Unit of Measure** field for the current period using the following **Target Value for CO2**, **Target Value for CH4**, **Target Value for N2O**, **Target Value for Water Intensity**, and **Target Value for Waste Intensity** fields.
10. You can specify one of these goals as a **Main Goal**. Values from the main goal are used on the **Sustainability Manager** Role Center.  

If you have many goals on the page, you can use the **Show My Goals** action to show only your goals. To show all, run the **Show All Goals** action.  

> [!NOTE]
> You can only create sustainability goals for a specific sustainability scorecard. You can't create goals that aren't related to a scorecard, but you can create more goals for one scorecard. You can only have one sustainability goal as the **Main Goal**.  

> [!NOTE]
> You can set up different combinations of goals for the whole company, specific countries or regions, and a responsibility center for a sustainability scorecard. You can also use different periods for the same model of tracking.  

## Related information

[Sustainability setup](finance-sustainability-setup.md)  
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)  
[How to record sustainability entries](finance-sustainability-journal.md)  
[Ad hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)  
[Sustainability reports and analytics in Business Central](sustainability-reports.md)  
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
