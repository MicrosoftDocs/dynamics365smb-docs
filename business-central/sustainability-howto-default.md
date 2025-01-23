---
title: Sustainability default data
description: Learn how to set up sustainability default values on you master data you will use across the system.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, emission, GHG, CSRD, carbon, CO2, value chain
ms.search.form: 16, 30, 76, 5800, 99000754, 99000760
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# Sustainability default data   

To simplify managing your sustainability accounts and emissions, you can establish default values for the following entities:  

- **G/L Account** (only default sustainability account available)
- **Item** (available default sustaianability account and emissions)
- **Resource** (available default sustaianability account and emissions)
- **Work Center** (available default sustaianability account and emissions)
- **Machine Center** (available default sustaianability account and emissions)

> [!NOTE]
> Although you can set default values, you have the flexibility to change them on journals and documents as needed. These values are simply defaults and not mandatory.  

## G/L Accounts

To set up default **Sustainability Account** for the **G/L Account**, follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of accounts**, and then select the related link. 
2. Pick the **No.** for the account you want to configure to open the **G/L Account Card**.  
3. On the **Sustainability** FastTab use the **Default Sust. Account** field to select the sustaianability account you want to use as a default one. 
4. Close the page.   

## Items

For items you can use manually enterred sustainability account, or using default value you have on the **Item Category**. We will explain both of options in the following process.

Before we proceed with the item set up, let's first explain how to set up default sustainability account for the **Item Category**. To do so, follow next steps: 

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item categories**, and then select the related link.
2. Pick the **Code** for the category you want to configure to open the **Item Category Card**.  
3. On the **Sustainability** FastTab use the **Default Sust. Account** field to select the sustaianability account you want to use as a default one for chose category. 
4. Close the page.   

To set up default sustainability values for the **Item**, follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then select the related link. 
2. Open the card for an item for which you want to set up default values.  
3. Add the default sustainability account:   

   1. On the **Sustainability** FastTab use the **Default Sust. Account** field to select the sustaianability account you want to use as a default one.  
   2. If you have configure default sustainability accounts on item categories, select the **Item Category Code** you want to use on the **Item** FastTab and default value for this category will updae the value in **Default Sust. Account** field for this item. 

4. Populate the following fields for default emissions for this item:   

   1. **Default CO2 Emission** 
   2. **Default CH4 Emission**  
   3. **Default N2O Emission** 

> [!NOTE]
> You can add default emissions only if the **Replenishment System** is set to **Purchase**. For other options, you can only set up the **Default Sust. Account**, and CO2e (carbon equivalent) will be calculated based on production or assembly processes. If you have already populated emissions and then change the **Replenishment System** to something other than **Purchase**, the system will delete the existing emissions.   

5. Run the **Calculate CO2e** action to calculate **CO2e per Unit** field if you are just making set up for this item and you do not have any transactions earlier. 
6. By default this action will offer update only for this one item, but you can change the filter and apply it to different items range.  

> [!NOTE]
> The calculation of CO2e (carbon equivalent) is based on the default emissions you have populated for this item and the setup you have in the **Emission Fees** table.  

7. Close the page.    

> [!NOTE]
> The information you enter related to emissions and the calculated **CO2e per Unit** will be overridden by the system's calculations for this item based on **Sustainability Value Entry**. This data is obtained from the **Posted Purchase Invoice** and uses the average method of emission calculation. Therefore, manually calculated **CO2e per Unit** will only be used before posting documents with the correct values. This means you can use manual creation for data planning (**Production BOM**, **Assembly Order**, etc.) before you have posted the related document.  

## Resources

To set up default sustainability values for the **Resource**, follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **resources**, and then select the related link. 
2. Open the card for a resource for which you want to set up default values.
3. On the **Sustainability** FastTab use the **Default Sust. Account** field to select the sustaianability account you want to use as a default one.  
4.  Populate the following fields for default emissions for this item:   

   1. **Default CO2 Emission** 
   2. **Default CH4 Emission**  
   3. **Default N2O Emission** 

5. Run the **Calculate CO2e** action to calculate **CO2e per Unit** field. 

> [!NOTE]
> You must use the **Calculate CO2e** action to calculate the **CO2e per Unit** field, as there are no other transactions that impact these values as we have in the case of items.  

6. By default this action will offer update only for this one resource, but you can change the filter and apply it to different resources range.  

> [!NOTE]
> The calculation of CO2e (carbon equivalent) is based on the default emissions you have populated for this item and the setup you have in the **Emission Fees** table.  

7. Close the page.    

## Work Centers



## Machine Centers



## See also  

[Sustainability Management overview](finance-manage-sustainability.md) 
[Sustainability Value Chain overview](value-chain-howto-overview.md)
[Sustainability setup](finance-sustainability-setup.md)    
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)    
[Record sustainability entries](finance-sustainability-journal.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
