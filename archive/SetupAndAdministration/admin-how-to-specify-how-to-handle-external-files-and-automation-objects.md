---
    title: How to Specify How to Handle External Files and Automation Objects | Microsoft Docs
    description: When [!INCLUDE[d365fin](includes/d365fin_md.md)] receives an external file, you are presented with a dialog box. In addition to selecting what to do with the file, you can decide how to treat that file type next time it is received.
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
# Specify How to Handle External Files and Automation Objects
When [!INCLUDE[d365fin](includes/d365fin_md.md)] receives an external file, you are presented with a dialog box. In addition to selecting what to do with the file, you can decide how to treat that file type next time it is received.  
  
 When [!INCLUDE[d365fin](includes/d365fin_md.md)] is required to run an automation object, you are presented with a dialog box. You can decide whether that type of object should always or never be able to run.  
  
 You can cancel your decisions for handling files and automation objects by opening the **Reset User-Specified Settings** window from your Role Center. For more information, see [Cancel Basic UI Changes and File Handling Decisions](../how-to-cancel-basic-ui-changes-and-file-handling-decisions.md).  
  
### To specify how to handle external files  
  
1.  When you are presented with the dialog box, clear the **Always ask before opening this type of file** check box if you want [!INCLUDE[d365fin](includes/d365fin_md.md)] to remember the option that you select in step 2. Next time that type file must be handled, the dialog box will not appear, and the file will be treated as specified in step 2.  
  
     Alternatively, select the **Always ask before opening this type of file** check box to always be presented with the dialog box when this file type is received.  
  
2.  Select **Open**, **Save**, or **Cancel**. The file is treated according to your selection.  
  
### To specify how to handle automation objects  
  
1.  When you are presented with the dialog, select the **Always allow** check box if you want [!INCLUDE[d365fin](includes/d365fin_md.md)] to always run that type of automation object. Next time that type of automation object is required to run, the dialog box will not appear, and the automation object will run directly.  
  
     Alternatively, select the **Never allow** check box to. Next time that type of automation object is required to run, the dialog box will not appear, and the automation object will not run.  
  
## See Also  
 PERSONALIZATION Personalize the User Interface   
 [Cancel Basic UI Changes and File Handling Decisions](../how-to-cancel-basic-ui-changes-and-file-handling-decisions.md)   
 [Make Basic UI Changes](../how-to-make-basic-ui-changes.md)   
 DELETEPERSONALIZATION Reset User-Specified Settings   
 [Customize the User Interface](../customize-the-user-interface.md)   
 [Working with Product Name](../working-with-$-p_1-product-name-$-.md)   
 [Learn About the RoleTailored Design](../learn-about-the-roletailored-design.md)