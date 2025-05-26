---
title: Setup best practices - Reordering policies | Microsoft Docs
description: The Reordering Policy field on item cards offers four different planning methods that determine how the individual planning parameters interact.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: best-practice
ms.devlang: al
ms.search.keywords:
ms.date: 06/13/2024
ms.service: dynamics-365-business-central

---
# Setup best practices: Reordering policies

The **Reordering Policy** field on item cards has planning methods that determine how the individual planning parameters interact.  

One best-practice foundation for selecting a reordering policy is the item’s ABC classification. When you use ABC classification, you manage items according to three classes. The class you use depends on the item's value and volume relative to the total stock. The following table shows the value-volume distribution of the three classes.

|Class|Percent of total stock volume|Percent of total stock value|
|-----|-----------------------------|----------------------------|
|A|10-20|50-70|
|B|20|20|
|C|60-70|10-30|

The ABC classification states that effort and money can be saved by applying looser control to items of low value-volume than to items of high value-volume. The following illustration shows which reordering policy in [!INCLUDE[prod_short](includes/prod_short.md)] is best suited for A, B, and C items respectively.

![ABC Classification.](media/abc_classification.png "abc_classification")

The following table provides best practices for selecting between the four policies.  

|Setup option|Best practice|Comment|  
|------------------|-------------------|-------------|  
|**Order**|Use for A items.<br /><br /> Use for make-to-order items.<br /><br /> In manufacturing, use for top-level items and for expensive components and subassemblies.<br /><br /> Use for items that are purchased as drop shipments and special orders.<br /><br /> Don't use if you don't accept automatic reservation.|A items, such as leather couches in a furniture store, are high-value items with low and irregular order velocity where inventory is unacceptable, or the required attributes vary. The best reordering policy is therefore one that plans specifically for each demand.|  
|**Lot-for-Lot**|Use for B items.<br /><br /> In manufacturing, use for components that occur in multiple BOMs. This policy ensures that purchase orders are combined for the same vendor, so better prices can be negotiated.<br /><br /> Use if you aren't sure about which reordering policy to select.|B items, such as dining chairs, have a regular and fairly high order velocity, but also high carrying costs. The best reordering policy for B items is therefore one that is economical by bundling demand in the reorder cycle.<br /><br /> 80 percent of items can use this policy.<br /><br /> Can be used successfully without planning parameters.|  
|**Fixed Reorder Qty.**|Use for C items.<br /><br /> Combine with reorder-point parameters.<br /><br /> In manufacturing, use for lowest-level components.<br /><br /> Don't use if the item is often reserved.|C items, such as tea cups, are low-value items with high and regular order velocity. The best reordering policy for C items is therefore one that guarantees constant availability by always staying above a reorder point.<br /><br /> If the user reserves a quantity for a distant demand, the planning foundation is disturbed. Even if the projected inventory level is acceptable regarding the reorder point, the quantities might not be available because of the reservation.|  
|**Maximum Qty.**|Use for C items with high carrying costs or storing limitations.<br /><br /> Combine with one or more order modifiers (Minimum/Maximum Order Quantity or Order Multiple).|C items, such as tea cups, are low-value items with high and regular order velocity. The best reordering policy for C items is therefore one that guarantees constant availability by always staying above a reorder point, but below a maximum inventory quantity.<br /><br /> To modify the suggested order, you might want the order quantity to be decreased to a specified maximum order quantity, increased to a specified minimum order quantity, or rounded up to meet a specified order multiple. **Note:**  If used with a reorder point, then inventory stays between the reorder point and the maximum quantity.|  

## Related information

 [Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md)  
 [Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md)  
 [Set Up Complex Application Areas Using Best Practices](set-up-complex-application-areas-using-best-practices.md)  
 [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
