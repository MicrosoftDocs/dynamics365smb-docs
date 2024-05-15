---
title: Sustainability setup
description: Learn how to set up sustainability features.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD
ms.search.form: 
ms.date: 05/08/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Sustainability setup

Before the Sustainability module can work correctly, you must set up some basic controls and instructions that are related to the whole functionality.

To set up the Sustainability module, follow the steps:

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

3. On the **Calculations** FastTab, configure the required fields that are related to the formulas that are used to calculate emissions.

    | Field | Description |
    |-------|-------------|
    | **Fuel/Electricity Decimal Places** | Specify the number of decimal places that are shown for fuel/electricity amounts. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |
    | **Distance Decimal Places** | Specify the number of decimal places that are shown for distance measurements. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |
    | **Custom Amount Decimal Places** | Specify the number of decimal places that are shown for custom amounts. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places are shown for all amounts. |

4. On the **Reporting** FastTab, complete the setup by configuring the fields that are related to reporting to authorities.

    > [!NOTE]
    > In version 24.0, [!INCLUDE[prod_short](includes/prod_short.md)] doesn't support reporting to any authority. Therefore, the fields that are related to the configuration of this functionality on the **Reporting** FastTab are intended for future reporting capabilities. However, partners can also use these fields in localized versions.

    | Field | Description |
    |-------|-------------|
    | **Emission Reporting Unit of Measure Code** | Specify the unit of measure code that is used to report emissions, because you can use a different unit of measure when you report to authorities. This field isn't applicable to the standard reports. |
    | **Reporting UOM Factor** | Specify the unit of measure factor that is used to register emissions, if you use a different unit of measure when you report to authorities. |
    | **Emission Rounding Precision** | Specify the size of the interval that is used during rounding of emission amounts when you report to authorities. |
    | **Emission Rounding Type** | Specify how the program rounds emission amounts when you report to authorities. The following options are available: **Nearest**, **Up**, and **Down**. |

## See also

[Finance](finance.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
