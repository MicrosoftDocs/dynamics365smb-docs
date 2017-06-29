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
# How to: Calculate Proportional VAT
You can use proportional VAT to calculate VAT when there is both deductible and non-deductible VAT. Because it is difficult to know where and how an item is used, you will have to contact the Norwegian tax authorities to determine whether a specified percentage of the VAT is deductible based on historical data.  
  
### To calculate proportional VAT  
  
1.  In the **Search** box, enter **VAT Posting Setup**, and then choose the related link.  
  
2.  In the **VAT Posting Setup** window, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Calc. Prop. Deduction VAT**|Select to indicate that you want to use the proportional VAT percentage. **Important:**  This field is available in the **VAT Posting Setup** window, but it is not shown by default. ADD INCLUDE<!--[!INCLUDE[bp_customize](../../includes/bp_customize_md.md)]-->|  
    |**\($ T\_325\_10605 Proportional Deduction VAT % $\)**|Enter the percentage of VAT to deduct.|  
  
3.  Choose the **OK** button.  
  
## See Also  
 [Proportional VAT](../FullExperience/proportional-vat.md)   
 [Norway Local Functionality](../FullExperience/norway-local-functionality.md)   
 PERSONALIZATION Personalize the User Interface