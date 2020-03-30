---
    title: Planning With or Without Locations | Microsoft Docs
    description: Planning with or without location codes on demand lines is important to understand.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Planning With or Without Locations
Concerning planning with or without location codes on demand lines, the planning system operates in a straight forward way when:  

-   demand lines always carry location codes and the system fully uses stockkeeping units, including the relevant location setup.  
-   demand lines never carry location codes and the system does not use SKUs or any location setup (see last scenario below).  

However, if demand lines sometimes have location codes and other times do not, the planning system will follow certain rules depending on setup.  

## Demand at Location  
When the planning system detects demand at a location (a line with a location code), it will behave in different ways depending on 3 critical setup values.  

During a planning run, the system checks for the 3 setup values in sequence and plans accordingly:  

1.  Is there a check mark in the **Location Mandatory** field?  

    If yes, then:  

2.  Does SKU exist for the item?  

    If yes, then:  

    The item is planned according to planning parameters on the SKU card.  

    If no, then:  

3.  Does the **Components at Location** field contain the demanded location code?  

    If yes, then:  

    The item is planned according to planning parameters on the item card.  

    If no, then:  

    The item is planned according to: Reordering Policy =  *Lot-for-Lot*, Include Inventory =  *Yes*, all other planning parameters = Empty. (Items using reordering policy  *Order* remain using  *Order* as well as the other settings.)  

> [!NOTE]  
>  This minimal alternative only covers the exact demand. Any planning parameters defined are ignored.  

See variations in the scenarios below.  

## Demand at "Blank Location"  
Even if the **Location Mandatory** check box is selected, the system will allow demand lines to be created without a location code – also referred to as *BLANK* location. This is a deviation for the system because it has various setup values tuned to dealing with locations (see above) and as a result, the planning engine will not create a planning line for such a demand line. If the **Location Mandatory** field is not selected but any of the location setup values exist, then that is also considered a deviation and the planning system will react by outputting the "minimal alternative":   
The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains *Order)*, Include Inventory =  *Yes*, all other planning parameters = Empty.  

See variations in the setup scenarios below.  

### Setup 1:  

-   Location Mandatory = *Yes*  
-   SKU is set up for  *RED*  
-   Component at Location =  *BLUE*  

#### Case 1.1: Demand is at  *RED* location  

The item is planned according to planning parameters on the SKU card (including possible transfer).  

#### Case 1.2: Demand is at  *BLUE* location  

The item is planned according to planning parameters on the item card.  

#### Case 1.3: Demand is at  *GREEN* location  

The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains  *Order*), Include Inventory =  *Yes*, all other planning parameters = Empty.  

#### Case 1.4: Demand is at  *BLANK* location  

The item is not planned because no location is defined on the demand line.  

### Setup 2:  

-   Location Mandatory = *Yes*  
-   No SKU exists  
-   Component at Location =  *BLUE*  

#### Case 2.1: Demand is at  *RED* location  

The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains  *Order*), Include Inventory =  *Yes*, all other planning parameters = Empty.  

#### Case 2.2: Demand is at  *BLUE* location  

The item is planned according to planning parameters on the item card.  

### Setup 3:  

-   Location Mandatory = *No*  
-   No SKU exists  
-   Component at Location =  *BLUE*  

#### Case 3.1: Demand is at  *RED* location  

The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains  *Order*), Include Inventory =  *Yes*, all other planning parameters = Empty.  

#### Case 3.2: Demand is at  *BLUE* location  

The item is planned according to planning parameters on the item card.  

#### Case 3.3: Demand is at  *BLANK* location  

The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains  *Order*), Include Inventory =  *Yes*, all other planning parameters = Empty.  

### Setup 4:  

-   Location Mandatory = *No*  
-   No SKU exists  
-   Component at Location =  *BLANK*  

#### Case 4.1: Demand is at  *BLUE* location  

The item is planned according to: Reordering Policy =  *Lot-for-Lot* ( *Order* remains  *Order*), Include Inventory =  *Yes*, all other planning parameters = Empty.  

#### Case 4.2: Demand is at  *BLANK* location  

The item is planned according to planning parameters on the item card.  

As you can see from the last scenario, the only way to get a correct result for a demand line without a location code is to disable all setup values relating to locations. Similarly, the only way to get stable planning results for demand at locations is to use stockkeeping units.  

Therefore, if you often plan for demand at locations, it is strongly advised to use the Stockkeeping Units feature.  

## See Also
[Planning](production-planning.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Manufacturing](production-manage-manufacturing.md)    
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Design Details: Supply Planning](design-details-supply-planning.md)   
[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
