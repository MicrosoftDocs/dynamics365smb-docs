---
    title: Set Up Inventory Valuation and Costing
    description: To make sure that inventory costs are recorded correctly, you must set up various fields and pages before you begin to make item transactions.
    author: brentholtorf
    ms.topic: conceptual
    ms.search.keywords:
    ms.date: 06/16/2021
    ms.author: bholtorf

---
# Setting Up Inventory Valuation and Costing

To make sure that inventory costs are recorded correctly, you must set up various fields and pages before you begin to make item transactions. Typically, businesses choose a specific costing method and apply that to inventory items, for example, to help them track the value of items on stock.  

> [!TIP]
> For an introduction to costing in [!INCLUDE [prod_short](includes/prod_short.md)], see [About Inventory Costing](finance-learn-about-costing.md).

The following table describes a sequence of tasks, with links to the topics that describe them.

|**To**|**See**|  
|------------|-------------|
|Specify a default costing method for the company to govern how incoming cost is used to assess inventory value and the cost of goods sold.|[Set Up General Inventory Information](inventory-how-setup-general.md)|  
|Specify a costing method on individual items if they require a different costing method.|[Register New Items](inventory-how-register-new-items.md)|  
|Ensure that the cost is automatically posted to the general ledger whenever an inventory transaction is posted.|**Automatic Cost Posting** field on the **Inventory Setup** page|  
|Ensure that expected costs are posted to the general ledger to see from the interim G/L accounts an estimate of the amounts due and the cost of the traded items before they are actually invoiced.|**Expected Cost Posting to G/L** field on the **Inventory Setup** page|  
|Set the system up to adjust for any cost changes automatically every time you post inventory transactions.|[Adjust Item Costs](inventory-how-adjust-item-costs.md)|  
|Define if the average cost is to be calculated per item only or per item for each stockkeeping unit and for each variant of the item.|**Average Cost Calc. Type** field on the **Inventory Setup** page|  
|Select the period of time you would like application to use for calculating the weighted average cost of items that use the average costing method.|**Average Cost Period** field on the **Inventory Setup** page|  
|Define inventory periods to control inventory value over time by disallowing transaction posting in closed inventory periods.|[Work with Inventory Periods](finance-how-to-work-with-inventory-periods.md)|  
|Ensure that sales returns are applied to the original outbound transaction to preserve inventory value.|**Exact Cost Reversing Mandatory** field on the **Sales & Receivables** page|  
|Ensure that purchase returns are applied to the original inbound transaction to preserve inventory value.|**Exact Cost Reversing Mandatory** field on the **Purchases & Payables** page|
|Set up the rounding rules to apply when adjusting or suggesting item prices and when adjusting or suggesting standard costs.|**Rounding Method** page|  

## See Also

[Managing Inventory Costs](finance-manage-inventory-costs.md)  
[Set Up General Inventory Information](inventory-how-setup-general.md)  
[Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md)  
[Setup Best Practices: Costing Method](setup-best-practices-costing-method.md)  
[Design Details: Inventory Costing](design-details-inventory-costing.md)  
[Design Details: Change the Costing Method for Items](design-details-changing-costing-methods.md)  
[Work with Business Central](ui-work-product.md)  
[Finance](finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]