---
title: Fiscal Inventory Valuation in Italy
description: Learn how to calculate fiscal inventory costs in the Italian version of Business Central, review cost history, and finalize year-end valuations.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: submit annual report, monetary value, inventory items, fiscal inventory valuation
ms.search.form: 12117, 12188, 12128, 12130, 12137
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Fiscal inventory valuation

You must submit an annual report that shows the monetary value of inventory items for the fiscal year. The Italian functionality supports the following cost types:

- Year average cost  
- Weighted average cost  
- First in, First Out (FIFO) cost  
- Last in, First Out (LIFO) cost  
- Discrete LIFO cost  

## Set up fiscal inventory valuation

Set up component valuation on **Item Costing Setup**, and select the required **Inventory Valuation** method on each item card. Learn more in [Set Up Fiscal Inventory Valuation](how-to-set-up-fiscal-inventory-valuation.md).

If you need historical quantities and costs from before you started using [!INCLUDE[prod_short](../../includes/prod_short.md)], enter them on **Before Start Item Cost**. These records provide input to fiscal cost calculations; they don't create item ledger entries.

For discrete LIFO valuation, configure the **Inventory Valuation** and **Lifo Category** fields on the item card.

> [!NOTE]  
> The discrete LIFO cost can only be calculated for items for which the **Inventory Valuation** field is set to **Discrete LIFO** on the **Item Card** page.

Fiscal valuation is calculated from the recorded inventory and production data. It doesn't replace the normal posting of sales and purchase transactions.

## End of year

At the end of the fiscal year, you can run the **Calculate End Year Costs** batch job to calculate the fiscal inventory value of each inventory item according to the required valuation methods. The results are shown in the **Item Cost History List** page. Then, you can run the **Fiscal Inventory Valuation** report and the **LIFO Valuation** report to show the inventory valuation.  

In **Calculate End Year Costs**, enter the **Reference Date** for the calculation. Select **Definitive** only for final year-end costs. A definitive run requires the reference date to be the fiscal year-end date.

The **Competence Year** in the cost history records the reference date. The **Definitive** field, not the date alone, identifies final results. A new calculation replaces nondefinitive cost history for the fiscal year. Existing definitive results prevent recalculation for the same or an earlier reference date.

## Related information

- [Italy Local Functionality](italy-local-functionality.md)  
- [Set Up Fiscal Inventory Valuation](how-to-set-up-fiscal-inventory-valuation.md)  
- [Set Up Initial Item Costs](how-to-set-up-initial-item-costs.md)  
- [Closing Years and Periods](../../year-close-years-periods.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
