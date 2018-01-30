---
    title: How to Change Which Layout is Currently Used on a Report | Microsoft Docs
    description: This procedure describes how to change the layout that is used by a report. A report can be set up with more than one report layout, which you can then switch among as needed.
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
# Change Which Layout is Currently Used on a Report
This procedure describes how to change the layout that is used by a report. A report can be set up with more than one report layout, which you can then switch among as needed.  
  
 Depending on the layouts that are available for a report, you can choose to use a built-in RDLC report layout, a built-in Word report layout, or a custom layout. For more information about RDLC and Word report layouts, built-in and custom layouts, and more, see [About Report Layouts](../FullExperience/about-report-layouts.md).  
  
### To change the layout that is used on a report  
  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Report Layout Selection**, and then choose the related link.  
  
     The **Report Layout Selection** window lists all the reports that are available for the company that is specified in the **Company** field at the top of the window.  
  
     The **Selected Layout** field specifies the layout that is currently used on the report.  
  
2.  Set the **Company** field at the top of the window to the company that includes the report.  
  
3.  To change the layout that is used by a report, in the row for the report in the list, set the **Selected Layout** field to one of the following options:  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tableoption](../../includes/bp_tabledescription_md.md)]-->|  
    |----------------------------------|---------------------------------------|  
    |**RDLC (built-in)**|Uses the built-in RDLC report layout on the report.|  
    |**Word (built-in)**|Uses the built-in Word report layout on the report.|  
    |**Custom**|Uses a custom layout on the report.<br /><br /> You can see which custom layouts are available for the report in the **Custom Layouts** FactBox. If there are no custom layouts for the report, then you will have to create one first.<br /><br /> If you choose this option, go to the next procedure to specify the custom layout that you want to use.|  
  
    > [!NOTE]  
    >  If you choose **RDLC (built-in)** or **Word (built-in)** and you get an error message that the report does not have a layout of the specified type, then you must choose another layout option or create a custom report layout of the type that you want to use.  
  
 If you selected a built-in RDLC or Word report layout, then no further action is required and the layout will be used the next time the report is run.  
  
### To specify a custom layout on a report  
  
1.  You specify which custom layout to use on the report from the **Report Layouts** window. If the **Report Layouts** window is not open, then in the **Report Layout Description** field, choose the lookup button.  
  
2.  In the **Report Layouts** window, select the row for custom layout that you want to use, and then choose the **OK** button.  
  
 You return to the **Report Layout Selection** window. The name of the selected custom layout displays in the **Report Description** field. The custom layout will be used the next time that you run the report.  
  
## See Also  
 [Managing Report Layouts From the Microsoft Dynamics NAV Clients](../FullExperience/managing-report-layouts-from-the-microsoft-dynamics-nav-clients.md)   
 [Designing Report Layouts from the Microsoft Dynamics NAV Development Environment](../FullExperience/Designing%20Report%20Layouts%20from%20the%20Microsoft%20Dynamics%20NAV%20Development%20Environment.md)   
 [Modify a Custom Report Layout](../FullExperience/how-to-modify-a-custom-report-layout.md)   
 [Create a Custom Report Layout](../FullExperience/how-to-create-a-custom-report-layout.md)