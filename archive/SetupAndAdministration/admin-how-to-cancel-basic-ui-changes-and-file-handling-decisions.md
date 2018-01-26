---
    title: How to Cancel Basic UI Changes and File Handling Decisions | Microsoft Docs
    description: You cancel you basic UI changes and decisions for handling of files and automation objects by opening the **Reset User-Specified Settings** window from your Role Center.
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
# Cancel Basic UI Changes and File Handling Decisions
You cancel you basic UI changes and decisions for handling of files and automation objects by opening the **Reset User-Specified Settings** window from your Role Center.  
  
 As basic types of UI personalization, you can change the size and position of any window, the width of columns, and the height of column headers, and you can change the sorting of data in columns. For more information, see [Make Basic UI Changes](../how-to-make-basic-ui-changes.md).  
  
 You also perform a basic type of personalization when you select whether to run, save, or cancel external files by default and whether to allow automation objects by default. For more information, see [Specify How to Handle External Files and Automation Objects](../how-to-specify-how-to-handle-external-files-and-automation-objects.md).  
  
> [!NOTE]  
>  You perform your main UI personalization in the **Customize** window. The **Reset User-Specified Settings** function does not cancel changes that you make in the **Customize** window. For more information, see [Cancel UI Personalization](../how-to-cancel-ui-personalization.md).  
  
### To cancel basic UI changes that you have made to window sizes, column sizes, or column sorting  
  
1.  Go to your Role Center.  
  
     On the **Application** menu ![Application Menu button in menu bar](../media/applicationmenuicon.png "ApplicationMenuIcon"), choose **Customize**, and then choose **Reset User-Specified Settings**.  
  
2.  Choose the **Reset UI settings** button. Alternatively, choose the **Reset all** button to also cancel your decisions for handling files and automation objects.  
  
 All basic UI changes that you have ever made under your current user logon to [!INCLUDE[d365fin](includes/d365fin_md.md)], or since you last chose the **Reset UI settings** button, are canceled. The user interface is reset to the default configuration for your profile.  
  
### To cancel your decision for running or saving external files  
  
1.  Go to your Role Center.  
  
     On the **Application** menu ![Application Menu button in menu bar](../media/applicationmenuicon.png "ApplicationMenuIcon"), choose **Customize**, and then choose **Reset User-Specified Settings**.  
  
2.  Choose the **Reset file handling decision** button. Alternatively, choose the **Reset all** button to also cancel your view changes and decision for handling automation objects.  
  
 All decisions for default handling of file types that you have ever made under your current user logon, or since you last chose the **Client file access** button, are canceled and reset to the default configuration for your profile. The next time [!INCLUDE[d365fin](includes/d365fin_md.md)] receives an external file of any type, you are presented with a dialog with the options, **Save**, **Run**, and **Cancel**  
  
### To cancel your decision for handling automation objects  
  
1.  Go to your Role Center.  
  
     On the **Application** menu ![Application Menu button in menu bar](../media/applicationmenuicon.png "ApplicationMenuIcon"), choose **Customize**, and then choose **Reset User-Specified Settings**.  
  
2.  Choose the **Reset automation decisions** button. Alternatively, choose the **Reset all** button to also cancel your view changes and decision for running or saving external files.  
  
 All decisions about how to run automation objects that you have ever made under your current user logon, or since you last chose the **Reset automation decisions** button, are canceled. The file handling behavior is reset to the default configuration for your profile.The next time [!INCLUDE[d365fin](includes/d365fin_md.md)] must run an automation object of any type, you are presented with a dialog with the options, **Always allow** and **Never allow**.  
  
## See Also  
 [Make Basic UI Changes](../how-to-make-basic-ui-changes.md)   
 [Specify How to Handle External Files and Automation Objects](../how-to-specify-how-to-handle-external-files-and-automation-objects.md)   
 PERSONALIZATION Personalize the User Interface   
 Delete Profile Configuration   
 [Customize the User Interface](../customize-the-user-interface.md)   
 [Working with Product Name](../working-with-$-p_1-product-name-$-.md)   
 [Learn About the RoleTailored Design](../learn-about-the-roletailored-design.md)