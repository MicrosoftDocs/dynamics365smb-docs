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
# How to: Set Up Default Dimension Priorities
Different account types, such as a customer account and an item account, can have different default dimensions set up. As a result, an entry can have more than one default dimension proposed for a dimension. To avoid such conflicts, you can apply priority rules to the different sources.  
  
### To set up default dimension priorities  
  
1.  In the **Search** box, enter **Default Dimension Priorities**, and then choose the related link.  
  
2.  In the **Default Dimension Priorities** window, in the **Source Code** field, enter the source code for the entry table to which default dimension priorities will apply.  
  
3.  Fill in a line for each default dimension priority that you want for the selected source code. For Help about a specific field, choose the field and press F1.  
  
4.  Repeat the procedure for each source code for which you want to set up default dimension priorities.  
  
> [!IMPORTANT]  
>  If you set up two tables with the same priority for the same source code, "[!INCLUDE[d365fin](../../includes/d365fin_md.md)] will always select the table with the lowest table ID.  
  
## See Also  
 [How to: Set Up Default Dimensions for One Account](../how-to-set-up-default-dimensions-for-one-account.md)   
 Default Dimension   
 Dimension