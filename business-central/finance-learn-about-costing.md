---
    title: About Inventory Costing | Microsoft Docs
    description: Managing inventory costs is concerned with recording and reporting business operating costs. It includes the reporting of manufacturing costs and inventory costs, that is, the value of items.
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
# About Inventory Costing
Managing inventory costs is concerned with recording and reporting business operating costs. It includes the reporting of manufacturing costs and inventory costs, that is, the value of items.  

 Central principles to understand are that costing methods define how items are valued when they leave inventory, that cost adjustment updates the cost of goods sold with related purchase costs posted after the sale, and that inventory values must be posted to dedicated G/L accounts at regular intervals.  

 The following table describes a sequence of tasks, with links to the topics that describe them.   

|**To**|**See**|  
|------------|-------------|  
|Distinguish the five different costing methods and their effect on cost flows.|[Design Details: Costing Methods](design-details-costing-methods.md)|  
|Learn how item application entries dynamically link inventory decreases with increases to keep control of cost flows.|[Design Details: Item Application](design-details-item-application.md)|  
|Learn how an item's unit cost is continuously updated with the cost of its latest transaction according to the item's costing method.|[Design Details: Cost Adjustment](design-details-cost-adjustment.md)|  
|Learn how an item's average cost is dynamically calculated according to the selected average cost period.|[Design Details: Average Cost](design-details-average-cost.md)|  
|Distinguish expected cost (not yet invoiced) from actual cost and learn how it is managed in the general ledger.|[Design Details: Expected Cost Posting](design-details-expected-cost-posting.md)|  
|Understand the cost adjustment mechanism, which ensures that costs are brought forward even if inventory transactions happen in a random manner.|[Design Details: Cost Adjustment](design-details-cost-adjustment.md)|  
|Read why standard costs are often used by manufacturing companies as a valuation base for components and end items.|[About Calculating Standard Cost](finance-about-calculating-standard-cost.md)|  
|Understand how the value of inventory is reflected in the general ledger.|[Reporting Costs and Reconciling with the General Ledger](finance-report-costs-and-reconcile-with-the-general-ledger.md)|  
|Learn how item charges, such as freight and insurance, can assign additional cost components to an item's unit cost.|[Use Item Charges to Account for Additional Trade Costs](payables-how-assign-item-charges.md)|  
|Read how inventory periods help a company to control inventory value over time by defining shorter periods that can be closed for posting as the fiscal year progresses.|[Work with Inventory Periods](finance-how-to-work-with-inventory-periods.md)|  
|Understand all mechanisms in the costing engine, including what happens when you post assembly and production transactions.|[Design Details: Inventory Costing](design-details-inventory-costing.md)|  

## See Also
[Managing Inventory Costs](finance-manage-inventory-costs.md)    
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
