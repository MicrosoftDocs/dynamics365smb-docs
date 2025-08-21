---
title: Sustainability value chain setup
description: Learn how to enable the sustainability value chain.
author: altotovi
ms.topic: install-set-up-deploy
ms.devlang: al
ms.search.keywords: Sustainability, scope 3, emission, GHG, CSRD, carbon, CO2, CO2e, value chain, setup
ms.search.form: 6221, 6245
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
---

# Sustainability value chain setup

To use the sustainability value chain features effectively, you need to set up some basic controls and instructions. This article explains how to do that.

## Sustainability setup  

You need to specify some settings for the sustainability value chain functionality, such as enabling the value chain features to work with sustainability features, and the areas you'll use and track.  

To configure these settings, follow these steps:  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sustainability Setup**, and then select the related link.
2. Check whether the basic setup already exists. If it doesn't, follow [these instructions](finance-sustainability-setup.md) to set it up.  
3. On the **Procurement** FastTab, configure the fields related to the sustainability value chain. The following table describes the fields.

    | Field | Description |
    |-------|-------------|
    | **Enable Value Chain tracking** | Enable sustainability value entries posting through the value chain operations, and the availability of these fields in operational documents and journals. If you don't enable this field, sustainability features aren't available on operational documents, orders, or journals. |
    | **G/L Account Emissions** | Enable a default sustainability account on the **G/L Account Card** page. |
    | **Item Emissions** | Enable a default sustainability account and emissions on the **Item Card** page. |
    | **Item Charge Emissions** | Enable a default sustainability account on the **Item Charge** page.</br></br> **Important:** This field isn't currently supported. |
    | **Resource Emissions** | Enable a default sustainability account and emissions on the **Resource Card** page. |
    | **Work Machine Center Emissions** | Enable a default sustainability account and emissions on the **Work Center** and **Machine Center** pages. |

> [!NOTE]
> Keep in mind that selecting the **Use Emissions In Purchase Documents** field doesn't activate the sustainability value chain features. The field only enables you to record emissions in purchase documents. If you want to use purchase documents in value chain operations, you must also select the **Enable Value Chain tracking** field.  

> [!NOTE]
> The **Item Charge** functionality currently isn't supported in the sustainability value chain process. We plan to add this feature in 2025 release wave 2.  

## Emission fees  

To use the sustainability value chain features, you must configure carbon dioxide equivalents (CO2e). The value chain works only for CO2e, and not each type of greenhouse gas (GHG). You set up CO2e on the **Emission Fees** page.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Emission Fees**, and then select the related link.
2. In the **Emission Type** field, choose the GHG emission you want to configure. This field is mandatory.
3. The **Carbon Equivalent Factor** field specifies the coefficient that converts the effect of various GHGs into the equivalent amount of carbon dioxide based on their global warming potential (GWP). If the **Emission Type** is **CO2**, the **Carbon Equivalent Factor** is always **1**. You can't change this value because CO2 is the reference gas used to calculate the GWP of other greenhouse gases. Because CO2 is the baseline, its GWP is set to **1**. For other GHGs, you must configure the values manually.  

> [!NOTE]
> The following example shows how to calculate the carbon equivalent factor. If we assume that 1 kilogram of N2O is equivalent to 298 kilograms of CO2, divide 1 by 298. The result you need to enter is 0.00336.  

To learn how track internal carbon fees or use other features related to carbon dioxide equivalents (CO2e), go to [Set up sustainability in Business Central](finance-sustainability-setup.md).

## Related information  

[Sustainability Value Chain overview](value-chain-howto-overview.md)  
[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
