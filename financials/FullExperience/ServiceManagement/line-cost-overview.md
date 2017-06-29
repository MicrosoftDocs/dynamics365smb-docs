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
# Line Cost Overview
The **Line Cost** field is filled in as described in the following table.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../ApplicationDesign/includes/bp_tableoption_md.md)]-->|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]-->|  
|----------------------------------|---------------------------------------|  
|**Service item**|The cost is automatically retrieved from the **Default Contract Cost** field in the **Service Item** table and copied into the **Line Cost** field. The following formula is used to calculate the line cost:<br /><br /> Sales Unit Cost × Contract Value % ÷ 100|  
|**Item**|The cost is automatically retrieved from the **Unit Cost** field in the **Item** table and the **Contract Value %** field value in the **Service Mgt. Setup** table. The following formula is used to calculate the line cost:<br /><br /> Unit Cost × Contract Value % ÷ 100|  
|**Text description**|The value in the **Line Cost** field is set to zero.|  
  
## See Also  
 Service Item   
 Service Mgt. Setup   
 Contract Value Calc. Method   
 Unit Cost   
 Contract Value Percentage   
 Default Contract Cost