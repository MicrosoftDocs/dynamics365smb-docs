---
title: Set up sustainability features in Business Central
description: Learn how to configure the Sustainability module to track and report your greenhouse gas emissions and carbon fees.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, CSRD, equivalent, CO2e, CO2, carbon, water, waste, value chain, role center, fees
ms.search.form: 6221, 6235, 6245
ms.date: 01/28/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Set up sustainability features

To use the sustainability features effectively, you need to set up some basic controls and instructions. This article explains how to do that.

## Role Center  

If your primary responsibilities involve sustainability processes, we recommend that you use the **Sustainability Manager** Role Center. It gives easy access to the core features of sustainability, and the finance and procurement processes. It also shows the most important sustainability-related key performance indicators (KPIs).

To configure the Role Center, follow the steps:  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **My settings**, and then select the related link.
2. In the **Role** field, select the **Available Roles** page.
3. Choose **Sustainability Manager**.
4. Select **OK**.

## Sustainability setup  

Specify some general settings for sustainability, such as the unit of measure for emissions, the decimal places for amounts, and whether some fields are mandatory.

To configure these settings, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sustainability Setup**, and then select the related link.
2. On the **General** FastTab, configure the required fields that are related to sustainability.

    | Field | Description |
    |-------|-------------|
    | **Emission Unit of Measure Code** | Enter the unit of measure code that you use to register emissions. |
    | **Waste Unit of Measure Code** | Enter the the waste unit of measure code that you use to register waste intensity. |
    | **Water Unit of Measure Code** | Enter the water unit of measure code that you use to register water intensity. |
    | **Disch. Into Water Unit of Measure Code** | Enter the unit of measure code that you use to register discharged into water. |
    | **Emission Decimal Places** | Enter the number of decimal places that show for emission amounts. The default setting, *2:5*, means that a minimum of two decimal places and a maximum of five decimal places are shown for all amounts. You can also enter a fixed number. For example, if you enter *2*, two decimal places show for all amounts. |
    | **Country/Region Mandatory** | Make the country/region field mandatory. You can set the country/region field in journals even if you don't select this field. However, by selecting it, you require that users set the country/region field before posting. |
    | **Responsibility Center Mandatory** | Make the responsibility center mandatory. The responsibility center can be used as a facility, so that you can measure facility-based emissions. You can set the responsibility center field in journals even if you don't select this field. However, by selecting it, you require that users set the responsibility center field before posting. |
    | **Block Calculation Foundation Change If Ledger Entries Exist** | Prevent changes to the calculation foundation (formula) at the account category level when the formula was already applied to sustainability entries. |
    | **Enable Background Error Check** | Enable validations for sustainability journal lines. The validations run in the background. |

    > [!NOTE]
    > After you turn on or turn off validations in journals, sign in again before you start the new setup.

3. On the **Procurement** FastTab, configure the fields that are required to use sustainability features in the purchase process.  

    | Field | Description |
    |-------|-------------|
    | **Use Emissions In Purchase Documents** | Enable sustainability related fields and features to appear on purchase documents, such as **Sustainability Account** or different emissions. |
    | **Enable Value Chain tracking** | Enable posting of **Sustainability Value Entries** through value chain operations and the visibility of sustainability related fields in operational documents and journals. |
    | **G/L Account Emissions** | Enable a default **Sustainability Account** on the **G/L Account** card page. |
    | **Item Emissions** | Enable default **Sustainability Account** emissions on the **Item** card page. |
    | **Item Charge Emissions** | Enable default **Sustainability Account** emissions on the **Item Charge** (currently not operating) page. |
    | **Resource Emissions** | Enable default **Sustainability Account** emissions on the **Resource Card** page. |
    | **Work Machine Center Emissions** | Specifies the enablement of default **Sustainability Account** emissions on the **Work Center** and **Machine Center** pages. |

    > [!NOTE]
    > The **Use Emissions in Purchase Documents** field makes the **Sustainability Account** and emission fields on purchase documents. However, when you post the document, [!INCLUDE [prod_short](includes/prod_short.md)] only creates **Sustainability Ledger Entries**. To activate posting to the **Sustainability Value Entries** and enable value chain tracking, you must also select the **Enable Value Chain Tracking** field.

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

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Emission Fees**, and then select the related link. 
2. In the **Emission Type** field, choose the greenhouse gas (GHG) emission you want to configure: **CO2**, **CH4**, or **N2O**. This field is mandatory.
3. Specify the **Scope Type**. If you leave this field blank, it applies to all scopes, but you can configure it for each scope.  
4. Specify a **Starting Date** and **Ending Date**. These dates let you use different configurations for different periods.
5. The **Country/Region Code** and **Responsibility Code** are optional fields that you can use if you want to have different carbon fees or carbon equivalent factors per country/region or per facility (responsibility center).
6. The **Carbon Fee** field represents the internal carbon fee that a company charges itself for each unit of CO2 equivalent that it emits. You can use this field based on some local or regional regulations, or for internal calculations. The **Carbon Fee** is calculated every time you post emissions. This information displays on the **Sustainability Ledger Entries**, without more posting to the **G/L Ledger**. You can set up **Carbon Fee** per unit of measure that you have in the **Sustainability Setup**, and you can fill this field only for the line where the **Emission Type** is **CO2**.
7. The **Carbon Equivalent Factor** specifies the coefficient that converts the effect of various GHGs into the equivalent amount of carbon dioxide based on their global warming potential. If the **Emission Type** is CO2, the **Carbon Equivalent Factor** is always *1* and you can't modify this value because CO2 is the reference gas used for calculating the global warming potential (GWP) of other GHGs. Because CO2 is the baseline, its GWP is set to *1*. For other GHGs, you must configure the values manually.
To calculate the carbon equivalent factor, use the following example. If we assume that 1 kilogram of N2O is equivalent to 298 kilograms of CO2, divide 1 by 298. The result you need to add is 0.00336.  

> [!NOTE]
> The **Carbon Fee** field on the **Sustainability Ledger Entries** isn't calculated based on the **CO2 Emission** values. Instead, as a foundation for this formula, [!INCLUDE[prod_short](includes/prod_short.md)] uses the **CO2e Emission** field. The **CO2e Emission** field is calculated based on all emissions posted to an entry. The **Carbon Equivalent Factor** is configured for each of the gases on the **Emission Fees** page.  

> [!TIP]
> To use CO2e for all emissions (*CO2e of CO2*, *CO2e of CH4*, and *CO2e of N2O*), set the **Carbon Equivalent Factor** to **1** for the **CO2**, **CH4**, and **N2O** options. This setting gives you CO2e for all emissions, and the **CO2e** field displays the total carbon equivalent.  

If you didn't configure the **Emission Fees** before you posted sustainability entries, and you want to calculate your carbon fees and CO2e retroactively, run the **Calculate Emission Fees** action to update values on the sustainability ledger entries.  

## Responsibility Center

Use the **Responsibility Center** to post entries related to sustainability, where it represents a specific facility. However, if you want to use water management in sustainability, configure some additional information. You can set up your responsibility center as usual, and fill in the fields on the **Sustainability** FastTab as described in the following table.  

| Field | Description |
|-----------|----------------------------------|
| **Water Capacity Dimension** | Specifies the capacity dimension. For example, Area or Volume. |
| **Water Capacity Quantity (Month)** | Indicates the total water capacity quantity of the responsibility center. |
| **Water Capacity Unit** | Specifies the unit of measure that describes capacity quantity. |

## Related information

[Finance](finance.md)  
[Sustainability management overview](finance-manage-sustainability.md)  
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
