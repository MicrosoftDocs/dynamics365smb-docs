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
# Automatic Breaking Bulk with Directed Put-away and Pick
For locations that use directed put-away and pick, ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> breakbulks as follows:  
  
## Breakbulking in Picks  
 If you want to store items in several different units of measure and allow them to be automatically combined as needed in the picking process, select the **Allow Breakbulk** field on the location card.  
  
 To fulfill a task, the program automatically looks for an item in the same unit of measure. But if it cannot find this form of the item, and this field is selected, the program will suggest that you break a larger unit of measure into the unit of measure that is needed.  
  
 If the program can only find smaller units of measure, it will suggest that you gather items to fulfill the quantity on the shipment or production order. In effect, it breaks the larger unit of measure on the source document into smaller units for picking.  
  
## Breakbulking in Put-aways  
 In the warehouse put-away, the program automatically suggests Place action lines in the put-away unit of measure, for example, pieces, even though the items arrive in a different unit of measure.  
  
## Breakbulking in Movements  
 The program also breakbulks automatically in replenishment movements, if the **Allow Breakbulk** field is selected on the **Option** FastTab in the **Calculate Bin Replenishment** request window.  
  
 You can view the results of the conversion process from one unit of measure to another as intermediate breakbulk lines in the put-away, pick, or movement instructions.  
  
> [!NOTE]  
>  If you select the **Set Breakbulk Filter** field on the warehouse instruction header, the program will hide the breakbulk lines whenever the larger unit of measure is going to be completely used. For example, if a pallet is 12 pieces and you are going to use all 12 pieces, the pick will then direct you to take 1 pallet and place 12 pieces. However, if you have to pick only 9 pieces, then the breakbulk lines will not be hidden, even if you have selected the **Breakbulk Filter** field, because you have to place the remaining three pieces somewhere in the warehouse.  
  
> [!NOTE]  
>  If you want your units of measure to perform optimally in the warehouse, also in connection with the breakbulk functionality, you should wherever possible try to:  
>   
>  -   Set up the base unit of measure for an item as the smallest unit of measure that you expect to handle in your warehouse processes.  
> -   Set up your alternative units of measure for the item as multiples of the base unit of measure.  
  
## See Also  
 Allow Breakbulk   
 [How to: Calculate Bin Replenishment](../FullExperience/how-to-calculate-bin-replenishment.md)   
 [Design Details: Warehouse Management](../FullExperience/design-details-warehouse-management.md)   
 [Perform Warehouse Activities](../FullExperience/perform-warehouse-activities.md)