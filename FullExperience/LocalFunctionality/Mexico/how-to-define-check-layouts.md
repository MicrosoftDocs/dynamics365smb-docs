---
title: "How to: Define Check Layouts"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "checks, defining"
  - "checks, layouts"
ms.assetid: 54d0a92d-ff6e-4870-937b-9c35efcb45b9
caps.latest.revision: 9
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "en-ca"
  - "es-mx"
  - "fr-ca"
---
# How to: Define Check Layouts
In [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)], you can design your checks to conform with the standards set by the local authorities. Check images can be printed in English, French, or Spanish.  
  
 Checks are designed to print in both the United States and Canadian check image formats in either a check\-stub\-check format or a stub\-stub\-check format.  
  
### To define check layouts  
  
1.  In the **Search** box, enter **Report Selections Bank Account**, and choose the related link.  
  
2.  In the **\($ N\_385 Report Selection \- Bank Acc. $\)** window, in the **\($ N\_385\_11 Usage $\)** field, select **Check**.  
  
3.  Use the following table to determine the ID of the report that you want to use to print checks.  
  
    |Report ID|Report name|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------|-----------------|---------------------------------------|  
    |1401|\($ R\_1401 Check $\)|This is the default report.|  
    |10401|\($ R\_10401 Check \(Stub\/Stub\/Check\) $\)|This report is designed to print checks in a stub\/stub\/check format.|  
    |10411|\($ R\_10411 Check \(Stub\/Check\/Stub\) $\)|This report is designed to print checks in a check\/stub\/check format.|  
  
4.  Choose the **OK** button.  
  
     To print checks, see [How to: Print Checks](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-print-checks.md).  
  
## See Also  
 [\($ R\_10411 Check \(Stub\-Check\-Stub\) $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-r_10411-check-stub-check-stub-$-.md)   
 [\($ R\_10401 Check \(Stub\-Stub\-Check\) $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-r_10401-check-stub-stub-check-$-.md)   
 [\($ R\_1401 Check $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/-$-r_1401-check-$-.md)   
 [How to: Print Checks](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Canada/how-to-print-checks.md)