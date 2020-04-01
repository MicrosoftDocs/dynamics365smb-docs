---
    title: Design Details - Demand and Supply | Microsoft Docs
    description: This topic introduces the concept of demand, which is the common term used for any kind of gross demand, such as a sales order and component need from a production order.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: design, demand, supply, inventory, planning
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Design Details: Demand at Blank Location
When a user creates a demand event, such as a sales order line, the program allows the user to sometimes specify a location code and other times not, that is, use blank location.

For demand with or without location codes, the planning system operates in a straight forward way when:

- Demand lines always carry location codes and the system fully uses SKUs, including the relevant location setup.
- Demand lines never carry location codes, and the system does not use SKUs or any location setup (see the last scenario in the following section).

However, if demand events sometimes have location codes and other times do not, the planning system will follow certain rules depending on setup.

## Demand at Location
When the planning system detects demand at a location, it will behave in different ways depending on three critical setup values. During a planning run, the system checks for three setup values in sequence and plans accordingly.

1. Is there a check mark in the **Location Mandatory** field?

    If yes, then:

2. Does SKU exist for the item?

    If yes, then:

    The item is planned according to planning parameters on the SKU card.

    If no, then:

3. Does the Components at Location field contain the demanded location code?

  If yes, then:

  The item is planned according to planning parameters on the item card.

  If no, then:

  The item is planned according to: Reordering Policy = Lot-for-Lot, Include Inventory = Yes, all other planning parameters = Empty, items using Reordering Policy = Order will remain using Order along with the other settings.

> [!NOTE]
> The exceptional planning setup that is output as the last reaction in step 3 above is referred to in the following as the “minimal alternative”. This planning setup only covers the exact demand, and all other planning parameters are ignored.

For information about variations of this planning logic, see the Scenarios section below.

## Demand at Blank Location
Even if the **Location Mandatory** field is selected, the program will allow demand lines to be created without a location code, also referred to as blank location. This is a deviation for the system because it has various setup values tuned to dealing with locations (see above) and as a result, the planning engine will not create a planning line for such a demand line.

If the **Location Mandatory** field is not selected but any of the location setup values exist, it is also considered a deviation, and the planning system will react by using the “minimal alternative”: The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.

## Scenarios
The following scenarios describe variations of demand at blank location and how the planning system resolves to the “minimal alternative.”

### Setup 1:
Location Mandatory = Yes

SKU is set up for RED

Components at Location = BLUE

#### Case 1.1: Demand is at RED location
The item is planned according to planning parameters on the SKU card.

#### Case 1.2: Demand is at BLUE location
The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.

#### Case 1.3: Demand is at GREEN location
The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.

#### Case 1.4: Demand is at BLANK location
The item is not planned because no location is defined on the demand line.

### Setup 2:
Location Mandatory = Yes

No SKU exists

Components at Location = BLUE

#### Case 2.1: Demand is at RED location
The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.

#### Case 2.2: Demand is at BLUE location
The item is planned according to planning parameters on the item card.

### Setup 3:
Location Mandatory = No

No SKU exists

Components at Location = BLUE

#### Case 3.1: Demand is at RED location
The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.

#### Case 3.2: Demand is at BLUE location
The item is planned according to planning parameters on the item card.

#### Case 3.3: Demand is at BLANK location
The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.

### Setup 4:
Location Mandatory = No

No SKU exists

Components at Location = BLANK

#### Case 4.1: Demand is at BLUE location
The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.

#### Case 4.2: Demand is at BLANK location
The item is planned according to planning parameters on the item card.

As illustrated in the last scenario, the only way to get a correct result for a demand line without a location code is to disable all setup values relating to locations. Similarly, the only way to get stable planning results for demand at locations is to use SKUs. Therefore, if companies often plan for demand at locations, they are strongly advised to use the Stockkeeping Units granule.

## See Also  
[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md)   
[Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md)   
[Design Details: Supply Planning](design-details-supply-planning.md)
