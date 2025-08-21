---
title: Sustainability default data
description: Learn how to set up default sustainability values for your master data.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Sustainability, emission, GHG, CSRD, carbon, CO2, value chain
ms.search.form: 16, 30, 76, 5800, 99000754, 99000760
ms.date: 01/22/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Default data for sustainability

To simplify how you manage your sustainability accounts and emissions, you can create default values for the following entities:  

- **G/L Account** (only available default sustainability account)
- **Item** (available default sustainability account and emissions)
- **Resource** (available default sustainability account and emissions)
- **Work Center** (available default sustainability account and emissions)
- **Machine Center** (available default sustainability account and emissions)

> [!NOTE]
> Although you set default values, you can change them on journals and documents as needed. These values are simply defaults and aren't mandatory.  

## G/L accounts

To set up a default sustainability account for a G/L account, follow these steps:  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Chart of accounts**, and then select the related link.
2. In the **No.** field, choose the number for the account you want to configure to open the **G/L Account Card** page.  
3. On the **Sustainability** FastTab, use the **Default Sust. Account** field to select the sustainability account you want to use as the default.
4. Close the page.

## Items

For items, you can use the manually entered sustainability account, or use the default value you have on the **Item Category**. The following processes explain both options.

### Specify a default sustainability account for an item category

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Item categories**, and then select the related link.
2. In the **Code** field, choose the code for the category you want to configure to open the **Item Category Card** page.  
3. On the **Sustainability** FastTab, use the **Default Sust. Account** field to select the sustainability account you want to use as the default for the category.
4. Close the page.

### Specify default sustainability values for an item  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, and then select the related link.
2. Open the card for an item for which you want to set up default values.  
3. Add the default sustainability account:

   1. On the **Sustainability** FastTab, use the **Default Sust. Account** field to select the sustainability account you want to use as the default.  
   2. If you configured default sustainability accounts on item categories, select the **Item Category Code** you want to use on the **Item** FastTab. The default value for the category updates the value in **Default Sust. Account** field.

4. Fill in the following fields for default emissions for this item:

   1. **Default CO2 Emission**
   2. **Default CH4 Emission**  
   3. **Default N2O Emission**

   > [!NOTE]
   > You can add default emissions only if the **Replenishment System** is set to **Purchase**. For other options, you can only set up the **Default Sust. Account**. CO2e (carbon equivalent) is calculated based on your production or assembly processes. If you already filled in the emissions fields and then change the replenishment system to something other than **Purchase**, [!INCLUDE [prod_short](includes/prod_short.md)] deletes the existing emissions.

5. Run the **Calculate CO2e** action to calculate **CO2e per Unit** field if you're just setting up this item and you don't have earlier transactions. By default, this action updates this item only. However, you can change the filter and apply it to a different range of items.  

   > [!NOTE]
   > The calculation of CO2e (carbon equivalent) is based on the default emissions you specified for the item and your setup on the **Emission Fees** page.  

6. Close the page.

> [!NOTE]
> The information you enter for emissions and the calculated **CO2e per Unit** are overridden by the system's calculations for this item based on **Sustainability Value Entry**. This data comes from the **Posted Purchase Invoice** page, and uses the average method of emission calculation. Therefore, manually calculated **CO2e per Unit** is only used before posting documents with the correct values. This means you can use manual creation for data planning (**Production BOM**, **Assembly Order**, and so on) before you post the related document.  

## Resources

To set up default sustainability values for a resource, follow these steps:  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **resources**, and then select the related link.
2. Open the card for a resource for which you want to set up default values.
3. On the **Sustainability** FastTab, use the **Default Sust. Account** field to select the sustainability account to use as the default.  
4. Fill in the following fields for default emissions for the resource:

   1. **Default CO2 Emission**
   2. **Default CH4 Emission**  
   3. **Default N2O Emission**

5. Run the **Calculate CO2e** action to calculate the value in the **CO2e per Unit** field.

> [!NOTE]
> You must use the **Calculate CO2e** action to calculate the **CO2e per Unit** field because, unlike items, no other transactions affect these values. By default, this action updates this resource only. However, you can change the filter and apply it to a different range of resources.  

> [!NOTE]
> The calculation of CO2e (carbon equivalent) is based on the default emissions you specified for the resource and your setup on the **Emission Fees** page.  

6. Close the page.

## Work centers

To set up default sustainability values for a work center, follow these steps:  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Work centers**, and then select the related link.
2. Open the **Work Center Card** page for a work center for which you want to set up default values.  
3. On the **Sustainability** FastTab, use the **Default Sust. Account** field to select the sustainability account to use as the default.  
4. Fill in the following fields for default emissions for this work center:

   1. **Default CO2 Emission**
   2. **Default CH4 Emission**  
   3. **Default N2O Emission**

5. Run the **Calculate CO2e** action to calculate the value in the **CO2e per Unit** field.

> [!NOTE]
> You must use the **Calculate CO2e** action to calculate the **CO2e per Unit** field because, unlike items, no other transactions affect these values. By default, this action updates this work center only. However, you can change the filter and apply it to a different range of work centers.  

> [!NOTE]
> The calculation of CO2e (carbon equivalent) is based on the default emissions you specified for this work center and your setup on the **Emission Fees** page.  

7. Close the page.

> [!NOTE]
> You can also run the **Calculate CO2e** action from the **Work Centers** list page. You can also apply this action to machine centers.  

## Machine centers

To set up default sustainability values for a machine center, follow these steps:  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Machine centers**, and then select the related link.
2. Open the **Machine Center Card** for a machine center for which you want to set up default values.  
3. On the **Sustainability** FastTab, use the **Default Sust. Account** field to select the sustainability account to use as the default.  
4. Fill in the following fields for default emissions for this machine center:

   1. **Default CO2 Emission**
   2. **Default CH4 Emission**  
   3. **Default N2O Emission**

5. Run the **Calculate CO2e** action to calculate **CO2e per Unit** field.

> [!NOTE]
> You must use the **Calculate CO2e** action to calculate the **CO2e per Unit** field because, unlike items, no other transactions affect these values. By default, this action updates this machine center only. However, you can change the filter and apply it to a different range of machine centers.  

> [!NOTE]
> The calculation of CO2e (carbon equivalent) is based on the default emissions you specified for this machine center and your setup on the **Emission Fees** page.  

6. Close the page.

> [!NOTE]
> You can also run the **Calculate CO2e** action from the **Machine Centers** list page. You can also apply this action to work centers.  

## Related information  

[Sustainability Management overview](finance-manage-sustainability.md)  
[Sustainability Value Chain overview](value-chain-howto-overview.md)  
[Sustainability setup](finance-sustainability-setup.md)  
[Chart of sustainability accounts and ledger](finance-sustainability-accounts-ledger.md)  
[Record sustainability entries](finance-sustainability-journal.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
