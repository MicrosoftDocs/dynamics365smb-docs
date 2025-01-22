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

