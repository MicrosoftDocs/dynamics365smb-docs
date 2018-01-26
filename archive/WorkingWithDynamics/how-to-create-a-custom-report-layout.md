---
    title: How to Create a Custom Report Layout | Microsoft Docs
    description: By default, a report will have a built-in report layout, which can be either an RDLC report layout or Word report layout, or both. You cannot modify built-in layouts. However, you can create your own custom layouts that enable you to change the appearance of report when it is viewed, printed or saved. You can create multiple custom report layouts for the same report, and then switch the layout that is used by a report as needed.
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
# Create a Custom Report Layout
By default, a report will have a built-in report layout, which can be either an RDLC report layout or Word report layout, or both. You cannot modify built-in layouts. However, you can create your own custom layouts that enable you to change the appearance of report when it is viewed, printed or saved. You can create multiple custom report layouts for the same report, and then switch the layout that is used by a report as needed.  
  
 To create a custom layout, you can either make a copy of an existing custom layout or add a new custom layout, which in most cases is based on a built-in layout. When you add a new custom layout, you can choose to add an RDLC report layout type, Word report layout type, or both. The new custom layout will automatically be based on the built-in layout for the report if one is available. If there is no built-in layout for the type, then a new blank layout is a created, which you will have to modify and design from scratch. For more information about RDLC and Word report layouts, built-in and custom layouts, and more, see [About Report Layouts](../FullExperience/about-report-layouts.md).  
  
### To create a custom layout  
  
1.  In the **Search** box of the ADD INCLUDE<!--[!INCLUDE[nav_windows](../../includes/nav_web_md.md)]-->, enter **Report Layout Selection**, and then choose the related link.  
  
     The **Report Layout Selection** window lists all the reports that are available in the company that is specified in the **Company** field at the top of the window.  
  
2.  Set the **Company** field to the company in which you want to create the report layout.  
  
3.  Select the row for the report that you want to create the layout for, and then on the **Home** tab, in the **Process** group, choose **Custom Layouts**.  
  
     The **Report Layouts** window appears and lists all the custom layouts that are available for the selected report.  
  
4.  If you want to create a copy of an existing custom layout, select the existing custom layout in the list, and then on the **Home** tab, in the **New** group, choose **Copy**.  
  
     The copy of the custom layout appears in the **Report Layouts** window and has the words **Copy of** in the **Description** field.  
  
5.  If you want to add a new custom layout that is based on a built-in layout, do the following:  
  
    1.  On the **Home** tab, in the **New** group, choose **New**.  
  
         The **Report Lookup** window appears. The **ID** and **Name** fields are automatically filled in.  
  
    2.  To add a custom Word report layout type, then select the **Insert Word Layout** check box.  
  
    3.  To add a custom RDLC report layout type, then select the **Insert RDLC Layout** check box.  
  
    4.  Choose the **OK** button.  
  
         The new custom layouts appear in the **Report Layouts** window. If a new layout is based on a built-in layout, then it has the words **Copy of a Built-in Layout** in the **Description** field. If there was no built-in layout for the report, then the new layout has the words **New Layout** in the **Description** field, which indicates that custom layout is blank.  
  
6.  By default, the **Company Name** field is blank, which means that the custom layout will be available for the report in all companies. To make the custom layout available in a specific company only, on the **Home** tab, in the **Manage** group, choose **Edit**, and then set the **Company Name** field to the company that you want.  
  
 The custom layout has been created. You can now modify the custom layout as needed. For more information, see [Modify a Custom Report Layout](../FullExperience/how-to-modify-a-custom-report-layout.md).  
  
 For information about how to make the custom layout the current layout for the report, see [Change Which Layout is Currently Used on a Report](../FullExperience/how-to-change-which-layout-is-currently-used-on-a-report.md).  
  
## See Also  
 [Managing Report Layouts From the Microsoft Dynamics NAV Clients](../FullExperience/managing-report-layouts-from-the-microsoft-dynamics-nav-clients.md)   
 [About Report Layouts](../FullExperience/about-report-layouts.md)