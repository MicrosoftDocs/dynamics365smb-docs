---
title: "How to: Specify How to Handle External Files and Automation Objects"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
ms.assetid: a26ec2f1-1d20-4ad4-8b83-9ac4fd059dc5
caps.latest.revision: 6
ms.author: "solsen"
manager: "edupont"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Specify How to Handle External Files and Automation Objects
When [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] receives an external file, you are presented with a dialog box. In addition to selecting what to do with the file, you can decide how to treat that file type next time it is received.  
  
 When [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] is required to run an automation object, you are presented with a dialog box. You can decide whether that type of object should always or never be able to run.  
  
 You can cancel your decisions for handling files and automation objects by opening the **Reset User\-Specified Settings** window from your Role Center. For more information, see [How to: Cancel Basic UI Changes and File Handling Decisions](../SetupAndAdministration/how-to-cancel-basic-ui-changes-and-file-handling-decisions.md).  
  
### To specify how to handle external files  
  
1.  When you are presented with the dialog box, clear the **Always ask before opening this type of file** check box if you want [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] to remember the option that you select in step 2. Next time that type file must be handled, the dialog box will not appear, and the file will be treated as specified in step 2.  
  
     Alternatively, select the **Always ask before opening this type of file** check box to always be presented with the dialog box when this file type is received.  
  
2.  Select **Open**, **Save**, or **Cancel**. The file is treated according to your selection.  
  
### To specify how to handle automation objects  
  
1.  When you are presented with the dialog, select the **Always allow** check box if you want [!INCLUDE[dyn_nav](../ApplicationDesign/includes/dyn_nav_md.md)] to always run that type of automation object. Next time that type of automation object is required to run, the dialog box will not appear, and the automation object will run directly.  
  
     Alternatively, select the **Never allow** check box to. Next time that type of automation object is required to run, the dialog box will not appear, and the automation object will not run.  
  
## See Also  
 [\($ S\_PERSONALIZATION Personalize the User Interface $\)](../SetupAndAdministration/-$-s_personalization-personalize-the-user-interface-$-.md)   
 [How to: Cancel Basic UI Changes and File Handling Decisions](../SetupAndAdministration/how-to-cancel-basic-ui-changes-and-file-handling-decisions.md)   
 [How to: Make Basic UI Changes](../SetupAndAdministration/how-to-make-basic-ui-changes.md)   
 [\($ S\_DELETEPERSONALIZATION Reset User\-Specified Settings $\)](../Topic/\($%20S_DELETEPERSONALIZATION%20Reset%20User-Specified%20Settings%20$\).md)   
 [Customize the User Interface](../SetupAndAdministration/customize-the-user-interface.md)   
 [Working with \($ P\_1 Product Name $\)](../WorkingWithDynamics/working-with-$-p_1-product-name-$-.md)   
 [Learn About the RoleTailored Design](../GettingStarted/learn-about-the-roletailored-design.md)