---
title: Sustainability Value Chain Setup
description: Learn how to enable value chain in Business Central and all aditional setup you need to make.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, CO2e, value chain, setup
ms.search.form: 6221, 6245
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: 
---

# Sustainability Value Chain Setup   

To use the Sustainability Value Chain functionallity effectively, you need to set up some basic controls and instructions for the whole functionality. This article explains how to do that.

## Sustainability setup  

You need to specify some settings for the Sustainability Value Chain functionallity, such as the eneblement of this module working withing Sustainability module and areas user will use and track.  

To configure these settings, follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link. 
2. Firt check if the basic setup already exists. If it doesn't exist, follow [this intstruction](finance-sustainability-setup.md) to setup it.  
3. On the **Procurement** FastTab, configure the required fields that are related to the Sustainability Value Chain functionallity.   

    | Field | Description |
    |-------|-------------|
    | **Enable Value Chain tracking** | Specifies the enablement of sustainability value entries postings through the value chain operations and the visibility of these fields in operational documents and journals. Without enabling this field, users will not see nothing related with the sustaianability in all operational documents, orders, and journals. |
    | **G/L Account Emissions** | Specifies the enablement of default **Sustainability Account** on the G/L Account card. |
    | **Item Emissions** | Specifies the enablement of default **Sustainability Account** and emissions on the **Item** card. |
    | **Item Charge Emissions** | Specifies the enablement of default **Sustainability Account** on the **Item Charge** (currently not operating). |
    | **Resource Emissions** | Specifies the enablement of default **Sustainability Account** and emissions on the **Resource** card. |
    | **Work Machine Center Emissions** | Specifies the enablement of default **Sustainability Account** and emissions on the **Work Center** and **Machine Center** cards. |

> [!NOTE]
> Keep in mind that even if you selected the **Use Emissions In Purchase Documents** field, it will not automaticall activate the Sustainability Value Chain functionallity. Haing enable only this field will enable using emissions in the purchase documents, but if you want to use purchase documents in the value chain operations you must select the **Enable Value Chain tracking** field as well.  

> [!NOTE]
> The **Item Charge** functionallity currently is not supported within the Sustainability Value Chain process. This feature will be added in 2025 release wave 2.  

## Emission Fees  

As a prerequisite for using sustainability value chain functionallity you must configure carbon dioxide equivalents (CO2e) as complete value chain works only for CO2e and not for each of gasses. To do so, you need to configure the **Emission Fees** page. To set up this information, follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Emission Fees**, and then select the related link. 
2. In the **Emission Type** field, choose the GHG emission you want to configure: **CO2**, **CH4**, or **N2O**. This field is mandatory.   
3. The **Carbon Equivalent Factor** specifies the coefficient that converts the impact of various greenhouse gases into the equivalent amount of carbon dioxide based on their global warming potential. If the **Emission Type** is CO2, the **Carbon Equivalent Factor** is always *1* and you can't modify this value, because CO2 is the reference gas used for calculating the global warming potential (GWP) of other greenhouse gases; since CO2 is the baseline, its GWP is set to *1*. For other GHG gases, you must configure the values manually.  

> [!NOTE]
> To calculate the carbon equivalent factor, you can use the following example: If we assume that 1 kilogram of N2O is equivalent to 298 kilograms of CO2, you need to divide 1 by 298 and the result you need to populate is 0.00336.  

To track internal carbon fees or use another features related to using carbon dioxide equivalents (CO2e), read [detailed explanation here](finance-sustainability-setup.md). 


## See also  
[Sustainability Value Chain overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md) 
[Sustainability setup](finance-sustainability-setup.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    


[!INCLUDE[footer-include](includes/footer-banner.md)]
