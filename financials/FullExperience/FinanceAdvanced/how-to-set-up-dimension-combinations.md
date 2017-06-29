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
# How to: Set Up Dimension Combinations
To avoid posting entries with contradictory or irrelevant dimensions, you can block or limit specific combinations of two dimensions. A blocked dimension combination means that you cannot post both dimensions on the same entry regardless of what the dimension values are. A limited dimension combination lets you post both dimensions to the same entry, but only for certain combinations of dimension values.  
  
### To set up dimension combinations  
  
1.  In the **Search** box, enter **Dimension Combinations**, and then choose the related link.  
  
2.  In the **Dimension Combinations** window, choose the field of the dimension combination and select one of the following options.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------------------------------|  
    |**No limitation**|This dimension combination has no restrictions. All dimensions values are allowed.|  
    |**Limit**|This dimension combination has restrictions depending on which dimension values that you enter. You must define the limitations in the **Dimension Value Combination** window.|  
    |**Blocked**|This dimension combination is not allowed.|  
  
3.  If you selected the **Limited** option, you must define which combinations of dimension values are blocked. To do this, choose the field to define the dimension combination.  
  
4.  Now select a dimension value combination that is blocked and enter **Blocked** in the field. A blank field means that the dimension value combination is allowed. Repeat if multiple combinations are blocked.  
  
> [!NOTE]  
>  The same dimensions are displayed in both rows and columns and, therefore, all dimension combinations appear two times. ADD INCLUDE<!--[!INCLUDE[navnow](../ApplicationDesign/includes/navnow_md.md)]--> automatically displays the setting in both fields. You cannot select anything in the fields from the upper\-left corner and down, because these fields have the same dimension in both rows and columns.  
>   
>  The selected option is not visible before you exit the field.  
>   
>  To show the name of the dimensions instead of the code, select the **Show Column Name** field.  
  
## See Also  
 [How to: Set Up Default Dimensions for One Account](../Finance/how-to-set-up-default-dimensions-for-one-account.md)   
 Default Dimension   
 Dimension