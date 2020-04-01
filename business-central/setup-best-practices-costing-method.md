---
    title: Setup Best Practices - Costing Method | Microsoft Docs
    description: The Costing Method on the item card defines item’s cost flow is recorded and whether an actual or budgeted value is capitalized and used in the cost calculation.
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
# Setup Best Practices: Costing Method
The **Costing Method** on the item card defines item’s cost flow is recorded and whether an actual or budgeted value is capitalized and used in the cost calculation.  

 Setting the correct costing method according to item type and business environment is important to ensure economical inventories.  

 The following table provides best practices on how to set up the **Costing Method** field. For more information, see [Design Details: Costing Methods](design-details-costing-methods.md).  

|Setup option|Best practice|Comment|  
|------------------|-------------------|-------------|  
|FIFO|Use where the product cost is stable.<br /><br /> Use for items with a limited shelf life, because the oldest goods need to be sold before they pass their sell-by date.|An item’s unit cost is the actual value of any receipt of the item, selected by the FIFO rule.<br /><br /> In inventory valuation, it is assumed that the first items placed in inventory are sold first. **Note:**  When prices are rising, the balance sheet shows greater value. This means that tax liabilities increase, but credit scores and the ability to borrow cash improve.|  
|LIFO|Use where levels of inventories are consistently maintained or increased over time.|An item’s unit cost is the actual value of any receipt of the item, selected by the LIFO rule.<br /><br /> In inventory valuation, it is assumed that the last items placed in inventory are sold first. **Note:**  When prices are rising, the value on the income statement decreases. This means that tax liabilities decrease, but the ability to borrow cash deteriorates. **Important:**  Disallowed in many countries/regions, as it can be used to depress profit.|  
|Average|Use where the product cost is unstable.<br /><br /> Use where inventories are piled or mixed together and cannot be differentiated, such as chemicals.|An item’s unit cost is the exact cost at which the particular unit was received.|  
|Specific|Use in production or trade of easily identifiable items with fairly high unit costs.<br /><br /> Use for items that are subject to regulation.<br /><br /> Use for items with serial numbers.|An item’s unit cost is calculated as the average unit cost at each point in time after a purchase.<br /><br /> For inventory valuation, it is assumes that all inventories are sold simultaneously.|  
|Standard|Use where cost control is critical.<br /><br /> Use in repetitive manufacturing, to value the costs of direct material, direct labor, and manufacturing overhead.<br /><br /> Use where there is discipline and staff to maintain standards.|An item’s unit cost is preset based on estimated.<br /><br /> When the actual cost is realized later, the standard cost must be adjusted to the actual cost through variance values.|  

## See Also  
 [Design Details: Costing Methods](design-details-costing-methods.md)   
 [Design Details: Inventory Costing](design-details-inventory-costing.md)   
 [Set Up Complex Application Areas Using Best Practices](set-up-complex-application-areas-using-best-practices.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
