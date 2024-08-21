---
title: Sustainability setup
description: Learn how to set up sustainability features.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, equivalent, CO2e, CO2, carbon, role center, fees
ms.search.form: 6221, 6235, 6245
ms.date: 05/08/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Sustainability module setup 

Before the Sustainability module can work correctly, you must set up some basic controls and instructions that are related to the whole functionality.

To set up the Sustainability module, follow the steps:

## Role center  

For individuals whose primary responsibilities involve sustainability processes, it is recommended to utilize the **Sustainability Manager** role center. To configure this role center, follow the steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **My settings**, and then select the related link.
2. From the **Role** field, point to the **Available Roles** page.
3. Choose the **Sustainability Manager** line
4. Click **OK**.

The **Sustainability Manager** role center facilitates efficient management of all key areas related to sustainability. It encompasses core sustainability features, as well as finance and procurement processes. Additionally, it provides visibility into the most critical sustainability-related KPIs.

## Sustainability setup  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link.
2. On the **General** FastTab, configure the required fields that are related to the Sustainability module.

    | Field | Description |
    |-------|-------------|
    | **Emission Unit of Measure Code** | Specify the unit of measure code that is used to register emissions. |
    | **Emission Decimal Places** | Specify the number of decimal places that are shown for emission amounts. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |
    | **Country/Region Mandatory** | Specify whether the country/region is mandatory. Users can set the country/region field in journals even if you don't select this field. However, by selecting it, you require that users set the country/region field before posting. |
    | **Responsibility Center Mandatory** | Specify whether the responsibility center is mandatory. The responsibility center can be used as a facility, so that you can measure facility-based emissions. Users can set the responsibility center field in journals even if you don't select this field. However, by selecting it, you require that users set the responsibility center field before posting. |
    | **Block Calculation Foundation Change If Ledger Entries Exist** | Specify whether changes to the calculation foundation (formula) at the account category level are blocked at the time of sustainability entry, when the formula has already been applied. |
    | **Enable Background Error Check** | Specify whether the background error check of sustainability journal lines is enabled. |

    > [!NOTE]
    > After you enable or turn off the background error check in journals, you must sign in again before you start the new setup.

3. On the **Procurement** FastTab, configure the required fields that are related to usage of sustainability features in the purchase process.  

    | Field | Description |
    |-------|-------------|
    | **Use Emissions In Purchase Documents** | If you enable this field, sustainability related fields and features will appear in the purchase documents, such as **Sustainability Account** or different emissions. |

4. On the **Calculations** FastTab, configure the required fields that are related to the formulas that are used to calculate emissions.

    | Field | Description |
    |-------|-------------|
    | **Fuel/Electricity Decimal Places** | Specify the number of decimal places that are shown for fuel/electricity amounts. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |
    | **Distance Decimal Places** | Specify the number of decimal places that are shown for distance measurements. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |
    | **Custom Amount Decimal Places** | Specify the number of decimal places that are shown for custom amounts. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |

5. On the **Reporting** FastTab, complete the setup by configuring the fields that are related to reporting to authorities.

    > [!NOTE]
    > In version 24.0, [!INCLUDE[prod_short](includes/prod_short.md)] doesn't support reporting to any authority. Therefore, the fields that are related to the configuration of this functionality on the **Reporting** FastTab are intended for future reporting capabilities. However, partners can also use these fields in localized versions.

    | Field | Description |
    |-------|-------------|
    | **Emission Reporting Unit of Measure Code** | Specify the unit of measure code that is used to report emissions, because you can use a different unit of measure when you report to authorities. This field isn't applicable to the standard reports. |
    | **Reporting UOM Factor** | Specify the unit of measure factor that is used to register emissions, if you use a different unit of measure when you report to authorities. |
    | **Emission Rounding Precision** | Specify the size of the interval that is used during rounding of emission amounts when you report to authorities. |
    | **Emission Rounding Type** | Specify how the program rounds emission amounts when you report to authorities. The following options are available: **Nearest**, **Up**, and **Down**. |

## Emission Fees   

To track internal carbon fees or calculate your emissions using carbon dioxide (CO2) equivalents, you need to configure the **Emission Fees** page. To set up this information, follow these steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Emission Fees**, and then select the related link. 
2. In the **Emission Type** field, choos the GHG emission you want to configure: CO2, CH4, or N2O. This option is mandatory.   
3. You can firther specify the **Scope Type**. If you leave this field blank it will apply to all scopes, but you can configure it per scope.  
4. You can configure **Starting Date** and **Ending Date**. That particullary means you can use different configurations for different period. 
5. The **Country/Region Code** and **Responsibility Code** are optional fields and you can choose if you want to use them. These fields can be useful as this is possible to have different carbon fee per country or to use different conversions to the CO2e per country or facility (reponsibility center).  
6. The **Carbon Fee** field represents the internal carbon fee that a company charges itself for each unit of CO2 equivalent that it emits. It can be used based on some local or regional regulations, but also for internal calculation. **Carbon Fee** will be calculated every time when you post emissions and this information will be visible in the **Sustainability Ledger Entries**, without any additional posting in i.e. **G/L Ledger**. You can set up **Carbon Fee** per unit of measure  you have in the **Sustainability Setup** and it can be populated only for the line where the **Emission Type** is **CO2**. 
7. The **Carbon Equivalent Factor** specifies the coefficient that converts the impact of various greenhouse gases into the equivalent amount of carbon dioxide based on their global warming potential. If the **Emission Type** is CO2, the **Carbon Equivalent Factor** will always be 1 and you cannot modify this value, because CO2 is the reference gas used for calculating the global warming potential (GWP) of other greenhouse gases; since CO2 is the baseline, its GWP is set to 1. For other GHG gases, user must configure vale manually. To make proper calculation you can use the following example: If we assume that 1 kilogram of N2O is equivalent to 298 kilograms of CO2, you need to calculate 1/298 and the result you need to populate will be 0.00336.  

> [!NOTE]
> Carbon Fee field in the **Sustainability Ledger Entries** will not be calculated based on the **CO2 Emission** values. Instead of that as foundation for this formula Business Central will use the **CO2e Emission** field. **CO2e Emission** field will be calculated based on all emissions posted to entry and the **Carbon Equivalent Factor** configured for each of gases in the **Emission Fees** page.  

If you didn't configure **Emission Fees** before you started with posting your sustainability entries and you want to calculate your carbon fees and CO2e retroactively, you need to run the **Calculate Emission Fees** action to update values in the **Sustainability Ledger Entries**.  

## See also

[Finance](finance.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
