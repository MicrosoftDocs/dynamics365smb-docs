---
    title: Physical Inventory Recording - Counting Physical Inventory
    description: After you have created a physical inventory order and after you have entered the physical inventory order lines, you can take the physical inventory. Therefore you can use the physical inventory recording documents.
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
# Physical Inventory Recording - Counting Physical Inventory
After you have created a physical inventory order and after you have entered the physical inventory order lines, you can take the physical inventory. Therefore you can use the physical inventory recording documents.  

A physical inventory recording is related to only one physical inventory order. A physical inventory order may have relations to more than one physical inventory recordings.  

A physical inventory recoding consists of a physical inventory recording header and a number of physical inventory recording lines. The physical inventory recording header contains the information, that are common for all physical inventory recording lines.  

This lines contain the items, locations, bins and the recorded quantities.  

You can create lines manually or you can have the program to create new physical inventory recordings automatically. You can print physical inventory recording lists.  

By setting the Status to finished, you tell the program, that the current physical inventory recording has been finished.  

> [!NOTE]  
>  When you finish the current physical inventory recording, the program assigns every physical inventory recording line to one line of the related physical inventory order. The program assigns this physical inventory order lines with the same values in the 4 fields Item No., Variant Code, Location Code and Bin Code like in the physical inventory recording line.  
>   
>  If there is no such physical inventory order line the program will automatically insert a new line when finishing the physical inventory recording. The program will note this by placing a check mark in the field Recorded without Order on the physical inventory order line.  
>   
>  If there are more than one such physical inventory order lines, an error message appears. You can have the program to show you the duplicate lines.  

## See Also  
 [Create a Physical Inventory Recording](how-to-create-a-physical-inventory-recording.md)   
 [Finish a Physical Inventory Recording](how-to-finish-a-physical-inventory-recording.md)   
 [View Duplicate Physical Inventory Order Lines](how-to-view-duplicate-physical-inventory-order-lines.md)   
 [Physical Inventory Order Lines With Item Tracking Lines](physical-inventory-order-lines-with-item-tracking-lines.md)
