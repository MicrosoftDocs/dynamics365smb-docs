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
# How to: Set Up Items to Use ADCS
Each warehouse item that you want to use with ADCS must be assigned an identifier code to link it with its item number. For example, you can use the item's bar code as the identifier code. An item can also have multiple identifier codes. You may find this useful in the case where an item is available in various units of measures, such as pieces and pallets. In this case, assign an identifier code to each.  
  
### To specify item identifier codes  
  
1.  In the **Search** box, enter **Items**, and then choose the related link.  
  
2.  Select an item from the list that is part of your ADCS solution. On the **Home** tab, in the **Manage** group, choose **Edit**. The **Item Card** window opens.  
  
3.  On the **Navigate** tab, in the **Master Data** group, choose **Identifiers**. The **Item Identifiers List** window opens.  
  
4.  On the **Home** tab, choose **New**. In the **Code** field, specify the identifier for the item. For example, the identifier could be the item's bar code number.  
  
     You can also enter a **Variant Code** and a **Unit of Measure** code.  
  
     If needed, enter multiple codes for each item. Choose **New** again to specify another identifier code. Choose the **OK** button.  
  
5.  To review the information, expand the **Warehouse** FastTab and choose the **Identifier Code** field. The **Item Identifiers List** window opens. You can review the information that you have entered.  
  
## See Also  
 [Use Automated Data Capture Systems \(ADCS\)](../FullExperience/use-automated-data-capture-systems-adcs-.md)   
 Item Identifier   
 Item Identifiers List