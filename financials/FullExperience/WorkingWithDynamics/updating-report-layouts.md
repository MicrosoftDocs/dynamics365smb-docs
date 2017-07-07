---
    title: Updating Report Layouts | Microsoft Docs
    description: Occasionally, you may need to update a custom report layout that is used on a report. This is required when there has been a design change to the report's data set, for example, a field that is used in the layout has been removed from the report data set. If a report layout requires updating, you will get an error message when you try to preview, print or save the report.
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
# Updating Report Layouts
Occasionally, you may need to update a custom report layout that is used on a report. This is required when there has been a design change to the report's data set, for example, a field that is used in the layout has been removed from the report data set. If a report layout requires updating, you will get an error message when you try to preview, print or save the report.  
  
 You can automatically update a report layout from the error message that appears when you run the report or, in advance of running reports, you can update specific report layouts or all custom report layouts that might be affected by dataset changes.  
  
 You also have the option to test updates without applying the required changes to the custom report layouts. This enables you to see what changes will be applied to the report layout and identify possible issues in the process. From the test results, you can open the custom report layouts directly for editing to fix any issues. We recommend that you test the report layout update before you apply the updates.  
  
 Not all report dataset changes can be automatically updated in the report layouts. When you choose to update or test the custom report layout updates, ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> scans the custom report layouts that are stored in the database and compares them to their corresponding dataset design. Some changes will require that you manually edit the report layout. For more information, see [Limitations of the Custom Report Layout Update](../WorkingWithDynamics/updating-report-layouts.md#UpdateLimitations).  
  
### To update a custom report layout from the error message when you run a report  
  
-   To update report layout from the error message that you get when you run a report, choose the **Yes** button on the error message.  
  
 The system will attempt to update the layout. If the update is unsuccessful, then you get an error message about a condition that must be fixed. For more information, see [Fixing Errors](../WorkingWithDynamics/updating-report-layouts.md#FixErrors).  
  
### To update a specific custom report layout  
  
1.  In the **Search** box, enter **Report Layouts**, and then choose the related link.  
  
2.  In the **Report Layouts** window, select the layout that you want to update, and then on the **Actions** tab, choose **Update Layout**.  
  
 The system will attempt to update the custom report layout to dataset changes. If no errors occur, then the update is applied to the report layout. If errors occur, then a message that contains the errors appears. You will then have to manually edit the custom report layout to fix the error. For more information, see [Fixing Errors](../WorkingWithDynamics/updating-report-layouts.md#FixErrors).  
  
### To update all custom report layouts for the company  
  
1.  In the **Search** box, enter **Report Layout Selection**, and then choose the related link.  
  
2.  In the **Report Layout Selection** window, on the Actions tab, choose Update All Layouts.  
  
 The system will attempt to update the custom report layouts to dataset changes. If no errors occur, then the update is applied to the report layouts. If errors occur, then a message that contains the errors appears. You will then have to manually edit the custom report layouts to fix the error. For more information, see [Fixing Errors](../WorkingWithDynamics/updating-report-layouts.md#FixErrors).  
  
### To test custom report layout updates  
  
1.  In the **Search** box, enter **Report Layout Selection**, and then choose the related link.  
  
2.  In the **Report Layout Selection** window, on the **Actions** tab, choose **Test Layout Updates**.  
  
 ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> validates the changes to the report layouts but does not apply the updates. A **Report Layout Update Log** window appears that provides the status a potential updates for each report layout. If there are errors for a report layout, you can access the report layout directly for editing from the message to fix any issues. For more information, see [Fixing Errors](../WorkingWithDynamics/updating-report-layouts.md#FixErrors).  
  
##  <a name="UpdateLimitations"></a> Limitations of the Custom Report Layout Update  
 There are several types of changes that the automatic update can apply to custom report layouts, for example, a field that is used in the layout has been removed from the report data set. However, the automatic update cannot handle the following changes to a report dataset.  
  
1.  Deleted fields, labels, or data items.  
  
2.  Duplicate field names in the report layout after a field has been renamed in the dataset. This should be treated as a design error.  
  
3.  Upgrade scenarios where there are multiple iterations of a report layout that causes multiple rename actions on the same fields, labels or data items.  
  
 If the update process detects any one of these issues, the update cannot be applied. You will have to fix the issues manually, for example by editing the report layout in Word, or programmatically by using upgrade codeunits.  
  
##  <a name="FixErrors"></a> Fixing Errors  
 If you get an error message when you update or test report layout updates, you most likely will have to modify the report layout to fix the problem. Read the error message to help determine the cause of the problem.  
  
 The most typical problem occurs when a field that is used on the layout has been removed from the report dataset. In this case, you will see a line in the error message that states that an item has been removed. To fix this issue, you will have to modify the layout and remove the field in question.  
  
 For more information, see [How to: Modify a Custom Report Layout](../FullExperience/how-to-modify-a-custom-report-layout.md) and [Removing Label and Data Fields in Word Layouts](../WorkingWithDynamics/how-to-modify-a-custom-report-layout.md#RemoveField).  
  
 After you modify the layout, try to update the layout again.  
  
## See Also  
 [Managing Report Layouts From the Microsoft Dynamics NAV Clients](../FullExperience/managing-report-layouts-from-the-microsoft-dynamics-nav-clients.md)