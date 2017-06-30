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
# How to: Set Up Operation Codes
You can add as many operation codes as you want to the table. However, the operation codes C, D, and I already exist in Microsoft Dynamics NAV. For example, Credit Memos always have the operation code D. You cannot set up these values in the table because they are system-created codes. If you try to add them, Microsoft Dynamics NAV will return an error.  
  
### To set up operation codes  
  
1.  In the **Search** box, enter **Operation Codes**, and then choose the related link.  
  
2.  In the **Operation Codes** window, fill in the fields as described in the following table  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Enter an operation code. You can only enter one letter or number.<br /><br /> Valid codes are numbers 1 – 8, and letters A – Z.<br /><br /> To submit a report under the CAC regimen, you must make certain that the code Z, which is required for these types of transactions, is in the list of operation codes.|  
    |**Description**|Enter a description for the operation code. You can enter a maximum of 30 letters and numbers.|  
  
### To link operation codes to general product posting groups  
  
1.  In the **Search** box, enter **Posting Groups**, and then choose the related link.  
  
2.  Choose **General Product Posting Groups**.  
  
3.  In the General Product Posting Groups window, link each operation code to a general product posting group.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |Code|Enter a code to create a new general product posting group.|  
    |Description|Enter a description for the general product posting group|  
    |Def. VAT Prod. Posting Group|Select a VAT percentage to link it to the general product posting group.|  
    |Operation Code|Select an appropriate operation code to link it to the general product posting group. You can assigne the same operation code to different posting groups. **Note:**  It is important to link the operation code to the correct VAT product posting group. The Make 340 Declaration report uses the setup to create trade declarations.|  
  
 When you add an operation code to the general product posting group, that association is in turn applied to the items that have that general product posting group.  
  
## See Also  
 [How to: Create Report 340](../how-to-create-report-340.md)