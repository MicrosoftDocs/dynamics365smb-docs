---
title: "Fiscal Inventory Valuation"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "fiscal inventory, about"
  - "inventory, fiscal value"
ms.assetid: 1aef1d4b-d371-4370-8691-3d3d7fdf67f5
caps.latest.revision: 35
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "it-it"
---
# Fiscal Inventory Valuation
You must submit an annual report that shows the monetary value of inventory items for the fiscal year. According to the Italian requirements for fiscal inventory valuation, you must calculate the following cost types:  
  
-   Year average cost  
  
-   Weighted average cost  
  
-   First in, First Out \(FIFO\) cost  
  
-   Last in, First Out \(LIFO\) cost  
  
-   Discrete LIFO cost  
  
## Fiscal Inventory Valuation in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]  
 Initially, you must set up the fiscal inventory valuation for all cost types in the **\($ N\_12137 Item Costing Setup $\)** window and the **\($ N\_30 Item Card $\)** window. For more information, see [How to: Set Up Fiscal Inventory Valuation](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-set-up-fiscal-inventory-valuation.md).  
  
 When you set up [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] for the first time, you must enter the inventory item ledger entries for the first year in order to calculate the item’s valuation. You can do this in the **\($ N\_12117 Before Start Item Cost $\)** window. For more information, see [How to: Set Up Initial Item Costs](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-set-up-initial-item-costs.md).  
  
 To calculate discrete LIFO cost, you must set up information in the **\($ N\_30 Item Card $\)** window and the **\($ N\_12156 Subcontracting Prices $\)** window.  
  
> [!NOTE]  
>  The discrete LIFO cost can only be calculated for items for which the **Inventory Valuation** is set to **Discrete LIFO** in the **\($ N\_30 Item Card $\)** window.  
  
 After you set up the discrete LIFO cost calculation, you can post sales and purchase transactions based on year\-end costs.  
  
### End of Year  
 At the end of the fiscal year, you can run the [\($ B\_12115 Calculate End Year Costs $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-b_12115-calculate-end-year-costs-$-.md) batch job to calculate the fiscal inventory value of each inventory item according to the required valuation methods. The results are shown in the [\($ N\_12118 Item Cost History List $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-n_12118-item-cost-history-list-$-.md) window. Then, you can run the **\($ R\_12135 Fiscal Inventory Valuation $\)** report and the **\($ R\_12137 LIFO Valuation $\)** report to show the inventory valuation.  
  
 For year\-end operations, such as calculating the profit and loss during a fiscal year, there is a definitive period and a non\-definitive period. If the **\($ T\_12131\_2 Competence Year $\)** field in the **\($ N\_12118 Item Cost History List $\)** window is equal to the fiscal year end date, it is a definitive period, and you cannot recalculate data for a definitive period. If the definitive data differs from the fiscal year end date, then it is a non\-definitive period. There should be data for at least one non\-definitive period to perform calculations or partial calculations.  
  
## See Also  
 [Italy Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/italy-local-functionality.md)   
 [How to: Set Up Fiscal Inventory Valuation](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-set-up-fiscal-inventory-valuation.md)   
 [How to: Set Up Initial Item Costs](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-set-up-initial-item-costs.md)   
 [\($ N\_12118 Item Cost History List $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-n_12118-item-cost-history-list-$-.md)   
 [\($ B\_12115 Calculate End Year Costs $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-b_12115-calculate-end-year-costs-$-.md)   
 [\($ N\_30 Item Card $\)](../Topic/\($%20N_30%20Item%20Card%20$\).md)   
 [\($ N\_12156 Subcontracting Prices $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-n_12156-subcontracting-prices-$-.md)   
 [\($ R\_12135 Fiscal Inventory Valuation $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-r_12135-fiscal-inventory-valuation-$-.md)   
 [\($ R\_12137 LIFO Valuation $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/-$-r_12137-lifo-valuation-$-.md)