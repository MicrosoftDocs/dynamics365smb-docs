---
    title: How to: Set Up Stockkeeping Units | Microsoft Docs
    description: You can use stockkeeping units to record information about your items for a specific location or a specific variant code.
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
# How to: Set Up Stockkeeping Units
You can use stockkeeping units to record information about your items for a specific location or a specific variant code.  
  
 Stockkeeping units are a supplement to item cards. They do not replace them, although they are related to them. Stockkeeping units allow you to differentiate information about an item for a specific location, such as a warehouse or distribution center, or a specific variant, such as different shelf numbers and different replenishment information, for the same item.  
  
### To set up a stockkeeping unit  
  
1.  In the **Search** box, enter **Stockkeeping Units**, and then choose the related link.  
  
2.  Create a new **Stockkeeping Unit** card. On the **Home** tab, in the **New** group, choose **New**.  
  
3.  Fill in the fields on the card. The following fields are required: **Item No.**, **Location Code**, and/or **Variant Code**.  
  
 For Help about any other field, select the field and press the F1 key.  
  
 After you have set up the first stockkeeping unit for an item, the **Stockkeeping Unit Exists** field on the **Item** card is selected.  
  
> [!NOTE]  
>  The information on the **Stockkeeping Unit** card has priority over the **Item** card.  
>   
>  To create several stockkeeping units for an item, use the **Create Stockkeeping Unit** batch job.  
  
## See Also  
 [How to: Register New Products](../how-to-register-new-products.md)