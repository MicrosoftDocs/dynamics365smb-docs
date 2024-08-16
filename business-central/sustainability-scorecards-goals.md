---
title: Sustainability Sorecards and Goals
description: Learn how to set up and use sustainability scorecards and goals.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, scorecard, goal, forecast, budget
ms.search.form: 
ms.date: 08/16/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# Sustainability scorecards and goals overview

This article explains how to create scorecards and goals, and how to update the status of goals. Scorecards and goals enable organizations to curate sustainability metrics and track them against key business objectives. Goals can be created based on current and target values, so users can keep track of the progress with current emissions compared with previous periods.  

## Create a scorecard  

To create new **Sustainability Scorecard**, follow the steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Scorecards**, and then select the related link. 
2. When you open the **Sustainability Scorecards** page, click **New** to create new scorecard.  
3. Specify the **No.** and the **Name** fields on the **General** FastTab and then add the **Owner**. 

> [NOTE!]
> In the **Owner** field, you can choose only users which have selected the **Sustainability Manager** field in the **User Setup** table. 

## Create goals  

To create new **Sustainability Goal**, follow the steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Scorecards**, and then select the related link.
2. Select the **Goals** action to create new **Sustainability Goal** for selected scorecard.  
3. Click **New** to start creating new goal.
4. the **Scorecard No.** will be added automatically inheriting this value from the connected **Sustainability Scorecard**, and user cannot edit this field. System will also set up the **Unit of Measure** field based on the **Emission Unit of Measure Code** in the **Sustainability Setup** page.  
5. You need to fill in **No.** and **Name** of new **Sustainability Goal**. The **Owner** field will be populated automatically inheriting this value from the connected **Sustainability Scorecard**.   
6. User can decide to create **Sustainability Goal** for whole company, specific country or facility. If users want to create spcific goal, they need to choose the country or region in the **Country/Region Code** or facility in the **Responsibility Center** field.  
7. Select the **Start Date** and **End Date** fields to set up dedicated period for tracking current values. Values in the following fields will be calculated based on this configuration: **Current Value for CO2**, **Current Value for CH4**, and **Current Value for N2O**. 
8. Select the **Baseline Start Date** and **Baseline End Date** fields to set up dedicated baseline period for comparing with current values. Values in the following fields will be calculated based on this configuration: **Baseline for CO2**, **Baseline for CH4**, and **Baseline for N2O**.
9. Users can also add target values in the selected **Unit of Measure** for the current period using the **Target Value for CO2**, **Target Value for CH4**, and **Target Value for N2O**.   
10. One of these goals can be selected as a **Main Goal**. Values from the main goal will be used on the **Sustainability Manager** role center.  

If you have many goals on the page, you can use the **Show My Goals** action to show you only your goals and if you want to show all, you need to run the **Show All Goals** action.  

> [NOTE!]
> **Sustainability Goal** can be created only for specific **Sustainability Scorecard** and you cannot create goal not related to the scorecard, but you can create more goals for one scorecard. Keep in mind you can have only one **Sustainability Goal** marked as a **Main Goal**.

> [NOTE!]
> Users can set up different combination of goals for whole company, specific country or region, as well as responsibility center for one **Sustainability Scorecard**. Users can also use different periods for the same model of tracking. 

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
