---
title: Set up sustainability features in Business Central
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

# Set up sustainability in Business Central

To use the sustainability features effectively, you need to set up some basic controls and instructions. This article explains how to do that.

## Role center  

If your primary responsibilities involve sustainability processes, we recommend that you use the **Sustainability Manager** Role Center. It gives easy access to the core features of sustainability, and the finance and procurement processes. It also shows the most important sustainability-related key performance indicators (KPIs).

To configure the Role Center, follow the steps:  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **My settings**, and then select the related link.
2. In the **Role** field, select the **Available Roles** page.
3. Choose **Sustainability Manager**.
4. Select **OK**.

## Sustainability setup  

Specify some general settings for sustainability, such as the unit of measure for emissions, the decimal places for amounts, and whether some fields are mandatory.

To configure these settings, follow these steps:

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sustainability Setup**, and then select the related link.
2. On the **General** FastTab, configure the required fields that are related to sustainability.

    | Field | Description |
    |-------|-------------|
    | **Emission Unit of Measure Code** | Enter the unit of measure code that you use to register emissions. |
    | **Emission Decimal Places** | Enter the number of decimal places that show for emission amounts. The default setting, *2:5*, means that a minimum of two decimal places and a maximum of five decimal places show for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places show for all amounts. |
    | **Country/Region Mandatory** | Require people to fill in the **Country/Region** field on journals before they can post. If you don't select this field, you can still specify a country/region in journals. |
    | **Responsibility Center Mandatory** | Require people to fill in the **Responsibility Center** field on journals before they can post. You can use a responsibility center as a facility, so that you can measure facility-based emissions. If you don't select this field, you can still specify a responsibility center in journals. |
    | **Block Calculation Foundation Change If Ledger Entries Exist** | Prevent people from changing the calculation foundation (formula) at the account category level if the formula was applied to sustainability entries. |
    | **Enable Background Error Check** | Enable [!INCLUDE [prod_short](includes/prod_short.md)] to validate sustainability journal lines in the background. |

    > [!NOTE]
    > After you turn on or turn off the background error check in journals, you must sign in again before you start the new setup.

3. On the **Procurement** FastTab, configure the required fields that are related to usage of sustainability features in the purchase process.  

    | Field | Description |
    |-------|-------------|
    | **Use Emissions In Purchase Documents** | If you enable this field, sustainability related fields and features are available on purchase documents, such as **Sustainability Account** field or various emissions. |

4. On the **Calculations** FastTab, configure the required fields for the formulas that calculate emissions.

    | Field | Description |
    |-------|-------------|
    | **Fuel/Electricity Decimal Places** | Enter the number of decimal places that show for fuel/electricity amounts. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places show for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places show for all amounts. |
    | **Distance Decimal Places** | Enter the number of decimal places that show for distance measurements. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places show for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places show for all amounts. |
    | **Custom Amount Decimal Places** | Enter the number of decimal places that show for custom amounts. The default setting, *2:5*, indicates that a minimum of two decimal places and a maximum of five decimal places show for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places show for all amounts. |

5. On the **Reporting** FastTab, complete the setup by configuring the fields that are related to reporting to authorities.

    > [!NOTE]
    > In version 24.0, [!INCLUDE[prod_short](includes/prod_short.md)] doesn't support reporting to any authorities. The fields that are related to the configuration of this functionality on the **Reporting** FastTab are intended for future reporting capabilities. However, partners can also use these fields in localized versions.

    | Field | Description |
    |-------|-------------|
    | **Emission Reporting Unit of Measure Code** | Enter the unit of measure code that you use to report emissions. You can use a different unit of measure when you report to authorities. This field isn't applicable to the standard reports. |
    | **Reporting UOM Factor** | Enter the unit of measure factor that you use to register emissions, if you use a different unit of measure when you report to authorities. |
    | **Emission Rounding Precision** | Enter the size of the interval that you use to round emission amounts when you report to authorities. |
    | **Emission Rounding Type** | Choose how to round emission amounts when you report to authorities. |

## Emission fees

To track internal carbon fees or calculate your emissions using carbon dioxide (CO2) equivalents, configure the **Emission Fees** page.  

1. Select the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Emission Fees**, and then select the related link.
2. In the **Emission Type** field, choose the GHG emission you want to configure. This field is mandatory.
3. You can also specify the **Scope Type**. If you leave this field blank, the fees apply to all scopes, but you can configure it for each scope.  
4. You can configure **Starting Date** and **Ending Date**. You can use different configurations for different periods.
5. The **Country/Region Code** and **Responsibility Code** are optional fields that you can use if you want to have different carbon fees or carbon equivalent factors per country/region or per facility (responsibility center).
6. The **Carbon Fee** field represents the internal carbon fee that a company charges itself for each unit of CO2 equivalent that it emits. You can use this field based on local or regional regulations, or for internal calculations. The carbon fee is calculated every time you post emissions. The information displays on the **Sustainability Ledger Entries** page, without a posting on **G/L Ledger**. You can set up a carbon fee for each unit of measure that you have on the **Sustainability Setup** page. You can fill in this field only for lines where the **Emission Type** field is set to **CO2**.
7. The **Carbon Equivalent Factor** field specifies the coefficient that converts the impact of various GHGs into the equivalent amount of carbon dioxide based on their global warming potential. If the **Emission Type** is **CO2**, the **Carbon Equivalent Factor** is always *1*. You can't change this value because CO2 is the reference gas used to calculate the global warming potential (GWP) of other GHGs. Because CO2 is the baseline, its GWP is set to **1**. For other GHGs, you must configure the values manually. Here's an example of how to calculate the carbon equivalent factor. If one kilogram of N2O is equivalent to 298 kilograms of CO2, you divide 1 by 298, and the result you need to populate is 0.00336.  

> [!NOTE]
> The **Carbon Fee** field on the **Sustainability Ledger Entries** isn't calculated based on the **CO2 Emission** values. Instead, as a foundation for this formula, [!INCLUDE[prod_short](includes/prod_short.md)] uses the **CO2e Emission** field. The **CO2e Emission** field is calculated based on all emissions posted to an entry. The **Carbon Equivalent Factor** is configured for each of the gases on the **Emission Fees** page.  

> [!TIP]
> To use CO2e for all emissions (*CO2e of CO2*, *CO2e of CH4*, and *CO2e of N2O*), set the **Carbon Equivalent Factor** field to **1** for all options - **CO2**, **CH4**, and **N2O**. This setting gives you CO2e for all emissions, and the **CO2e** field displays the total carbon equivalent.  

If you didn't configure emission fees before you post sustainability entries, and you want to calculate your carbon fees and CO2e retroactively, run the **Calculate Emission Fees** action to update the values on the sustainability ledger entries.  

## Related information

[Finance](finance.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
