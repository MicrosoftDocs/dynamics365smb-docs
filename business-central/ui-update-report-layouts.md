---
    title: Keeping a Report Layout Up-to-date | Microsoft Docs
    description: You may need to update a custom report layout that is used on a report. This is required when there has been a design change to the report's data set, for example, a field that is used in the layout has been removed from the report data set.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Update Custom Report Layouts
Occasionally, you may need to update a custom report layout that is used on a report. This is required when there has been a design change to the report's data set, for example, a field that is used in the layout has been removed from the report data set. If a report layout requires updating, you will get an error message when you try to preview, print or save the report.  

You can automatically update a report layout from the error message that appears when you run the report by choosing the **Yes** button on the error message. Or, in advance of running reports, you can update specific report layouts or all custom report layouts that might be affected by dataset changes.  

You also have the option to test updates without applying the required changes to the custom report layouts. This enables you to see what changes will be applied to the report layout and identify possible issues in the process. From the test results, you can open the custom report layouts directly for editing to fix any issues. We recommend that you test the report layout update before you apply the updates.  

Not all report dataset changes can be automatically updated in the report layouts. Some changes will require that you manually edit the report layout. For more information, see [Limitations of the Custom Report Layout Update](ui-update-report-layouts.md#UpdateLimitations).  

## To update one or more custom report layouts  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layouts**, and then choose the related link.  

2.  On the **Report Layouts** page, if you want to update a specific report, select the layout from the list, and then choose the **Update Layout** action. Or, if you want to update all custom report layouts for the company, choose the **Update All Layouts** action.  

If no errors occur, then the updates is applied to the report layouts. If errors occur, then a message that contains the errors appears. You will then have to manually edit the custom report layout to fix the error. For more information, see [Fixing Errors](ui-update-report-layouts.md#FixErrors).  

## To test custom report layout updates  

1.  Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Layout Selection**, and then choose the related link.  

2.  On the **Report Layout Selection** page, choose the **Test Layout Updates** action.  

 Changes to the report layouts are tested but not applied to the actual report layouts. A **Report Layout Update Log** page appears that provides the status a potential updates for each report layout. If there are errors for a report layout, you can access the report layout directly for editing from the message to fix any issues. For more information, see [Fixing Errors](ui-update-report-layouts.md#FixErrors).  

##  <a name="UpdateLimitations"></a> Limitations of the Custom Report Layout Update  
 There are several types of changes that the automatic update can apply to custom report layouts, for example, a field that is used in the layout has been removed from the report data set. However, the automatic update cannot handle the following changes to a report dataset.  

1.  Deleted fields, labels, or data items.  

2.  Duplicate field names in the report layout after a field has been renamed in the dataset. This should be treated as a design error.  

3.  Upgrade scenarios where there are multiple iterations of a report layout that causes multiple rename actions on the same fields, labels or data items.  

 If the update process detects any one of these issues, the update cannot be applied. You will have to fix the issues manually, for example by editing the report layout in Word, or programmatically by using upgrade codeunits.  

##  <a name="FixErrors"></a> Fixing Errors  
 If you get an error message when you update or test report layout updates, you most likely will have to modify the report layout to fix the problem. Read the error message to help determine the cause of the problem.  

 The most typical problem occurs when a field that is used on the layout has been removed from the report dataset. In this case, you will see a line in the error message that states that an item has been removed. To fix this issue, you will have to modify the layout and remove the field in question.  

 For more information, see [Create and Modify a Custom Report Layout](ui-how-create-custom-report-layout.md#ModifyCustomLayout).  

After you modify the layout, try to update the layout again.  

## See Related Training at [Microsoft Learn](/learn/modules/change-documents-dynamics-365-business-central/index)

## See Also  
 [Managing Report Layouts](ui-manage-report-layouts.md)  
 [Working with Reports, Batch Jobs, and XMLports](ui-work-report.md)  
