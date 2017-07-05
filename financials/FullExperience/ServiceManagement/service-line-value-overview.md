---
    title: Line Value Overview | Microsoft Docs
    description: The **Line Value** field is filled in as described in the following table.
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
# Line Value Overview
The **Line Value** field is filled in as described in the following table.  
  
|ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../../includes/bp_tabledescription_md.md)]-->|  
|----------------------------------|---------------------------------------|  
|**Service item**|The price is automatically retrieved from the **Default Contract Value** field in the **Service Item** table and copied into the **Line Value** field.|  
|**Item**|Depending on the value in the **Contract Value Calc. Method** field in the **Service Mgt. Setup** table, the amount is retrieved from either the **Unit Price** or the **Unit Cost** field in the **Item** table. After that, this value is multiplied by the contents of the **Contract Value %** field in the **Service Mgt. Setup** table and divided by 100. This amount is copied into the **Line Value** field.<br /><br /> **NOTE:** If the **Contract Value Calc. Method** field is set to **None**, the contents of the **Line Value** field are not calculated.|  
|**Text description**|The contents of the **Line Value** field are set to zero.|  
  
## See Also  
 Service Item   
 Service Mgt. Setup   
 Default Contract Value   
 Contract Value Calc. Method   
 Unit Price   
 Unit Cost   
 Contract Value Percentage