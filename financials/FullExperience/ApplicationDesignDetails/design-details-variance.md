---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# Design Details: Variance
Variance is defined as the difference between the actual cost and the standard cost, as described in the following formula.  
  
 actual cost – standard cost \= variance  
  
 If the actual cost changes, for example, because you post an item charge on a later date, then the variance is updated accordingly.  
  
> [!NOTE]  
>  Revaluation does not affect the variance calculation, because revaluation only changes the inventory value.  
  
## Example  
 The following example illustrates how variance is calculated for purchased items. It is based on the following scenario:  
  
1.  The user purchases an item at LCY 90.00, but the standard cost is LCY 100.00. Accordingly, the purchase variance is LCY –10.00.  
  
2.  LCY 10.00 is credited to the purchase variance account.  
  
3.  The user posts an item charge of LCY 20.00. Accordingly, the actual cost is increased to LCY 110.00, and the value of the purchase variance becomes LCY 10.00.  
  
4.  LCY 20.00 is debited to the purchase variance account. Accordingly, the net purchase variance becomes LCY 10.00.  
  
5.  The user revalues the item from LCY 100.00 to LCY 70.00. This does not affect the variance calculation, only the inventory value.  
  
 The following table shows the resulting value entries.  
  
 ![Purchase variance calculation](../FullExperience/media/design_details_inventory_costing_11_purchase_variance.png "design\_details\_inventory\_costing\_11\_purchase\_variance")  
  
## Determining the Standard Cost  
 The standard cost is used when calculating variance and the amount to capitalize. Since the standard cost can be changed over time because of manual update calculation, you need a point in time when the standard cost is fixed for variance calculation. This point is when the inventory increase is invoiced. For produced or assembled items, the point when standard cost is determined is when the cost is adjusted.  
  
 The following table shows how different cost shares are calculated for produced and assembled items when you use the Calculate Standard Cost function.  
  
|Cost share|Purchased item|Produced\/Assembled item|  
|----------------|--------------------|------------------------------|  
|**Standard Cost**||Single-Level Material Cost \+ Single-Level Capacity Cost \+ Single-Level Subcontrd. Cost \+ Single-Level Cap. Ovhd. Cost \+ Single-Level Mfg. Ovhd. Cost|  
|**Single-Level Material Cost**|Unit Cost|![Equation 1](../FullExperience/media/design_details_inventory_costing_11_equation_1.png "design\_details\_inventory\_costing\_11\_equation\_1")|  
|**Single-Level Capacity Cost**|Not applicable|![Equation 2](../FullExperience/media/design_details_inventory_costing_11_equation_2.png "design\_details\_inventory\_costing\_11\_equation\_2")|  
|**Single-Level Subcontrd. Cost**|Not applicable|![Equation 3](../FullExperience/media/design_details_inventory_costing_11_equation_3.png "design\_details\_inventory\_costing\_11\_equation\_3")|  
|**Single-Level Cap. Ovhd Cost**|Not applicable|![Equation 4](../FullExperience/media/design_details_inventory_costing_11_equation_4.png "design\_details\_inventory\_costing\_11\_equation\_4")|  
|**Single-Level Mfg. Ovhd Cost**|Not applicable|\(Single-Level Material Cost \+ Single-Level Capacity Cost \+ Single-Level Subcontrd. Cost\) \* Indirect Cost % \/ 100 \+ Overhead Rate|  
|**Rolled-up Material Cost**|Unit Cost|![Equation 5](../FullExperience/media/design_details_inventory_costing_11_equation_5.png "design\_details\_inventory\_costing\_11\_equation\_5")|  
|**Rolled-up Capacity Cost**|Not applicable|![Equation 6](../FullExperience/media/design_details_inventory_costing_11_equation_6.png "design\_details\_inventory\_costing\_11\_equation\_6")|  
|**Rolled-Up Subcontracted Cost**|Not applicable|![Equation 7](../FullExperience/media/design_details_inventory_costing_11_equation_7.png "design\_details\_inventory\_costing\_11\_equation\_7")|  
|**Rolled-up Capacity Ovhd. Cost**|Not applicable|![Equation 8](../FullExperience/media/design_details_inventory_costing_11_equation_8.png "design\_details\_inventory\_costing\_11\_equation\_8")|  
|**Rolled-up Mfg. Ovhd. Cost**|Not applicable|![Equation 9](../FullExperience/media/design_details_inventory_costing_11_equation_9.png "design\_details\_inventory\_costing\_11\_equation\_9")|  
  
## See Also  
 [Design Details: Inventory Costing](../FullExperience/design-details-inventory-costing.md)   
 [Design Details: Costing Methods](../FullExperience/design-details-costing-methods.md)