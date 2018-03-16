---
    title: Fiscal Inventory Valuation
    description: You must submit an annual report that shows the monetary value of inventory items for the fiscal year.

    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Fiscal Inventory Valuation
You must submit an annual report that shows the monetary value of inventory items for the fiscal year. According to the Italian requirements for fiscal inventory valuation, you must calculate the following cost types:  

- Year average cost  
- Weighted average cost  
- First in, First Out (FIFO) cost  
- Last in, First Out (LIFO) cost  
- Discrete LIFO cost  

## Fiscal Inventory Valuation in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]  
Initially, you must set up the fiscal inventory valuation for all cost types in the **Item Costing Setup** window and the **Item Card** window. For more information, see [Set Up Fiscal Inventory Valuation](how-to-set-up-fiscal-inventory-valuation.md).  

When you set up [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you must enter the inventory item ledger entries for the first year in order to calculate the item’s valuation. You can do this in the Before Start Item Cost window.  

To calculate discrete LIFO cost, you must set up information in the **Item Card** window and the **Subcontracting Prices** window.

> [!NOTE]  
>  The discrete LIFO cost can only be calculated for items for which the **Inventory Valuation** field is set to **Discrete LIFO** in the **Item Card** window.

After you set up the discrete LIFO cost calculation, you can post sales and purchase transactions based on year-end costs.  

## End of Year  
 At the end of the fiscal year, you can run the Calculate End Year Costs batch job to calculate the fiscal inventory value of each inventory item according to the required valuation methods. The results are shown in the Item Cost History List window. Then, you can run the **Fiscal Inventory Valuation** report and the **LIFO Valuation** report to show the inventory valuation.  

 For year-end operations, such as calculating the profit and loss during a fiscal year, there is a definitive period and a non-definitive period. If the **Competence Year** field in the **Item Cost History List** window is equal to the fiscal year end date, it is a definitive period, and you cannot recalculate data for a definitive period. If the definitive data differs from the fiscal year end date, then it is a non-definitive period. There should be data for at least one non-definitive period to perform calculations or partial calculations.

## See Also  
 [Italy Local Functionality](italy-local-functionality.md)   
 [Set Up Fiscal Inventory Valuation](how-to-set-up-fiscal-inventory-valuation.md)   
 [Set Up Initial Item Costs](how-to-set-up-initial-item-costs.md)
