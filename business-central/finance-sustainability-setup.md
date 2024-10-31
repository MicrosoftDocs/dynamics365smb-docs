---
title: Set up the Sustainability module in Business Central
description: Learn how to configure the Sustainability module to track and report your greenhouse gas emissions and carbon fees.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, equivalent, CO2e, CO2, carbon, role center, fees
ms.search.form: 6221, 6235, 6245
ms.date: 08/22/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Set up the Sustainability module in Business Central 

To use the Sustainability module effectively, you need to set up some basic controls and instructions for the whole functionality. This article explains how to do that.

## Role center  

If your primary responsibilities involve sustainability processes, we recommend that you use the *Sustainability Manager* role center. This role center gives you easy access to the core sustainability features, as well as finance and procurement processes. It also shows you the most important sustainability-related key performance indicators (KPIs).

To configure this role center, follow the steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **My settings**, and then select the related link.
2. In the **Role** field, select the **Available Roles** page.
3. Choose the **Sustainability Manager** line.
4. Select **OK**.

## Sustainability setup  

You need to specify some general settings for the Sustainability module, such as the unit of measure for emissions, the decimal places for amounts, and whether some fields are mandatory or not.

To configure these settings, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link.
2. On the **General** FastTab, configure the required fields that are related to the Sustainability module.

    | Field | Description |
    |-------|-------------|
    | **Emission Unit of Measure Code** | Enter the unit of measure code that is used to register emissions. |
    | **Emission Decimal Places** | Enter the number of decimal places that are shown for emission amounts. The default setting, *2:5*, means that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |
    | **Country/Region Mandatory** | Select this field if you want to make the country/region field mandatory. Users can set the country/region field in journals even if you don't select this field. However, by selecting it, you require that users set the country/region field before posting. |
    | **Responsibility Center Mandatory** | Select this field if you want to make the responsibility center mandatory. The responsibility center can be used as a facility, so that you can measure facility-based emissions. Users can set the responsibility center field in journals even if you don't select this field. However, by selecting it, you require that users set the responsibility center field before posting. |
    | **Block Calculation Foundation Change If Ledger Entries Exist** | Select this field if you want to prevent changes to the calculation foundation (formula) at the account category level when the formula has already been applied to sustainability entries. |
    | **Enable Background Error Check** | Select this field if you want to enable the background error check of sustainability journal lines. |

    > [!NOTE]
    > After you enable or turn off the background error check in journals, you must sign in again before you start the new setup.

3. On the **Procurement** FastTab, configure the required fields that are related to usage of sustainability features in the purchase process.  

    | Field | Description |
    |-------|-------------|
    | **Use Emissions In Purchase Documents** | If you enable this field, sustainability related fields and features appear in the purchase documents, such as **Sustainability Account** or different emissions. |

4. On the **Calculations** FastTab, configure the required fields that are related to the formulas that are used to calculate emissions.

    | Field | Description |
    |-------|-------------|
    | **Fuel/Electricity Decimal Places** | Enter the number of decimal places that are shown for fuel/electricity amounts. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |
    | **Distance Decimal Places** | Enter the number of decimal places that are shown for distance measurements. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |
    | **Custom Amount Decimal Places** | Enter the number of decimal places that are shown for custom amounts. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |

5. On the **Reporting** FastTab, complete the setup by configuring the fields that are related to reporting to authorities.

    > [!NOTE]
    > In version 24.0, [!INCLUDE[prod_short](includes/prod_short.md)] doesn't support reporting to any authority. Therefore, the fields that are related to the configuration of this functionality on the **Reporting** FastTab are intended for future reporting capabilities. However, partners can also use these fields in localized versions.

    | Field | Description |
    |-------|-------------|
    | **Emission Reporting Unit of Measure Code** | Enter the unit of measure code that is used to report emissions, because you can use a different unit of measure when you report to authorities. This field isn't applicable to the standard reports. |
    | **Reporting UOM Factor** | Enter the unit of measure factor that is used to register emissions, if you use a different unit of measure when you report to authorities. |
    | **Emission Rounding Precision** | Enter the size of the interval that is used during rounding of emission amounts when you report to authorities. |
    | **Emission Rounding Type** | Choose how the program rounds emission amounts when you report to authorities. The following options are available: **Nearest**, **Up**, and **Down**. |

## Emission Fees   

To track internal carbon fees or calculate your emissions using carbon dioxide (CO2) equivalents, you need to configure the **Emission Fees** page. To set up this information, follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Emission Fees**, and then select the related link. 
2. In the **Emission Type** field, choose the GHG emission you want to configure: **CO2**, **CH4**, or **N2O**. This field is mandatory.   
3. You can also specify the **Scope Type**. If you leave this field blank, it  applies to all scopes, but you can configure it for each scope.  
4. You can configure **Starting Date** and **Ending Date**. This means that you can use different configurations for different periods. 
5. The **Country/Region Code** and **Responsibility Code** are optional fields that you can use if you want to have different carbon fees or carbon equivalent factors per country/region or per facility (responsibility center). 
6. The **Carbon Fee** field represents the internal carbon fee that a company charges itself for each unit of CO2 equivalent that it emits. You can use this field based on some local or regional regulations, or for internal calculations. Teh **Carbon Fee** is calculated every time when you post emissions and this information is visible on the **Sustainability Ledger Entries**, without any additional posting on **G/L Ledger**. You can set up **Carbon Fee** per unit of measure that you have in the **Sustainability Setup** and you can fill this field only for the line where the **Emission Type** is **CO2**. 
7. The **Carbon Equivalent Factor** specifies the coefficient that converts the impact of various greenhouse gases into the equivalent amount of carbon dioxide based on their global warming potential. If the **Emission Type** is CO2, the **Carbon Equivalent Factor** is always *1* and you can't modify this value, because CO2 is the reference gas used for calculating the global warming potential (GWP) of other greenhouse gases; since CO2 is the baseline, its GWP is set to *1*. For other GHG gases, you must configure the values manually. 
To calculate the carbon equivalent factor, you can use the following example: If we assume that 1 kilogram of N2O is equivalent to 298 kilograms of CO2, you need to divide 1 by 298 and the result you need to populate is 0.00336.  

> [!NOTE]
> The **Carbon Fee** field on the **Sustainability Ledger Entries** isn't calculated based on the **CO2 Emission** values. Instead, as a foundation for this formula, [!INCLUDE[prod_short](includes/prod_short.md)] uses the **CO2e Emission** field. The **CO2e Emission** field is calculated based on all the emissions posted to an entry and the **Carbon Equivalent Factor** configured for each of the gases on the **Emission Fees** page.  

If you didn't configure the **Emission Fees** before posting your sustainability entries, and you want to calculate your carbon fees and CO2e retroactively, you need to run the **Calculate Emission Fees** action to update values on the **Sustainability Ledger Entries**.  

## See also

- [Finance](finance.md)    
- [Sustainability management overview](finance-manage-sustainability.md)    
- [Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)    
- [Record sustainability entries](finance-sustainability-journal.md)    
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
