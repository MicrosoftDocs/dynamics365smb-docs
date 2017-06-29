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
# How to: Finish a Physical Inventory Recording
After you have entered all data for a physical inventory recording, you can finish the recording by setting the **Status** field to **Finished**.  
  
 You can only do this, if the **Recorded** field is selected for all physical inventory recording lines for the current physical inventory recording.  
  
### To finish a physical inventory recording  
  
1.  In the **Search** box, enter **Phys. Inventory Recording List**, and then choose the related link.  
  
2.  Open the physical inventory recording that you want to finish.  
  
3.  On the **Home** tab, in the **Process** group, choose **Finish**.  
  
     The status is set to **Finished**. You can no longer change the physical inventory header or the physical inventory lines.  
  
 When you finish the current physical inventory recording, every physical inventory recording line is assigned to one line of the related physical inventory order. The physical inventory order lines are assigned with the same values in the fields **Item No.**, **Variant Code**, **Location Code**, and **Bin Code** as the physical inventory recording line has.  
  
 If no such physical inventory order line exists, and if the **Recording without order permit** field is selected on the physical inventory recording header, a new line is inserted automatically and the **Recorded without Order** field on the physical inventory order line is selected. Otherwise, an error message is displayed and the process is canceled. If there are more than one such physical inventory order lines, an error message is displayed and the process is canceled.  
  
## See Also  
 [How to: Create a Physical Inventory Recording](../FullExperience/how-to-create-a-physical-inventory-recording.md)   
 [How to: Create a Physical Inventory Recording](../FullExperience/how-to-create-a-physical-inventory-recording.md)   
 [How to: View Duplicate Physical Inventory Order Lines](../FullExperience/how-to-view-duplicate-physical-inventory-order-lines.md)   
 [How to: Analyze Physical Inventory Differences](../FullExperience/how-to-analyze-physical-inventory-differences.md)   
 [Physical Inventory Order Lines With Item Tracking Lines](../FullExperience/physical-inventory-order-lines-with-item-tracking-lines.md)