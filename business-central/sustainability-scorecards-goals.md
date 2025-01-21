---
title: Sustainability sorecards and goals
description: Learn how to set up and use sustainability scorecards and goals.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, scorecard, goal, forecast, budget
ms.search.form: 
ms.date: 08/19/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Sustainability scorecards and goals overview

This article offers guidance on how to create scorecards and goals, and how to update the status of goals. Scorecards and goals allow organizations to curate sustainability metrics and track them against key business objectives. Goals can be created based on current and target values, so users can keep track of the progress of current gas emissions, or water/waste intensity, compared to previous periods.  

## Create a scorecard  

To create new a *Sustainability Scorecard*, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Scorecards**, and then select the related link. 

2. On the **Sustainability Scorecards** page, select **New** to create a new scorecard.  

3. Specify the **No.** and the **Name** fields on the **General** FastTab, and then add the **Owner**. 

> [!NOTE]
> In the **Owner** field, you can only choose users who have selected the **Sustainability Manager** field in the **User Setup** table. 

## Create goals  

To create a new **Sustainability Goal**, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Scorecards**, and then select the related link.

2. Choose the **Goals** action to create a new **Sustainability Goal** for the selected scorecard.  

3. Select **New** to start creating a goal.

4. The **Scorecard No.** is automatically added based on the value from the connected **Sustainability Scorecard**, and the user won't be able to edit this field. The system also sets up the **Unit of Measure** field based on the **Emission Unit of Measure Code** on the **Sustainability Setup** page.  

5. You must fill in **No.** and **Name** of the new **Sustainability Goal**. The **Owner** field is automatically populated based on the value from the connected **Sustainability Scorecard**. 

6. Users can decide to create a *Sustainability Goal* for the entire company, a specific country/region, or a facility. If users want to create a specific goal, they must choose the country or region in the **Country/Region Code** field or the facility in the **Responsibility Center** field.  

7. Select the **Start Date** and **End Date** fields to set up a dedicated period for tracking current values. This configuration determines the values in the following fields: **Current Value for CO2**, **Current Value for CH4**, **Current Value for N2O**, **Current Value for Water Intensity**, and **Current Value for Waste Intesity'.  

8. Select the **Baseline Start Date** and **Baseline End Date** fields to set up a dedicated baseline period for comparing current values. This configuration determines the values in the following fields: **Baseline for CO2**, **Baseline for CH4**, **Baseline for N2O**, **Baseline for Water Intensity**, and **Baseline for Waste Intesity'.  

9. Users also can add target values in the selected **Unit of Measure** field for the current period using the following fields: **Target Value for CO2**, **Target Value for CH4**, **Target Value for N2O**, **Target Value for Water Intensity**, and **Target Value for Waste Intesity'.   

10. One of these goals can be selected as a **Main Goal**. Values from the main goal are used on the **Sustainability Manager** role center.  

If you have many goals on the page, you can use the **Show My Goals** action to see only your goals; if you want to show all, you must run the **Show All Goals** action.  

> [!NOTE]
> **Sustainability Goals** can only be created for a specific **Sustainability Scorecard**; you can't create goals that aren't related to the scorecard, but you can create more goals for one scorecard. You can have only one **Sustainability Goal** marked as the **Main Goal**.  

> [!NOTE]
> Users can set up different combinations of goals for the whole company, specific countries or regions, and a responsibility center for one **Sustainability Scorecard**. Users can also use different periods for the same model of tracking.  

## See also

[Sustainability setup](finance-sustainability-setup.md)    
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)    
[How to record sustainability entries](finance-sustainability-journal.md)    
[Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)    
[Sustainability reports and analytics in Business Central](sustainability-reports.md)   
[Sustainability API](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)    
[Finance](finance.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
