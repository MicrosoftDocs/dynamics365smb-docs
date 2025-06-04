---
title: Fiscal Inventory Valuation
description: Submit an annual report detailing the monetary value of inventory items for the fiscal year.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: submit annual report, monetary value, inventory items, fiscal inventory valuation
ms.search.form: 12117, 12188, 12128, 12130, 12137
ms.date: 05/20/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Fiscal inventory valuation

You must submit an annual report that shows the monetary value of inventory items for the fiscal year. According to the Italian requirements for fiscal inventory valuation, you must calculate the following cost types:  

- Year average cost  
- Weighted average cost  
- First in, First Out (FIFO) cost  
- Last in, First Out (LIFO) cost  
- Discrete LIFO cost  

## Fiscal inventory valuation in [!INCLUDE[prod_short](../../includes/prod_short.md)]

Initially, you must set up the fiscal inventory valuation for all cost types on the **Item Costing Setup** page and the **Item Card** page. Learn more in [Set Up Fiscal Inventory Valuation](how-to-set-up-fiscal-inventory-valuation.md).  

When you set up [!INCLUDE[prod_short](../../includes/prod_short.md)], you must enter the inventory item ledger entries for the first year in order to calculate the item’s valuation. You can do this in the **Before Start Item Cost** page.  

To calculate discrete LIFO cost, you must set up information on the **Item Card** page and the **Subcontracting Prices** page.

> [!NOTE]  
> The discrete LIFO cost can only be calculated for items for which the **Inventory Valuation** field is set to **Discrete LIFO** on the **Item Card** page.

After you set up the discrete LIFO cost calculation, you can post sales and purchase transactions based on year-end costs.  

## End of year

At the end of the fiscal year, you can run the **Calculate End Year Costs** batch job to calculate the fiscal inventory value of each inventory item according to the required valuation methods. The results are shown in the **Item Cost History List** page. Then, you can run the **Fiscal Inventory Valuation** report and the **LIFO Valuation** report to show the inventory valuation.  

For year-end operations, such as calculating the profit and loss during a fiscal year, there's a definitive period and a non-definitive period. If the **Competence Year** field on the **Item Cost History List** page is equal to the fiscal year end date, it's a definitive period, and you can't recalculate data for a definitive period. If the definitive data differs from the fiscal year end date, then it's a non-definitive period. There should be data for at least one non-definitive period to perform calculations or partial calculations.

## Related information

- [Italy Local Functionality](italy-local-functionality.md)  
- [Set Up Fiscal Inventory Valuation](how-to-set-up-fiscal-inventory-valuation.md)  
- [Set Up Initial Item Costs](how-to-set-up-initial-item-costs.md)  
- [Closing Years and Periods](../../year-close-years-periods.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
