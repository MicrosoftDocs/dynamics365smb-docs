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
# How to: Define Check Layouts
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can design your checks to conform with the standards set by the local authorities. Check images can be printed in English, French, or Spanish.  
  
 Checks are designed to print in both the United States and Canadian check image formats in either a check-stub-check format or a stub-stub-check format.  
  
### To define check layouts  
  
1.  In the **Search** box, enter **Report Selections Bank Account**, and choose the related link.  
  
2.  In the **Report Selection - Bank Acc.** window, in the **Usage** field, select **Check**.  
  
3.  Use the following table to determine the ID of the report that you want to use to print checks.  
  
    |Report ID|Report name|ADD INCLUDE<!--[!INCLUDE[bp_tabledescription](../../includes/bp_tabledescription_md.md)]-->|  
    |---------------|-----------------|---------------------------------------|  
    |1401|Check|This is the default report.|  
    |10401|Check \(Stub\/Stub\/Check\)|This report is designed to print checks in a stub\/stub\/check format.|  
    |10411|Check \(Stub\/Check\/Stub\)|This report is designed to print checks in a check\/stub\/check format.|  
  
4.  Choose the **OK** button.  
  
     To print checks, see [How to: Print Checks](../how-to-print-checks.md).  
  
## See Also  
 Check \(Stub-Check-Stub\)   
 Check \(Stub-Stub-Check\)   
 Check   
 [How to: Print Checks](../how-to-print-checks.md)