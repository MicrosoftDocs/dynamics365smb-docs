---
title: Planning With or Without Locations
description: In this topic learn about production and manufacturing, including supply planning, in Business Central.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 09/15/2022
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Planning With or Without Locations

Before you start utilizing planning engine, we recommend deciding about whether or not to use locations. There are two main straightforward ways:

* demand lines always carry location codes and the system fully uses stockkeeping units, including the relevant location setup. Learn more at [Demand at location](#demand-at-location).  
* demand lines never carry location codes and the system uses the item card. See the [Demand at a "blank location"](#demand-at-blank-location) scenario below.

## Demand at location  

When the planning system detects demand at a location (a line with a location code), it will behave in different ways depending on 2 critical setup values.  

During a planning run, the system checks for the 2 setup values in sequence and plans accordingly:  

1. Does a SKU exist for the item on the demanded location?  

    If yes, then:  

    The item is planned according to planning parameters on the SKU card.  

    If no, then:  

2. Does the **Components at Location** field in the **Manufacturing Setup** page contain the demanded location code?  

    If yes, then:  

    The item is planned according to planning parameters on the item card.  

    If no, then:  

    The item is planned according to the "minimal alternative" which covers the exact demand. The planning parameters are set as: Reordering Policy = *Lot-for-Lot*, Include Inventory = *Yes*, all other planning parameters = Empty. (Items using reordering policy *Order* remain using *Order* as well as the other settings.)

> [!TIP]
> If you often plan for demand at different locations, then we recommend that you use the stockkeeping units capability and avoid demand on blank location. Learn more at [Set Up Stockkeeping Units](inventory-how-to-set-up-stockkeeping-units.md)

See variations in the [scenarios below](#scenarios).

> [!NOTE]
> The **Components at Location** field in the **Manufacturing Setup** page are very important in governing how the planning system handles production demand lines.
>
> For production demand, [!INCLUDE [prod_short](includes/prod_short.md)] will use the same location for subassembly and components as the one stated on the production order. However, by filling in this field, you can redirect the subassembly and components to another location.
>
> You can also define this for a specific SKU by selecting a different location code in the **Components at Location** field on the SKU card. Note, however, that this rarely makes sense as the planning logic may be distorted when planning for the SKU component.

## Demand at "blank location"

In general, when the planning system detects demand at a blank location (a line without a location code), the item is planned according to planning parameters on the item card.

The **Locations Mandatory** field in the **Inventory Setup** page, the **Components at Location** field in the **Manufacturing Setup** page, or stockkeeping units will affect how the planning system handles demand lines with/without location codes. If one of following statements is true, the demand on blank location is also considered a deviation and the planning system will react by outputting the "minimal alternative": The item is planned according to: Reordering Policy = *Lot-for-Lot* (*Order* remains *Order*), Include Inventory = *Yes*, all other planning parameters = Empty.

* The **Components at Location** field in the **Manufacturing Setup** page has a value.
* A stockkeeping unit exists for the planned item.
* The **Location Mandatory** field is selected.

## Scenarios

See variations in the setup scenarios below.

### Setup 1

* Location Mandatory = *Yes*  
* SKU is set up for *WEST*  
* Component at Location = *EAST*  

#### Case 1.1: Demand is at *WEST* location

The item is planned according to planning parameters on the SKU card (including possible transfer).

#### Case 1.2: Demand is at *EAST* location

The item is planned according to planning parameters on the item card.

#### Case 1.3: Demand is at *MAIN* location

The item is planned according to: Reordering Policy = *Lot-for-Lot* (*Order* remains *Order*), Include Inventory = *Yes*, all other planning parameters = Empty.

#### Case 1.4: Demand is at *BLANK* location

The item is planned according to: Reordering Policy = *Lot-for-Lot* (*Order* remains *Order*), Include Inventory = *Yes*, all other planning parameters = Empty.

### Setup 2

* Location Mandatory = *Yes*  
* No SKU exists  
* Component at Location = *EAST*  

#### Case 2.1: Demand is at *WEST* location

The item is planned according to: Reordering Policy = *Lot-for-Lot* (*Order* remains *Order*), Include Inventory = *Yes*, all other planning parameters = Empty.

#### Case 2.2: Demand is at *EAST* location

The item is planned according to planning parameters on the item card.  

### Setup 3

* Location Mandatory = *No*  
* No SKU exists  
* Component at Location = *EAST*  

#### Case 3.1: Demand is at *WEST* location

The item is planned according to: Reordering Policy = *Lot-for-Lot* (*Order* remains *Order*), Include Inventory = *Yes*, all other planning parameters = Empty.

#### Case 3.2: Demand is at *EAST* location

The item is planned according to planning parameters on the item card.  

#### Case 3.3: Demand is at *BLANK* location

The item is planned according to: Reordering Policy = *Lot-for-Lot* (*Order* remains *Order*), Include Inventory = *Yes*, all other planning parameters = Empty.

### Setup 4

* Location Mandatory = *No*  
* No SKU exists  
* Component at Location = *BLANK*  

#### Case 4.1: Demand is at *EAST* location

The item is planned according to: Reordering Policy = *Lot-for-Lot* (*Order* remains *Order*), Include Inventory = *Yes*, all other planning parameters = Empty.

#### Case 4.2: Demand is at *BLANK* location

The item is planned according to planning parameters on the item card.

As you can see from the last scenario, the only way to get a correct result for a demand line without a location code is to disable all setup values relating to locations. Similarly, the only way to get stable planning results for demand at locations is to use stockkeeping units.  

Therefore, if you often plan for demand at locations, then we recommend that you use the Stockkeeping Units capability.

## Related information

[Planning](production-planning.md)  
[Set Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Inventory](inventory-manage-inventory.md)  
[Set Up Stockkeeping Units](inventory-how-to-set-up-stockkeeping-units.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)  
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
