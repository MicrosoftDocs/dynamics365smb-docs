---
title: Set Up Online Maps
description: Learn how to configure Business Central to offer directions and location information with an online map service.
author: brentholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.search.form: 800, 804
ms.date: 07/15/2022
ms.author: bholtorf
ms.reviewer: bholtorf
---
# Set Up Online Maps

When you plan a visit to an address saved on a card, such as a customer, you can get a map from an online service with route directions described in the language you select. To make sure this online map service finds the right map and directions, you need to set it up in [!INCLUDE[prod_short](includes/prod_short.md)].

## Set up the online map feature

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Online Map Setup**,  then choose the related link.
2. On the **Online Map Setup** page, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
3. Turn on the **Enabled** toggle.

### Customize the online map provider features

To customize the online map feature beyond the options listed on the **Online Map Setup** page, or to use a different map provider, follow these steps:

1. On the **Online Map Setup** page, choose the **Parameter Setup** action.
2. On the **Online Map Parameter Setup** page, choose the **New** action.
3. Fill in the fields to customize how [!INCLUDE[prod_short](includes/prod_short.md)] will generate the URLs for the available services. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
   * Refer to the **Online Map Substitution Parameter** list on the **FactBox** pane for the data available to generate URLs.

## Related information

[Use Online Maps to Find Locations and Directions](across-online-maps.md)  
[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
